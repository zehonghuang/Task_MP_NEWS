# 任务补充：published_at 抓取规则（补充到 TASK_mp_news_ingest_from_article_url.md）

> 背景：`c:\F1InkDashboard\mp_news_ingest\extracted\autosport\TASK_mp_news_ingest_from_article_url.md` 为权威任务文档，本补充文件用于承载聊天中新增的规则，避免直接改动权威文档结构。

## published_at 抓取要求（新增）

在执行“抓取文章内容”阶段，若文章页面存在：

- `class="msnt-author-toolbar"` 的 `<div>`

则应优先从该 `<div>` 中提取发布时间/编辑时间（例如 “Edited: Jun 4, 2026, 2:20 PM” 等），并据此解析生成入库字段：

- `published_at`：RFC3339/RFC3339Nano（若页面未提供时区，可按文档兜底策略处理）

若上述 `<div>` 不存在或不可用，再使用其他可获得的时间信息或兜底策略。

