# Wiki Schema

## Domain
本仓库维护一个面向 Obsidian 的 LLM Wiki / 知识图谱，当前原始资料主要是 GitHub 开源项目、AI 工具、知识管理与自动化工具的项目卡片和分析材料。

## Repository Layout
- `raw/`: immutable source material; do not modify existing raw files.
- `wiki/`: agent-maintained knowledge layer (`sources/`, `entities/`, `concepts/`, `comparisons/`, `overview/`, `queries/`).
- `wiki/index.md`: active catalog for this repository.
- `wiki/log.md`: active append-only operation log.
- `TheSchema.md`: original Chinese schema/operation guide shipped with the repository.

## Conventions
- Prefer Chinese, readable filenames for `wiki/` pages; keep links stable.
- Every maintained wiki page should include YAML frontmatter with `type`, `tags`, `summary`, `sources`, and `updated`.
- Use Obsidian `[[wikilinks]]` for cross-references.
- Raw files are read-only; corrections and synthesis belong in `wiki/`.
- Every write operation updates `wiki/index.md` and/or `wiki/log.md` as appropriate.

## Page Types
- `source`: source summaries under `wiki/sources/`
- `entity`: projects, people, organizations under `wiki/entities/`
- `concept`: reusable concepts/methods under `wiki/concepts/`
- `comparison`: side-by-side analyses under `wiki/comparisons/`
- `overview`: synthesis pages under `wiki/overview/`
- `query`: saved answers under `wiki/queries/`

## Current Tag Taxonomy
- `wiki`, `knowledge-management`, `obsidian`, `llm`, `agent`, `automation`, `github`, `open-source`, `ai-tool`, `security`, `diagramming`, `video`, `publishing`, `kindle`, `desktop`, `mapping`, `curated-list`, `query`, `overview`

## Query Policy
For `action=query`, orient from `SCHEMA.md`, `index.md`, and recent logs first. If `save=false`, do not create a query page, but log the query execution.
