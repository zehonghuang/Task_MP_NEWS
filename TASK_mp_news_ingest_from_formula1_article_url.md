# 任务：从 Formula1.com 文章地址生成 mp_news 入库 JSON 并提交

> 用途：给我一个 `https://www.formula1.com/en/latest/article/...` 文章 URL，我会按 `mp_news_content.md` + `mp_news_ingest_api.md` 的约定，完成：抓取 → **全文中文翻译** → 生成入库 JSON →（可选）POST 到入库接口。

## 必备参考文档（两份都必须读取并严格遵守）

1. `mp_news_content.md`：正文 `content` 的字段与 `nodes` 结构约定  
2. `mp_news_ingest_api.md`：`POST /api/v1/mp/news/ingest` 入库字段、枚举与约束（尤其是 `tag_text/tags` 的语义生成规则）

> 说明：执行本任务时，必须先读取并遵守以上两份文档；若字段/约束冲突，以文档为准并提示差异。

## 输入

- `article_url`（必填）：`https://www.formula1.com/en/latest/article/...`
- `ingest_endpoint`（可选，默认）：`https://winpc-f1.normal-person.icu/api/v1/mp/news/ingest`
- `token`（可选）：若接口需要鉴权，则作为 query 参数 `?token=...`

## 输出（写入本目录）

1. 翻译稿 Markdown：  
   - 文件名：`YYYYMMDD_formula1_<Title_Slug>_<sha1_10>.md`
2. 入库 JSON（可直接 POST）：  
   - 文件名：`YYYYMMDD_formula1_<Title_Slug>_<sha1_10>.ingest.json`

> 其中 `<sha1_10>` = 对 `article_url` 做 SHA1 后取前 10 位（用于稳定去重）。

## 流程（必须按顺序执行）

### 1) 抓取文章内容

1. 优先抓取 `article_url` 正文（标题、发布时间、正文段落、头图/正文图）。
2. 若页面存在明确的发布时间/更新时间文本，优先解析为 `published_at`。
3. 若正文抓取失败，必须说明原因；若是临时页面异常，可重试一次。

### 2) 提取图片

> 目标：尽量“看到什么图就收什么图”，避免仅靠静态 HTML 解析漏掉懒加载图片。

- `cover_url`：
  - 取“正文出现的第一张图”（若没有则空串）
- `content.nodes`：
  - 在正文开头插入第一张图的 `img` 节点（如果存在）
  - 之后按正文出现顺序，继续插入其余图片的 `img` 节点（每张图一个节点）
  - `img.attrs` 字段约定：
    - `src`：图片 URL
    - `mode`：`widthFix`
    - `style`：`width:100%;display:block;`
    - `alt`：尽量给出简短中文描述；若无法判断可省略或置空

### 3) 全文翻译为中文

- 要求：**完整翻译**（包含引号内原文引述、数据/比例/记录等）
- 要求：**逐字/逐句忠实翻译**，不是摘要/总结/改写
- 风格：新闻中文写法，专有名词保持一致（车手/车队/赛道/机构）

### 4) 生成入库 JSON（严格按 ingest API）

#### 字段要求（高优先级校验点）

- `id`：`n_formula1_YYYYMMDD_<sha1_10>`
- `layout_code`：默认 `STANDARD`（除非明确属于突发/头条/专题/简报）
- `type_code`：按语义选（常见：车手/车队消息 → `PADDOCK`；规则讨论 → `REGULATION`；技术 → `TECH` 等）
- `tag_text`：必须是 `<主实体> / <文章属性>`（只允许一个 `/`）
- `tags`：非空数组、原子词；若包含车手 slug，**必须带车号**（车号必须通过 `https://winpc-f1.normal-person.icu/api/v1/mp/session-results?latest=1` 查询得到，严禁猜测）
- `published_at`：RFC3339/RFC3339Nano（能确定当地时区就带时区；否则允许 `Z`）
- `source.name`：`Formula1.com`
- `source.url`：原始 `article_url`
- `content.format_code`：`RICH_TEXT_NODES`
- `content.text`：中文纯文本（自然段用空行分隔）
- `content.nodes`：`p` 段落 +（可选）`img` 等，结构按 `mp_news_content.md`

### 5) 保存文件

- 写入本目录：翻译 `.md` + 入库 `.ingest.json`

### 6) POST 入库（如果用户要求）

- POST 到：`ingest_endpoint`（如有 token：`ingest_endpoint?token=...`）
- 请求体：上一步生成的 JSON（平铺结构，无额外外层包裹）
- 成功条件：HTTP 200 且返回 `{"ok":true,"id":"..."}`  

## 失败与回退策略

- 若正文抓取失败：必须说明原因
- 若发布时间不可得：可用当天 `00:00:00+08:00` 兜底，但必须在摘要或备注中说明不确定
- 若图片抓取失败（例如无正文图）：`cover_url` 置空，且不要生成任何 `img` 节点

## 你给我调用时的最简输入格式（示例）

```
文章地址：
https://www.formula1.com/en/latest/article/xxx/12345678
需要入库：是
接口：
https://winpc-f1.normal-person.icu/api/v1/mp/news/ingest
token：无
```
