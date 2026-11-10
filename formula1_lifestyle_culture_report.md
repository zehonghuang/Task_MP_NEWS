# F1 Lifestyle & Culture 栏目全文中译入库 · 验收报告

- 任务依据：`TASK_formula1_lifestyle_culture_pipeline.md`（入口索引 `TASK_mp_news_tasks_index.md`）
- 执行完成时间：2026-11-10（Asia/Shanghai）
- 栏目快照：`formula1_lifestyle_culture_state.json`，fetched_at = 2026-11-09T15:37:55+08:00，来源 `https://www.formula1.com/en/latest/tags/lifestyle-culture.4R2e2KAaQF8RBPPy7GeeL7`，count=10 与 urls 数一致

## 1. 约束执行情况

| 约束 | 结果 |
| --- | --- |
| 禁止 WebFetch | 遵守。全部抓取经本地 python 脚本（urllib）完成 |
| 翻译禁用翻译平台 API | 遵守。9 篇译文均为逐句人工（模型）直译，未调用任何翻译接口 |
| 去重以远端为准 | 执行。抓取远端全量列表 id 后按 SHA1(canonical) 前 10 位比对：仅 #01 Hamilton 篇命中远端既有记录 `n_f1_20261108_fe848630b4`，跳过入库 |
| 现役车手 slug 必配车号 | 执行。车号经 `session-results?latest=1`（session_key=11412）核实：hamilton/44、alonso/14、gasly/10、perez/11、sainz/55、bottas/77、albon/23；历史/退役车手（Senna、Schumacher 等）不加 slug |
| Git | 未 commit / 未 push（未获授权） |

## 2. 逐篇明细（列表顺序，共 10 条）

| # | 中文标题 | id / sha10 | published_at (+08:00) | type | tag_text | nodes | CJK | 入库结果 |
| - | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | 赛道之外：汉密尔顿第 400 场 F1 大奖赛首发 | `n_f1_20261108_fe848630b4` | 2026-11-08T17:10:34+08:00 | — | — | — | — | 远端已存在，跳过 POST |
| 2 | F1 传奇们的拍卖座驾（塞纳本田 NSX 超百万美元） | `n_f1_20261104_ab6b0ea22a` | 2026-11-04T01:28:02.793 | DRIVER | Senna / 盘点 | 46 | 2175 | POST 成功 + 复核通过 |
| 3 | 头盔、万寿菊与墨西哥传统：亡灵节在 F1 的印记 | `n_f1_20261101_ee59d0dbf6` | 2026-11-01T20:10:21.556 | PADDOCK | F1 / 亡灵节 | 46 | 2333 | POST 成功 + 复核通过 |
| 4 | 整蛊与围场淘气：F1 史上最伟大恶作剧的万圣节灵感 | `n_f1_20261030_bd6a6fa277` | 2026-10-30T20:57:17.630 | PADDOCK | F1 / 恶作剧盘点 | 69 | 2993 | POST 成功 + 复核通过 |
| 5 | 佩雷斯迎来第 300 场大奖赛：他对墨西哥为何重要 | `n_f1_20261030_eaaf4b5124` | 2026-10-30T17:18:53.970 | DRIVER | Perez / 里程碑 | 28 | 1290 | POST 成功 + 复核通过 |
| 6 | 十年之后：泰勒·斯威夫特在美国大奖赛的 2016 唯一演出 | `n_f1_20261022_beed0737bc` | 2026-10-23T02:20:45.550 | PADDOCK | Taylor Swift / 美国大奖赛 | 23 | 1133 | POST 成功 + 复核通过（id 日期偏差见 §4） |
| 7 | 从赛道到漫展：威廉姆斯如何加入漫威宇宙 | `n_f1_20261020_adc69a6ab0` | 2026-10-21T00:33:53.467 | PADDOCK | Williams / 跨界合作 | 41 | 1677 | POST 成功 + 复核通过（id 日期偏差见 §4） |
| 8 | 让「舒马赫 '94」重现银幕：Netflix 新纪录片幕后 | `n_f1_20261014_0d9184514e` | 2026-10-14T15:55:02.123 | DRIVER | Schumacher / 纪录片 | 73 | 3364 | POST 成功 + 复核通过 |
| 9 | “淡定”的蛇与 420 公里：博塔斯马来西亚→新加坡骑行 | `n_f1_20261008_d125ba7cbb` | 2026-10-08T21:04:41.586 | DRIVER | Bottas / 跨界骑行 | 26 | 990 | POST 成功 + 复核通过 |
| 10 | 独家｜“我几乎就住在行李箱里”：阿尔本谈巡回生活 | `n_f1_20261008_d15f80674c` | 2026-10-08T19:08:04.762 | DRIVER | Albon / 巡回生活 | 66 | 2625 | POST 成功 + 复核通过 |

- layout_code 全部为 STANDARD；cover_url 均为正文首图（media.formula1.com 原站地址，无 ibyteimg/本地路径占位）。
- CJK 数为 validate.py 对 text+nodes 的中文字符统计。

## 3. 校验与复核结果

