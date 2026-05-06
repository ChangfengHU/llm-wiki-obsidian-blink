---
created: 2026-04-08T14:41
updated: 2026-05-06T20:40
type: guide
tags:
  - schema
  - wiki
  - knowledge-management
  - l1-l2-l3
---

## 0. 目标与边界

> [!info] 核心目标
> 维护 `wiki/` 目录，将其打造为可复利、可追溯、可审计的知识层。

- 目标：你负责维护本仓库中的 `wiki/` 目录。
- 边界：
  - `raw/` 是唯一事实来源，**只读不改**。
  - 仅在 `wiki/`、`index.md`、`log.md` 内进行知识层维护。
  - 非必要不改其它目录；若需改动，先在运行日志说明原因。

---

## 1. 三层模型（强约束）

### L1 Fact Layer（事实层）
- 仅允许写入可由 `raw/**/*.md` 直接支持的事实。
- 每条关键事实必须可追溯到 `sources`（页级）或段落出处（建议）。
- 禁止把推测写成事实。

### L2 Inference Layer（推断层）
- 允许基于多个 L1 事实做归纳/推断。
- 必须显式标注：
  - `confidence: high|medium|low`
  - `reasoning: ...`（简短推理依据）
  - `sources: [...]`（支撑来源）

### L3 Question Layer（问题层）
- 记录未决问题、假设、证据缺口。
- 作用是指导下一轮 raw 采集，不作为既定事实。

> 规则：L1 可直接入库；L2/L3 必须标注，不得伪装为 L1。

---

## 2. 目录结构约定

### 原始资料层
- `raw/`：原始资料（PDF、网页 Markdown、图片等），**只读**。

### Wiki 维护层

| 目录 | 用途 |
| --- | --- |
| `wiki/sources/` | 单个来源摘要页 |
| `wiki/entities/` | 人物、书籍、项目等实体页 |
| `wiki/concepts/` | 方法、理论、模型等概念页 |
| `wiki/comparisons/` | 比较分析页 |
| `wiki/overview/` | 总览、综合页 |
| `wiki/queries/` | 重要问答沉淀（可选） |

### 根目录文件
- `index.md`、`log.md`（全局索引/日志）
- `wiki/index.md`、`wiki/log.md`（兼容旧结构时同步维护）

---

## 3. 页面格式（frontmatter）

所有 wiki 页面使用 Markdown，顶部 frontmatter：

```yaml
---
type: source|entity|concept|comparison|overview|query
tags: [tag1, tag2]
summary: 一句话说明核心内容
sources: [raw/xxx.md]
created: 2026-05-06
updated: 2026-05-06
layer: L1|L2|L3
confidence: high|medium|low
reasoning: 推理依据（L2/L3 必填，L1 可省略）
---
```

强约束：
- `type/tags/summary/sources/updated/layer` 必填。
- `layer=L2|L3` 时，`confidence` 与 `reasoning` 必填。
- `sources` 必须指向 `raw/` 文件。

---

## 4. 页面类型

### 4.1 Source Summary（来源摘要页）
路径：`wiki/sources/xxx.md`
- 来源信息（标题、作者、时间、链接）
- 核心要点（3–7 条）
- 关联实体/概念链接

### 4.2 Entity Page（实体页）
路径：`wiki/entities/*.md`
- 基本信息
- 关键行为/状态
- 相关事件链接
- 证据来源

### 4.3 Concept Page（概念页）
路径：`wiki/concepts/*.md`
- 定义
- 应用场景/步骤
- 在本库中的例子
- 关联实体/概念

### 4.4 Comparison Page（比较页）
路径：`wiki/comparisons/*.md`
- 对象简介
- 相同点/不同点
- 结论与适用条件

### 4.5 Overview / Query
路径：`wiki/overview/*.md` 或 `wiki/queries/*.md`
- 结论摘要
- 支撑证据
- 未决问题

---

## 5. 工作流：Ingest / Incremental / Full / Query / Lint

### 5.1 Ingest（导入）
1. 先读 `TheSchema.md`、`index.md`、`log.md`（最近记录）。
2. 从 `raw` 提炼要点，更新 `wiki/sources`。
3. 更新关联实体/概念/比较/总览页面。
4. 更新索引与日志。

### 5.2 Incremental Build（增量）
1. 用 `before..sha` 或 `HEAD~1..HEAD` 找变更。
2. 仅保留 `raw/**/*.md`。
3. 若 raw 无变化：`skipped:no_raw_changes`，停止写 wiki、停止 commit/push。
4. 若有变化：仅更新受影响页面并记日志。

### 5.3 Full Build（全量）
1. 扫描全部 `raw/**/*.md`。
2. 重建/修复 sources/entities/concepts/comparisons/overview 的链接与索引。
3. 清理孤立项与明显重复项（先记录再改）。

### 5.4 Query（问答）
- 先查 `index` 与相关页，再综合回答。
- 有长期价值的问题可沉淀到 `wiki/queries/`。

### 5.5 Lint（健康检查）
- 检查：坏链、孤立页、缺 frontmatter、层级标注缺失、来源不可追溯、明显冲突。
- 输出“建议清单”优先，不做大范围自动改写。

---

## 6. 质量门禁（必过）

1. 可追溯性：关键结论必须能回溯到 `raw`。
2. 层级一致性：L1/L2/L3 标签正确，L2/L3 有 confidence+reasoning。
3. 链接健康：禁止新增明显坏链；坏链需在日志列出并计划修复。
4. Frontmatter 完整：缺字段页面计入 lint 问题。
5. 日志完整：每次执行必须有 run log，包含开始/结束、改动文件、git 结果、错误信息。

---

## 7. 命名与风格

- 页面命名：优先“中文_主题”或稳定 slug，避免频繁改名。
- 内链：使用 `[[wikilink]]`。
- 不确定时：先给修改提案，再执行。
- 大改动前先说明范围（影响文件数、类型、风险）。

---

## 8. 工具约定

- 关系查询、标签检索、frontmatter 提取：优先 Obsidian/结构化检索方式。
- Git 自动化运行必须遵循：先同步、后处理、再提交、最后推送。
- 如遇冲突或无法快进同步（ff-only failed），应中止并记录，不强行提交。
