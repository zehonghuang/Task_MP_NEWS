# TASK 索引：Formula1.com Lifestyle & Culture 入库工作流

## 当前分支入口

本分支 `feature/f1-lifestyle-culture` 专用于 Formula1.com 的 Lifestyle & Culture 栏目。

**推荐执行： [TASK_formula1_lifestyle_culture_pipeline.md](TASK_formula1_lifestyle_culture_pipeline.md)**

- 全流程：栏目最新 10 条 → 独立状态快照 → 逐篇详情抽取 → 忠实全文中译 → Markdown + ingest JSON → POST 并核验。
- 只刷新列表：执行该任务第 3 节，不翻译、不 POST。
- 只处理单篇：执行该任务第 4–7 节；是否 POST 以用户要求为准。
- 只制定/修改任务：不自动执行文章流水线。

## 固定配置

- 栏目：https://www.formula1.com/en/latest/tags/lifestyle-culture.4R2e2KAaQF8RBPPy7GeeL7
- 状态：`formula1_lifestyle_culture_state.json`（首次执行时生成）
- 产物：`YYYYMMDD_f1_<Title_Slug>_<sha1_10>.md` 与同名 `.ingest.json`
- 来源：Formula1.com；id：`n_f1_YYYYMMDD_<sha1_10>`
- 接口：https://f1ink.normal-person.icu/api/v1/mp/news/ingest

## 必须遵守

1. 全文翻译必须逐句忠实覆盖导语、各段、引语、数字、小标题与图注，禁止摘要代替正文。
2. 读取 [mp_news_content.md](mp_news_content.md) 与 [mp_news_ingest_api.md](mp_news_ingest_api.md) 校验结构及枚举。
3. 详情发布时间按 Formula1.com 结构提取，不套用 Motorsport 的 msnt-author-toolbar 规则；源名和文件前缀不得写成 Autosport。
4. 本地旧文章产物已清空，但远端数据库未清空；去重必须考虑远端已有记录。
5. 开始执行前检查分支、工作区和 upstream；有 upstream 时先 `git pull --ff-only`，无 upstream 时报告，不误拉 main。仅在用户授权提交/推送且任务全部完成核验后操作当前分支，不向 main 自动推送。
6. 用户既有修改、输入 HTML、状态配置、历史脚本均不得擅自删除或混入提交。

## 保留的旧任务（历史参考，不是本分支执行入口）

- [TASK_motorsport_f1_news_pipeline.md](TASK_motorsport_f1_news_pipeline.md)：原 Motorsport 全流程。
- [TASK_motorsport_f1_news_state_toggle.md](TASK_motorsport_f1_news_state_toggle.md)：原 Motorsport 最新 10 条快照。
- [TASK_mp_news_ingest_from_article_url.md](TASK_mp_news_ingest_from_article_url.md)：原单篇入库流程，包含 Autosport 硬编码字段。
- [TASK_mp_news_ingest_from_article_url_supplement.md](TASK_mp_news_ingest_from_article_url_supplement.md)：原站发布时间补充规则。

这些文档保留用于追溯，不与新的 Formula1.com 任务混用。旧 `motorsport_f1_news_state.json` 及其脚本不作为新栏目状态或执行程序。
