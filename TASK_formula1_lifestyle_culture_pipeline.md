# TASK：Formula1.com Lifestyle & Culture 列表 → 详情 → 全文中译 → mp_news 入库

## 1. 范围与入口

本任务在 `feature/f1-lifestyle-culture` 分支运行，沿用原工作流的“最新 10 条快照 → 逐篇双文件 → POST → 核验”逻辑，但针对 Formula1.com 栏目及详情页重新定义抽取规则。

- 列表： https://www.formula1.com/en/latest/tags/lifestyle-culture.4R2e2KAaQF8RBPPy7GeeL7
- 栏目：Lifestyle & Culture；tag ID：`4R2e2KAaQF8RBPPy7GeeL7`
- 默认数量：10，按栏目主列表展示顺序去重后截取；不是全站最新 10 条。
- 状态文件：`formula1_lifestyle_culture_state.json`（执行列表任务时才创建）。不得读写旧 `motorsport_f1_news_state.json`。
- 入库接口：`https://f1ink.normal-person.icu/api/v1/mp/news/ingest`，无 token。
- 字段规范：生成数据前必须读取 `mp_news_content.md` 与 `mp_news_ingest_api.md`。
- 默认运行模式：全流程；用户仅要求列表时只刷新快照，仅要求单篇时跳过列表；用户只要求制定任务时不得抓取全文批量翻译或 POST。
- 本任务不调用旧 Motorsport 抓取脚本，不继承 Autosport 源名、文件前缀和 `msnt-author-toolbar` 时间规则。

**翻译必须逐句忠实、覆盖全文，不得用摘要、改写或要点替代正文。** 标题、导语、小节标题、引语、括号、数字、正文图注均须保留和翻译。

## 2. Git 与执行边界

1. 开始执行前检查分支和工作区；只在本分支操作。不得切回 main 后运行，也不得把用户已有修改混入产物。
2. 已配置 upstream 时执行一次 `git pull --ff-only`；新分支尚无 upstream 时明确报告，不能误拉 main 覆盖本分支。
3. 仅在用户已授权提交/推送时执行 commit/push；先核验全部结果，再提交任务相关文件并推送当前分支。不得自动向 main 推送，不使用强推。
4. 清空本地文章产物不代表清空线上数据库，也不代表远端文章尚未入库。不得删除线上记录。
5. 临时 HTML、抽取脚本、调试输出放到系统临时目录，根目录只保留最终产物及必要状态。

## 3. 列表任务：刷新最新快照

### 3.1 抓取与筛选

1. HTTP/WebFetch 获取指定栏目；若返回登录、挑战、错误页或正文缺失，使用浏览器查看实际栏目。不要把错误响应当作空列表。
2. 只从标题为 Lifestyle & Culture 的主文章列表抽取卡片链接；忽略导航、页脚、推荐区以及其他栏目链接。
3. 相对链接转绝对地址。仅接收主机 `www.formula1.com`、路径 `/en/latest/article/` 的文章详情；排除视频、画廊索引、商店、车手页及站外链接。
4. 去除 fragment 和跟踪 query，保持路径、大小写及 URL 尾部内容 ID，不擅自添加尾斜杠。以规范 URL 去重，保留首次出现顺序。
5. 取前 10 条。如果当前可见不足 10 条，检查实际存在的“加载更多”/分页并继续收集，最多补足 10 条；禁止臆造分页参数或未验证的 API。
6. 若确实已到列表末尾，允许少于 10 条并注明原因；若加载失败导致不足，则保留旧快照并报告失败。正常页面却提取为 0 条时按结构变化处理，不覆盖有效旧快照。
7. 卡片标题可能是短标题，只用于发现链接；详情页标题才是翻译依据。卡片的“21 hours ago”等相对时间不能作为最终 published_at。

### 3.2 状态格式

以下仅为结构示例，不是应直接落盘的抓取结果：

```json
{
  "source": "https://www.formula1.com/en/latest/tags/lifestyle-culture.4R2e2KAaQF8RBPPy7GeeL7",
  "fetched_at": "2026-11-09T00:00:00+08:00",
  "count": 1,
  "urls": [
    "https://www.formula1.com/en/latest/article/beyond-the-track-hamiltons-remarkable-projects-away-from-f1-as-he-marks-400-grand-prix-starts.2EHQU6DAJjIFgT7OfB5iHf"
  ]
}
```

- fetched_at 使用本次实际执行时间，RFC3339，带时区。
- count 必须等于去重后的 urls 长度，且不大于 10。
- 提取、校验成功后再覆盖状态文件；状态是最新快照，不是消费队列。任何单篇成功/失败都不删除 urls。
- 用户明确要求全量历史时才遍历所有实际分页，并先明确范围；默认不无限回溯。

## 4. 详情任务：抓取真实正文

每个 URL 独立执行，单篇失败不阻止其余文章，但必须报告失败，不能宣称整批全部完成。

### 4.1 URL、标题、来源与时间

