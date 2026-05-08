# Wiki Log

> Chronological record of wiki actions. Append-only.
> Format: `## [YYYY-MM-DD] action | subject`

## [2026-05-03] create | Initialized llm-wiki automation metadata
- Created root `SCHEMA.md`, root `index.md`, and repaired `wiki/index.md` / `wiki/log.md` because canonical `SCHEMA.md`, `index.md`, and `log.md` were missing or empty.
- Preserved existing `TheSchema.md` as the repository's original Chinese schema.

## [2026-05-03] query | 测试查询：请简单说明这个 wiki 当前主要内容是什么？
- save: false
- Filed query page: no
- Answer summarized from README, TheSchema, and raw project source list.
## [2026-05-03] update | full_build knowledge graph repair
- run_id: 123
- Scanned Markdown files: 20 total; raw sources: 13.
- Initialized/repaired structure: wiki/sources, wiki/entities, wiki/concepts, wiki/comparisons, wiki/overview, wiki/queries, logs/webhook-runs.
- Generated/updated index and graph pages: index.md, wiki/index.md, wiki/overview/知识图谱关系.md, wiki/overview/开源ai工具知识图谱总览.md.
- Created files: 43; updated files: 2.

## [2026-05-06] update | incremental_build run_id=incremental_124
- Synced `origin/main` with protective stash workflow (`stash -> fetch/checkout/pull --ff-only -> stash pop`).
- Incremental diff base: `a430e1d..4a8f3f7`.
- Created/updated/deleted affected pages in `wiki/sources/` and `wiki/entities/`.
- Rebuilt `Sources`/`Entities` sections in `index.md` and `wiki/index.md`.
- Detailed run log: `logs/webhook-runs/incremental_124.md`.

## [2026-05-06] query | health check only, reply short
- save: false
- Filed query page: no
- Health check summary: core schema/index/log present; wiki layer has 53 markdown pages; detected 20 potential broken wikilinks; `wiki/queries/` directory missing.
- Detailed run log: `logs/webhook-runs/callback-check-1.md`.

## [2026-05-06] update | incremental_build run_id=gh-25445428103-1
- Synced `origin/main` with protective stash workflow (`stash -> fetch/checkout/pull --ff-only -> stash pop`).
- Incremental diff base: `HEAD~1..HEAD`.
- Changed markdown files: raw/webhook-action-test-20260506-154023.md.
- Updated Sources index and affected wiki source pages.
- Detailed run log: `logs/webhook-runs/gh-25445428103-1.md`.

## [2026-05-06] update | incremental_build run_id=gh-25446071114-1
- Synced `origin/main` with protective stash workflow (`stash -> fetch/checkout/pull --ff-only -> stash pop`).
- Incremental diff base: `f3b89b105c1010150816151da245019338355a22..6cf4de94dec01be1f51100e92e1d0c886248a35e`.
- Changed markdown files: raw/recursion-guard-test-20260506-155321.md.
- Updated Sources/Entities pages and index navigation.
- Detailed run log: `logs/webhook-runs/gh-25446071114-1.md`.

## [2026-05-06] update | incremental_build run_id=gh-25457105761-1
- Synced `origin/main` with protective stash workflow (`stash -> fetch/checkout/pull --ff-only -> stash pop`).
- Incremental diff base: `HEAD~1..HEAD` (fallback after empty `..2ce8fd1e548dc90546c01ac04316b8505e420735`).
- Changed markdown files: raw/awesome-selfhosted.md.
- Created `wiki/sources/awesome-selfhosted.md` and `wiki/entities/awesome-selfhosted.md`; updated indexes and relation overview.
- Detailed run log: `logs/webhook-runs/gh-25457105761-1.md`.

## [2026-05-06] update | incremental_build run_id=gh-25457927233-1
- Synced `origin/main` with protective stash workflow (`stash -> fetch/checkout/pull --ff-only -> stash pop`).
- Incremental diff base: `48ce2c532d10d40d820764d74c0c2253d59a9ec9..a236edffb952eb8aca772b46cfd8e5489d9f10f2`.
- Changed markdown files: raw/awesome-go.md.
- Created `wiki/sources/awesome-go.md` and `wiki/entities/awesome-go.md`; updated `index.md`, `wiki/index.md`, `wiki/overview/知识图谱关系.md`.
- Detailed run log: `logs/webhook-runs/gh-25457927233-1.md`.

## [2026-05-06] update | incremental_build run_id=gh-25458462144-1
- Synced `origin/main` with protective stash workflow (`stash -> fetch/checkout/pull --ff-only -> stash pop`).
- Incremental diff base: `aea1b15af69c4957b186d61570577a3b3af562fe..89b6d5d10c3be862de5729a34ae4c11993fa991c`.
- Changed markdown files: raw/HelloGitHub.md.
- Created `wiki/sources/hellogithub.md` and `wiki/entities/hellogithub.md`; updated `index.md`, `wiki/index.md`, `wiki/overview/知识图谱关系.md`.
- Detailed run log: `logs/webhook-runs/gh-25458462144-1.md`.