1. **本地校验（validate.py）**：9 组双文件全部 OK，`BAD: 0 / 9`（id 正则、枚举、tag_text 单斜杠、nodes[0]=封面 img 且 src==cover_url、无代理/本地图源、无 U+FFFD、CJK≥200、拉丁长词占比、车手号配对均通过）。
2. **POST**：9 篇逐条提交至 `https://f1ink.normal-person.icu/api/v1/mp/news/ingest`，全部 HTTP 200 + `ok=true` + 响应 id 与请求一致（9/9）。
3. **GET 列表复核**（`/api/v1/mp/news` 分页）：9 个 id 全部命中；title、layout_code、type_code、tag_text、published_at（北京墙钟逐位一致）、tags（服务端规范化排序后与预期一致）零差异，`fail: 0 / 9`。
4. **GET 详情复核**（`/api/v1/mp/news/{id}`）：content.format_code=RICH_TEXT_NODES、nodes 数量与名称序列与本地逐节一致、封面节点一致、正文 text CJK 均≥200、source.url 一致，`fail: 0 / 9`。

新生成 9 篇 / 远端已存在 1 篇 / POST 成功 9 / 失败或待确认 0。

## 4. 偏差与备注（如实记录）

1. **id/文件名日期偏差（#6、#7）**：任务文档 §4.1 第 6 条规定文件名与 id 日期取 Asia/Shanghai 转换后的 YYYYMMDD。#6 泰勒·斯威夫特篇（北京 2026-10-23 02:20）与 #7 威廉姆斯×漫威篇（北京 2026-10-21 00:33）的发布时间在 UTC 与北京跨天，本地误取 UTC 日期，生成 `20261022_beed0737bc`、`20261020_adc69a6ab0`，并以此 id 入库（其余 7 篇两种日期同日，无影响）。因 API 无删除接口、改新 id 将造成同一文章双记录（文档禁止“制造重复新闻”），经用户确认**维持远端现状**，本地双文件与远端保持一致不改名。published_at 字段本身正确（带 +08:00 时区、北京墙钟准确）。
2. **原文疑点括注**：#9 Bottas 篇“Bahrain GP in Malaysia”表述与事实不符（巴林站不在马来西亚），译文保留原意并加括注说明，未擅改原文事实。
3. **图片 alt 截断**：#9 封面原站 alt 文本止于“poses for a”（源数据即截断），已在元信息如实注明。
4. **非正文内容处理**：各篇 video_slot 嵌入位、Instagram reel（#10 DdCS5tZKO_o 等）、F1 Store 促销模块均按规范以文字括注保留/剔除，不虚构视频内容；相关取舍在各 MD 元信息备注。
5. **俚语/谐音**：#9 “chill”译“淡定”、#10 “Al-bon Appétit”（谐音 bon appétit）、“cabin fever”等均按规范加括注保留原文风味。

## 5. 产物清单（工作区根目录，仅 f1 前缀双文件）

9 组 Markdown + ingest JSON（文件名=日期_f1_<Title_Slug>_<sha1_10>），对应 §2 各篇；状态文件 `formula1_lifestyle_culture_state.json`。临时 HTML、抽取与校验脚本均位于系统临时目录 `%TEMP%\f1lifestyle\`，未污染工作区。

## 6. 修复补记：children 缺 `"type":"text"` 字段（2026-11-10，用户指出）

### 6.1 缺陷确认
- 依据 `mp_news_content.md` §节点通用结构/文本节点/children 兼容输入：文本节点必须为 `{"type":"text","text":"..."}`，文档全部示例均带 `type`。
- 对照 main 分支既有入库文件（如 `20261108_f1_beyond-the-track-hamilton...fe848630b4.ingest.json` 及 autosport 系列）：children 一律带 `"type":"text"`。
- 本地 9 个 JSON 统计：child 键集合 `{('text',): 304, ('text','type'): 80}`，即 **304 处缺 `type`**（img attrs 为 src/alt/mode/style，与 main 一致，无需改）。

### 6.2 修复与重新入库
- 批量补齐 `{'type':'text', **child}`：7 个文件共修复 304 处（Bottas +24、Albon +60、Schumacher +67、Williams +38、TaylorSwift +22、Halloween +66、Perez +27；20261101/20261104 两篇原本已带 type，修复 0 处）。
- validate.py 重跑：`BAD: 0 / 9` 通过。
- 9 篇全量重新 POST `/api/v1/mp/news/ingest`（Upsert）：全部 HTTP 200 + `ok=true`（9/9）。

### 6.3 复核发现：详情接口返回旧缓存快照
逐节点严格比对（本地 vs `GET /api/v1/mp/news/{id}`）：
- **4 篇详情已反映新数据**（children 带 type，逐节点全等）：`d125ba7cbb`、`beed0737bc`、`ee59d0dbf6`、`ab6b0ea22a`。
- **5 篇详情仍是首次入库时的旧快照**（children 无 type）：`d15f80674c`、`0d9184514e`、`adc69a6ab0`、`bd6a6fa277`、`eaaf4b5124`；间隔 20s+ 复跑无变化。

排查证据（排除客户端与结构差异）：
1. 连打同一详情接口 10+ 次、变换请求头，响应稳定一致；`cf-cache-status: DYNAMIC`，非负载均衡节点差异。
2. 标记实验：向 `adc69a6ab0` 的 summary 追加【L】/【D】后 POST `ok=true`，**列表接口 `/api/v1/mp/news` 立即可见标记（读库，证明 Upsert 已生效）**，而详情接口始终不返回标记。
3. 9 篇本地结构（节点数、children 形态、body 大小）修复后完全同构，不存在"部分文章无法更新"的数据侧原因。

**结论**：数据库中新数据（含 type）已正确落库并经列表侧验证；5 篇详情接口差异属服务端详情缓存未按 Upsert 失效（旧快照将随缓存过期自然一致），本地 9 个 JSON 与 main 分支规范完全对齐，无需再改。如需 5 篇详情立即生效，需后端清除对应文章详情缓存。
