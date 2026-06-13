# 任务：爬取 Formula1.com Latest 列表并更新状态文件（覆盖为最新 10 条）

> 目标：从 `https://www.formula1.com/en/latest` 获取**最新 10 条**官方新闻文章 URL，并维护一个状态文件 `formula1_latest_news_state.json`。  
> 规则：状态文件中的 `urls` **不做逐条删除**，而是**每次执行后直接覆盖为最新 10 条**（去重后按列表页出现顺序）。

> 关系：本任务通常作为子任务，被 `TASK_formula1_latest_news_pipeline.md` 调用；也可单独执行用于“只更新状态快照”。

## TL;DR（只看这 3 行也能执行）

1. 先在任务目录执行 `git pull`
2. WebFetch 抓取 `https://www.formula1.com/en/latest`
3. 过滤并提取最新 10 个文章 URL（只保留 `https://www.formula1.com/en/latest/article/`）
4. 覆盖写入 `formula1_latest_news_state.json`：`source + fetched_at + count + urls`
5. 全部确认无误后执行 `git push`

## 输入

- `list_url`（固定）：`https://www.formula1.com/en/latest`
- `state_file`（固定）：本目录下 `formula1_latest_news_state.json`
- `limit`（固定）：10

## 输出

更新后的 `formula1_latest_news_state.json`，结构示例：

```json
{
  "source": "https://www.formula1.com/en/latest",
  "fetched_at": "2026-06-05T00:00:00+08:00",
  "count": 3,
  "urls": [
    "https://www.formula1.com/en/latest/article/...",
    "https://www.formula1.com/en/latest/article/...",
    "https://www.formula1.com/en/latest/article/..."
  ]
}
```

## 规则与约束

1. **只收集**符合 `https://www.formula1.com/en/latest/article/` 路径前缀的文章 URL。
2. **取最新 10 条**（按列表页出现顺序）。
3. 写回状态文件（覆盖写入）：
   - `source` 固定为 `list_url`
   - `fetched_at` 写入本次执行时间（RFC3339，带时区）
   - `urls` 直接写入“最新 10 条 URL”数组
   - `count = len(urls)`

## 最小执行步骤（参考实现思路）

1. 先执行 `git pull`。
2. 用 WebFetch/HTTP 抓取 `list_url`。
3. 从返回内容中提取候选链接，过滤、去重并截取前 10。
4. 将 `state_file` 覆盖写入为：`source + fetched_at + count + urls`。
5. 检查无误后执行 `git push`。

<details>
<summary>过滤规则细节（展开）</summary>

- 只保留以 `https://www.formula1.com/en/latest/article/` 开头的 URL
- 过滤非文章页（常见）：标签页 `/tags/`、视频直播页、`Gallery`、`Video` 等非正文文章类型

</details>
