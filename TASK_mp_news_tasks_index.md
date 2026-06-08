# TASK 索引：Motorsport F1 News 入库工作流

> 说明：本目录内有多个 `TASK_*.md`。为避免重复和歧义，请优先从本索引选择“入口任务”执行。

## TL;DR（先看这个）

1. 要“跑全流程”→ 执行 `TASK_motorsport_f1_news_pipeline.md`
2. 只想刷新“最新 10 条 URL 快照”→ 执行 `TASK_motorsport_f1_news_state_toggle.md`
3. 只想手动入库某一篇文章 → 执行 `TASK_mp_news_ingest_from_article_url.md`

> 🚨 全局硬性要求（必须遵守）：凡出现“翻译/全文中文翻译”，一律指 **逐字/逐句忠实翻译**（不是摘要/总结/改写）。  
> - 必须覆盖全文：引述/数字/比例/记录/括号内容都要翻译  
> - 禁止偷懒：不得省略段落、不得只翻“要点”、不得用概述替代正文
>
> 🚨 Git 执行要求（必须遵守）：
> - 开始整个任务前，必须先在对应目录执行一次 `git pull`
> - 只有当整个任务已经完全执行完、文件与结果都确认无误后，才执行 `git push`
> - 禁止未完成就提前 `git push`

## 推荐入口（优先使用）

### 1) `TASK_motorsport_f1_news_pipeline.md`（推荐｜全流程）

用途：  
从 `https://www.motorsport.com/f1/news/` 抓取最新 10 条 → 覆盖写入状态文件 `motorsport_f1_news_state.json`（最新快照）→ 对快照里的 URL 逐条生成 `.md + .ingest.json` → POST 入库（状态文件不删除 URL）。

适用场景：日常跑批/持续更新。

## 子任务（被入口任务复用，也可单独执行）

### 2) `TASK_motorsport_f1_news_state_toggle.md`（只维护快照）

用途：只做“抓取最新 10 条 URL 并覆盖写入状态文件（最新快照）”，不抓取文章正文、不生成入库文件、不 POST。

适用场景：你只想更新状态快照，稍后再单独入库。

### 3) `TASK_mp_news_ingest_from_article_url.md`（单篇文章入库）

用途：给定一个 `article_url`，严格按 `mp_news_content.md` + `mp_news_ingest_api.md` 的约定：抓取 →（必要时找镜像）→ 图片提取 → 全文中文翻译 → 生成 `.md + .ingest.json` →（可选）POST 入库。

> 注意：此处“翻译”指 **逐字/逐句忠实翻译**，不是摘要/总结/改写。
> 补充规则：`published_at` 的抓取优先级见 `TASK_mp_news_ingest_from_article_url_supplement.md`。

适用场景：手动补一篇/重跑某一篇/调试某篇文章的抽取与入库字段。

## 关键产物（文件）

- 状态队列：`motorsport_f1_news_state.json`
- 文章翻译稿：`YYYYMMDD_autosport_<Title_Slug>_<sha1_10>.md`
- 入库 JSON：`YYYYMMDD_autosport_<Title_Slug>_<sha1_10>.ingest.json`

<details>
<summary>为什么需要多个 TASK？（展开）</summary>

- `state_toggle` 是“轻量抓取列表 + 写状态文件”，方便快速刷新数据源；
- `ingest_from_article_url` 是“重任务”：正文抓取、图片提取、翻译、生成入库 JSON、POST；
- `pipeline` 把两者串起来，作为日常入口。

</details>

<details>
<summary>推荐阅读顺序（逐渐式披露｜展开）</summary>

1. 只想“知道从哪开始”→ 先读本索引（本文件）
2. 要跑全流程 → 读 `TASK_motorsport_f1_news_pipeline.md` 的 TL;DR
3. 真正要刷新列表快照时 → 再读 `TASK_motorsport_f1_news_state_toggle.md`
4. 真正要处理单篇入库时 → 再读 `TASK_mp_news_ingest_from_article_url.md`
5. 只有当需要生成字段/结构时才读规范：
   - 组织 `content.nodes` 才读 `mp_news_content.md`
   - 生成/POST 入库 JSON 才读 `mp_news_ingest_api.md`

</details>
