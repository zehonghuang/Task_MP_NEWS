# 任务：Motorsport F1 News → 状态队列 → 生成入库 JSON → POST 入库（流水线）

> 目标：把两件事串起来做成一个可执行流程：  
> 1) 从 `https://www.motorsport.com/f1/news/` 抓取最新 10 条新闻 URL，并用状态文件保存“最新快照”；  
> 2) 对快照里的 URL，按 `TASK_mp_news_ingest_from_article_url.md` 的规范生成 `.md + .ingest.json` 并 POST 入库；  
>    **翻译必须逐字/逐句忠实翻译（不是总结）**：不得省略段落、不得只翻要点、不得用概述替代正文；  
>    且**不修改状态文件中的 urls（不删除）**。

## TL;DR（推荐执行顺序）

1. 执行 `TASK_motorsport_f1_news_state_toggle.md`：刷新 `motorsport_f1_news_state.json`（覆盖为最新 10 条）
2. 读取 `motorsport_f1_news_state.json` 的 `urls`
3. 对每个 `article_url` 执行 `TASK_mp_news_ingest_from_article_url.md`（生成文件 + POST）

## 按步骤逐渐式阅读（推荐）

> 原则：先跑通流程，再在需要产出特定字段/结构时读取对应规范，避免一上来把所有文档读完。

### 第 1 步：刷新“最新快照”

仅需阅读：

1. `TASK_motorsport_f1_news_state_toggle.md`

### 第 2 步：逐篇处理并入库（对 state.urls 的每个 article_url）

按阶段阅读：

1. **准备执行单篇任务前**：阅读 `TASK_mp_news_ingest_from_article_url.md`（了解整体流程与产物命名）
2. **准备组织 content.nodes 前**：阅读 `mp_news_content.md`
3. **准备生成入库 JSON/POST 前**：阅读 `mp_news_ingest_api.md`

## 固定输入

- `list_url`：`https://www.motorsport.com/f1/news/`
- `state_file`：本目录 `motorsport_f1_news_state.json`
- `limit`：10
- `ingest_endpoint`：`https://winpc-f1.normal-person.icu/api/v1/mp/news/ingest`
- `token`：无

## 状态文件结构

```json
{
  "source": "https://www.motorsport.com/f1/news/",
  "fetched_at": "2026-06-05T00:00:00+08:00",
  "count": 3,
  "urls": ["https://www.motorsport.com/f1/news/..."]
}
```

## 第 1 部分：更新“待处理队列”（状态文件）

直接执行子任务：`TASK_motorsport_f1_news_state_toggle.md`  
（它负责：抓取 `list_url` → 提取最新 10 条 → 覆盖写入 `state_file`。）

## 第 2 部分：消费队列并入库（严格复用既有 TASK 规范）

对 `state.urls` 中的每个 `article_url` 逐条执行：

1. **执行 `TASK_mp_news_ingest_from_article_url.md`** 的完整流程：  
   抓取 →（必要时镜像）→ 图片提取 → 全文中文翻译 → 生成入库 JSON → POST 到 `ingest_endpoint`（无 token）。
   - 其中在生成 `tags` 时：若包含任何车手 slug，必须先查 `mp/session-results?latest=1` 获取正确车号，严禁猜测。
   - 其中在生成 `published_at` 时：若文章页存在 `class="msnt-author-toolbar"` 的 `<div>`，优先从该处提取并解析时间（详见 `TASK_mp_news_ingest_from_article_url_supplement.md`）。
2. 去重/避免重复处理（推荐实现）：  
   - 若本目录已存在某个 `*.ingest.json`，其 `source.url == article_url`，则视为已处理，可跳过（避免重复生成和重复 POST）。  
3. 若 POST 失败：  
   - 不修改 `state_file`（状态文件只做“最新快照”用途）  
   - 记录失败原因（例如抓取失败、POST 失败等）

<details>
<summary>实现提示：如何“跳过已处理”的文章？（展开）</summary>

- 以本目录已有的 `*.ingest.json` 为准：读取其中 `source.url`，与 `motorsport_f1_news_state.json` 的 `urls` 做集合对比；
- 已存在则跳过：避免重复翻译、重复 POST。

</details>

## 输出（写入本目录）

- 队列状态：`motorsport_f1_news_state.json`
- 每篇文章两份文件（命名规则以 `TASK_mp_news_ingest_from_article_url.md` 为准）：
  - `YYYYMMDD_autosport_<Title_Slug>_<sha1_10>.md`
  - `YYYYMMDD_autosport_<Title_Slug>_<sha1_10>.ingest.json`