## [2026-05-06] update | incremental_build run_id=gh-25459442379-1
- Synced `origin/main` with protective stash workflow (`stash -> fetch/checkout/pull --ff-only -> stash pop`).
- Incremental diff base: `1e2df1b9a811af0bcbf972028c5df8ac633d59b7..3be261f35f2dc218cc23be36c0abeb67ad6d255b`.
- Changed markdown files: raw/papers-we-love.md.
- Created `wiki/sources/papers-we-love.md` and `wiki/entities/papers-we-love.md`; updated `index.md`, `wiki/index.md`, `wiki/overview/知识图谱关系.md`.
- Detailed run log: `logs/webhook-runs/gh-25459442379-1.md`.

## [2026-05-06] update | full_build run_id=manual-full-20260506-2041
- Full scan markdown files: 140 total; raw sources: 28.
- Initialized/repaired structure: wiki/sources, wiki/entities, wiki/concepts, wiki/comparisons, wiki/overview, wiki/queries, logs/webhook-runs.
- Generated/updated index and graph pages: index.md, wiki/index.md, wiki/overview/知识图谱关系.md, wiki/overview/开源ai工具知识图谱总览.md.
- Detailed run log: logs/webhook-runs/manual-full-20260506-2041.md.

## [2026-05-07] update | incremental_build run_id=gh-25469675700-1
- Synced `origin/main` with protective stash workflow (`stash -> fetch/checkout/pull --ff-only -> stash pop`).
- Incremental diff base: `7c82da3c24dd88e22a271a9b8f18717ee846f07e..661739b43565aa1573dede88ccfc4efb28df74bd`.
- Changed markdown files under `raw/**/*.md`: raw/zed.md.
- Created `wiki/sources/zed.md` and `wiki/entities/zed.md`; updated `index.md`, `wiki/index.md`, `wiki/log.md`, `wiki/overview/知识图谱关系.md`.
- Detailed run log: `logs/webhook-runs/gh-25469675700-1.md`.

## [2026-05-07] update | incremental_build run_id=gh-25469665279-1
- Synced `origin/main` with protective stash workflow (`stash -> fetch/checkout/pull --ff-only -> stash pop`).
- Incremental diff base: `f90d7e57ca0e6f39abb5e66e607b01ed836ad29c..7c82da3c24dd88e22a271a9b8f18717ee846f07e`.
- Changed markdown files under `raw/**/*.md`: raw/ruflo.md.
- Updated affected `wiki/sources/`, `wiki/entities/`, `wiki/concepts/`, `wiki/overview/知识图谱关系.md`, and indexes.
- Detailed run log: `logs/webhook-runs/gh-25469665279-1.md`.

## [2026-05-07] update | incremental_build run_id=gh-25496112884-1
- Synced `origin/main` with protective stash workflow (`stash -> fetch/checkout/pull --ff-only -> stash pop`).
- Incremental diff base: `e5053506f51353bbbfad0bf4eeaf6e528e7f7947..e0352f7b3e492041c9e5d900bcf09cff6aa0abbe`.
- Changed markdown files under `raw/**/*.md`: raw/raphael-publish.md.
- Updated affected `wiki/sources/`, `wiki/entities/`, `wiki/concepts/`, `wiki/overview/知识图谱关系.md`.
- Detailed run log: `logs/webhook-runs/gh-25496112884-1.md`.

## [2026-05-07] update | incremental_build run_id=gh-25496127090-1
- Incremental diff base: `e0352f7b3e492041c9e5d900bcf09cff6aa0abbe..9687a8f29d7df8d8c7f9d31ae0d1b95a7c4fe831`.
- Changed markdown files under `raw/**/*.md`: raw/raphael-publish.md.
- Updated affected `wiki/sources/raphael-publish.md`, `wiki/entities/raphael-publish.md`, `log.md`, `wiki/log.md`, and run log.
- Detailed run log: `logs/webhook-runs/gh-25496127090-1.md`.

## [2026-05-07] update | incremental_build run_id=gh-25496140596-1
- Synced `origin/main` with protective stash workflow (`stash -> fetch/checkout/pull --ff-only -> stash pop`).
- Incremental diff base: `9687a8f29d7df8d8c7f9d31ae0d1b95a7c4fe831..8706e776163ae439002975ea6a1bdefa608bd53c`; fallback `HEAD~1..HEAD` (both hit `raw/raphael-publish.md`).
- Changed markdown files under `raw/**/*.md`: raw/raphael-publish.md.
- Updated affected `wiki/sources/`, `wiki/entities/`, `wiki/concepts/`, `wiki/overview/知识图谱关系.md`, and indexes.
- Detailed run log: `logs/webhook-runs/gh-25496140596-1.md`.
## [2026-05-08] update | incremental_build run_id=gh-25530949671-1
- Synced `origin/main` with protective stash workflow (`stash -> fetch/checkout/pull --ff-only -> stash pop`).
- Incremental diff base: `e629725c027a23c979e49e56c4faeb6dca3a8c4b..35fe76d65b852ebe664e6bbb22c61fa9c8bf47bf`.
- Changed markdown files under `raw/**/*.md`: raw/html-ppt-skill.md.
- Created `wiki/sources/html-ppt-skill.md` and `wiki/entities/html-ppt-skill.md`; updated `index.md`, `wiki/index.md`, `wiki/log.md`, `wiki/overview/知识图谱关系.md`.
- Detailed run log: `logs/webhook-runs/gh-25530949671-1.md`.