1. 获取详情原始 HTML，记录最终重定向地址及 canonical。只有确认为同一篇 Formula1.com 文章的 canonical 才可采用；对跨站或不同内容的重定向停止处理并报告。
2. 最终规范 article_url 用于 source.url、去重及 SHA1。列表 URL 有别名时记录映射，不重复生成。
3. 标题优先详情页 H1，并与 JSON-LD headline 核对；保留原英文标题于 Markdown 元信息。作者按实际页面记录，不将作者头像视为正文图。
4. published_at 优先取属于当前文章的 JSON-LD Article/NewsArticle.datePublished（可能位于数组或 @graph）；其次 article:published_time；再次详情页可见绝对发布时间或 time[datetime]。若多个来源冲突，核对时区并记录取舍。
5. dateModified 仅为更新时间，不能无说明替代首次发布时间。缺少时区时不得臆测；日期仅有年月日或时间完全缺失时记录不确定，暂停该篇 POST，等待补证/用户确认。
6. 输出 published_at 为带时区 RFC3339；timezone_name 为 Asia/Shanghai。文件名日期统一取发布时间转换至 Asia/Shanghai 后的 YYYYMMDD。
7. source.name 固定 Formula1.com；不沿用 Autosport，也不寻找不同内容的转载替代正文。

### 4.2 正文边界与完整性

1. 使用文章内容容器/结构化正文，包含 H1 下的导语、所有自然段、小节标题、列表、引用、正文图片及图注。
2. JSON-LD articleBody 可辅助核对，但可能不包含图片和完整富文本，不能仅凭它认定抓取完整。WebFetch 也可能省略结构，需与原始 HTML/浏览器交叉确认。
3. 在 Next Up、Related Articles、页脚等推荐区前结束；排除导航、分享按钮、订阅入口、独立“相关阅读”推荐卡片、商店促销（例如 F1 Store / SHOP NOW）、作者头像和广告。正文段落中的人物/品牌链接及文字必须保留。
4. 标题、导语可能在结构化数据和 DOM 重复出现，按实际正文顺序只保留一次。不要用全页所有 p/img 直接拼接。
5. 对嵌入视频、社交媒体和图集，保留公开可读取的正文说明及必要链接；不能虚构视频台词或漏掉图集的实际正文图。若关键内容无法获取，注明并暂停该篇入库。
6. 遇访问限制、登录墙或机器人验证，不绕过限制；可使用用户提供且能核实来源的完整 HTML 快照。快照不完整时请求补充，不将摘要当全文。

### 4.3 图片：使用原站真实资源

1. 用浏览器从头至尾分段滚动（每次约 600–1200px），结合快照/DOM 收集 src、currentSrc、data-src、srcset。到达正文末尾且连续 2–3 次无新增正文图后结束；浏览器不可用则明确记录校验未完成，不宣称图片齐全。
2. 优先采用页面实际引用的 `media.formula1.com` 原图/CDN 地址。从已存在的 srcset 选合适清晰度，不凭空拼接 Cloudinary 版本号、尺寸路径或资源名。
3. WebFetch 结果可能将图片替换为 `ibyteimg.com` 等代理地址；这些不是已验证的原站资源，必须回到原始 HTML/浏览器解析真实 URL。不得用搜索缩略图替代。
4. 本地快照 `_files` 路径不能入库；从原站恢复真实公开 URL，空格正确 URL 编码，避免重复编码。
5. 按实际图片资源去重，同图不同尺寸只保留一次；保留每张不同正文图及对应图注。逐一验证可访问性，HEAD 不支持时用 GET 核验，不以 HEAD 失败直接判定无图。
6. cover_url = 正文第一张图；将其唯一的 img 节点置于 nodes[0]，其余图按正文原位置插入，不再重复头图。确实无图时 cover_url 为空串且无 img 节点；图片提取失败不等于无图，应报告并暂停 POST。
7. img.attrs 为 src、中文 alt、mode=`widthFix`、style=`width:100%;display:block;`。图注另作可读文本节点，不仅藏在 alt 中。

## 5. 全文翻译、命名和字段

### 5.1 翻译与双文件

逐句翻译全部有效正文，保留引述层次、作品名称、年份、金额、数量、比例与括号含义；人名/车队/机构译名一致。不得自行纠正、补写原文事实，发现疑点在元信息备注中列出。

- sha1_10 = SHA1(最终规范 article_url 的 UTF-8 字节) 的前 10 位小写十六进制。
- Title_Slug 使用详情英文标题生成小写 ASCII slug，非字母数字连续串替换为 `-`，去除首尾 `-`；过长时缩短 slug，保留完整日期与 hash。相同 URL 不因卡片标题变化创建第二组文件。
- Markdown：`YYYYMMDD_f1_<Title_Slug>_<sha1_10>.md`
- JSON：`YYYYMMDD_f1_<Title_Slug>_<sha1_10>.ingest.json`
- id：`n_f1_YYYYMMDD_<sha1_10>`
- Markdown 元信息包含 id、源名、原始/规范 URL、英文标题、作者（若有）、发布时间及来源、封面、栏目、必要抽取备注；中文正文与 nodes 的标题、段落、图及图注顺序一致。

