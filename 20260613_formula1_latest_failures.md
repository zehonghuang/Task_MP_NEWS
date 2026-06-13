# Formula1 Latest 本次失败记录

- 执行时间：2026-06-13
- 来源列表：`https://www.formula1.com/en/latest`

## 未完整处理的 URL

### 1. PRACTICE DEBRIEF: Are McLaren really back in the fight against Mercedes at the Barcelona-Catalunya Grand Prix?

- URL：`https://www.formula1.com/en/latest/article/are-mclaren-really-back-in-the-fight-against-mercedes-in-barcelona.6JiIZpRB9js3S1NJ1IuhfE`
- 原因：页面 `isAccessibleForFree=false`，服务端 HTML 仅暴露导语和一个问答小节，无法取得全文正文。
- 处理结论：未生成 `.md` 与 `.ingest.json`，避免用不完整内容冒充全文翻译并入库。

### 2. Formula 1 2026 Barcelona-Catalunya Grand Prix best Qualifying bets available in F1 betting markets

- URL：`https://www.formula1.com/en/latest/article/best-qualifying-bets-available-for-the-barcelona-catalunya-grand-prix.1pxhs2b2WbufYr6dngNK4r`
- 原因：页面可访问，但当前返回 HTML 中无可抽取的正文容器、正文段落或结构化正文内容。
- 处理结论：未生成 `.md` 与 `.ingest.json`，等待后续若页面结构变化或可获得正文后再补跑。
