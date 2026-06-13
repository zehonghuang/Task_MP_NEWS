# 任务：mp_news 总入口（每次必须先选择数据源）

> 这是所有 `mp_news` 相关任务的**唯一推荐入口**。  
> **每次执行前，必须先明确选择数据源**，只能二选一：
>
> 1. `Motorsport`
> 2. `Formula 1 官网`

## 硬性要求（必须遵守）

### 第一步：必须先选数据源

开始执行前，必须先明确回答：

`本次要处理哪个来源？`

可选值只有：

- `Motorsport`
- `Formula 1 官网`

**禁止跳过这一步。**  
**禁止在未选来源时直接开始抓取、翻译、生成 JSON 或 POST。**

### 第二步：按来源进入对应流水线

如果选择：

- `Motorsport`  
  则执行：`TASK_motorsport_f1_news_pipeline.md`

- `Formula 1 官网`  
  则执行：`TASK_formula1_latest_news_pipeline.md`

## 全局硬性要求

- 凡出现“翻译/全文中文翻译”，均指**逐字/逐句忠实翻译**，不是摘要/总结/改写
- 必须覆盖全文：引述/数字/比例/记录/括号内容都要翻译
- 禁止省略段落、禁止只翻要点、禁止用概述替代正文
- 开始整个任务前，必须先执行 `git pull`
- 只有当整个任务已经完全执行完、文件与结果都确认无误后，才执行 `git push`
- 禁止未完成就提前 `git push`

## 路由表

| 你选择的来源 | 对应入口任务 |
|---|---|
| `Motorsport` | `TASK_motorsport_f1_news_pipeline.md` |
| `Formula 1 官网` | `TASK_formula1_latest_news_pipeline.md` |

## 执行说明

如果用户没有明确说来源，必须先让用户选择：

- `Motorsport`
- `Formula 1 官网`

只有选完，才能继续进入对应 TASK。