### 5.2 入库字段

请求体保持 API 定义的平铺结构，禁止擅自添加未支持的业务枚举。

- source：`{"name":"Formula1.com","url":"<规范 article_url>"}`。
- layout_code：人物长文/专题常用 FEATURE，普通资讯 STANDARD；按实际语义选择 API 允许值，不因栏目归属就强制全部 FEATURE。
- type_code：人物生活、采访用 DRIVER；车队文化合作/围场娱乐通常 PADDOCK；其他按 REGULATION/STRATEGY/TECH 等既有枚举判断。不得新增 LIFESTYLE 类型。
- tag_text：`<主实体> / <文章属性>`，仅一个 `/`，例如 `Hamilton / 专题`、`Williams / 文化合作`；多人物文章可用 F1 主实体，避免标题复述。
- tags：非空原子词数组，栏目词 `lifestyle`、`culture`，再添加实际相关实体/属性；不照搬源站所有标签，不使用命名空间格式替换既有约定。
- 任一车手 slug 必须配车号字符串；每批从 `GET https://f1ink.normal-person.icu/api/v1/mp/session-results?latest=1` 获取并核实。历史/退役车手或接口无匹配时不可猜测；可不添加该车手 slug，使用已核实的其他主题词并备注，正文和 tag_text 可照常提及人物。
- content.format_code：RICH_TEXT_NODES。
- content.text：中文标题层级文本、段落及图注，以空行分隔；不含抓取说明、导航、广告。
- content.nodes：遵守 mp_news_content.md，用受支持的节点保留 p、标题、图片、列表等结构；文本不能含尚未替换的英文正文或占位符。

## 6. 去重、POST 与失败重跑

**本分支文章已清空，不能仅靠本地文件判断服务器是否已有文章。** Hamilton 400 场专题此前已成功入库，清空文件不会撤销该记录。

1. 先检查本地同规范 source.url/hash 的双文件。文件存在只说明已生成，不代表 POST 成功，不能一律跳过上传。
2. 再按 API 文档查询服务器是否已有对应 id/source.url；列表分页必须遵循实际返回字段和分页规则，不能假设 page_size=1000 能取全量。列表未返回 source 对象时不要强行读取；优先使用文档支持的详情查询核实。
3. 远端已存在且不要求更新时跳过重复 POST，并报告远端命中；本地缺稿时可重新生成，但保持原有 id。若日期取舍变化造成新 id，先按 canonical URL 核查，不能制造重复新闻。
4. 远端是否存在不能确认时，先查清接口的重复 id 行为，不猜测其为 upsert；记录待确认，不盲目重复 POST。
5. POST 前检查 JSON 可解析、枚举有效、tag_text 单斜杠、车手号配对、时间带时区、source 正确、封面等于首图、图片无本地路径/代理占位图，以及译文完整性。
6. 全流程模式逐条 POST；仅单篇模式依用户“需要入库”选项决定。Content-Type 为 application/json，请求体 UTF-8，无外层包装。
7. 成功条件：HTTP 200、响应 ok=true、响应 id 与请求一致。随后使用文档支持的详情/列表接口复核 id、标题、时间及关键字段。响应丢失/超时先查服务器再重试，避免重复提交。
8. 保存成功/失败结果并汇报；失败时保留双文件用于重跑，不改变快照 urls。每次重跑均核对远端状态，不把“文件存在”当作成功标记。

## 7. 验收与报告

- 列表：来源准确，按主列表顺序去重，count 与 urls 一致，默认至多 10 条。
- 详情：标题/导语/全部段落/小节/图注完整，推荐与商店模块已剔除，发布时间可追溯，真实图片已核实。
- 产物：仅 f1 前缀，Markdown 与 JSON 内容一致，符合接口字段约束。
- 入库：分别报告新生成、远端已存在、POST 成功、失败/待确认数量与原因；不能因部分成功声称全批完成。
- Git：仅在授权且所有必要工作完成后提交并推送本分支，未完成不提前推送。

## 8. 结构核验依据（2026-11-09）

已读取栏目及以下详情作为任务设计依据，不是固定待处理清单：

- 栏目主列表含 Hamilton、赛车拍卖、亡灵节、恶作剧、音乐及文化合作等文章；卡片时间既有相对时间也有绝对日期。
- https://www.formula1.com/en/latest/article/from-the-circuit-to-comic-con-how-williams-joined-the-marvel-universe.2CRyGcEiwfgZ67ouVodMxF
- Williams 样本含导语、UTC 发布时间、署名、多个小标题、正文图注、独立相关阅读、F1 Store 商店推广和 Next Up/Related Articles；因此不能全页无差别提取文本与图片。
- WebFetch 展示了代理图 URL，因此必须从原站 HTML/浏览器恢复真实图片；本次未验证分页接口或固定 CSS 选择器，运行时应检查真实页面，不将猜测写成实现事实。
