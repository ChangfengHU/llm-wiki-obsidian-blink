# 📦 项目：notebooklm-py

**项目主页**：
[https://github.com/teng-lin/notebooklm-py](https://github.com/teng-lin/notebooklm-py)

**核心描述**：
Unofficial Python API and agentic skill for Google NotebookLM. Full programmatic access to NotebookLM's features—including capabilities the web UI doesn't expose—via Python, CLI, and AI agents like Claude Code, Codex, and OpenClaw.

**技术标签**：
agentic-skill, api, claude, claude-skills, google-notebooklm, notebooklm, notebooklm-api, notebooklm-skill, openclaw-skills, podcast-generator, python, python-api, sdk, skills

**language**：
Python

**stars**：
12478

**date**：
2026-05-04 15:45:12

---

### 🎯 一句话定位
这是一个非官方的 Google NotebookLM Python API 与 CLI 工具，让开发者和 AI Agent 能以编程方式全面接管 NotebookLM，并解锁了网页端未开放的高级导出功能。

### ⚡ 核心功能（3~5条）
1. **全功能 API 与 CLI 封装**：支持通过代码或命令行创建笔记本、导入各类数据源（URL、PDF、YouTube等）、管理对话和分享权限。
2. **多模态内容生成与下载**：支持一键生成并下载播客（Audio Overview）、视频、PPT、思维导图、测验题等多种格式内容。
3. **解锁隐藏高级功能**：提供网页端不支持的批量下载、测验/卡片转 JSON/Markdown、思维导图数据提取、PPTX 导出等能力。
4. **AI Agent 原生集成**：内置 Claude Code、Codex 等大模型 Agent 的 Skill 模板，允许其他 AI 工具直接调用 NotebookLM 的强大能力。

### 🎭 适用场景
* **自动化研究工作流**：科研人员或内容创作者需要批量导入数百篇论文、网页或视频，并自动提取摘要、生成播客或建立知识库。
* **AI Agent 能力扩展**：开发者在构建自己的 AI 智能体时，希望将 NotebookLM 极其强大的长文本理解和高质量 RAG 能力作为底层工具接入。
* **结构化数据提取**：需要将 NotebookLM 生成的测验、思维导图导出为结构化数据（JSON/CSV），以便集成到下游系统（如背单词软件、可视化工具）的开发者。

### ✅ 是否值得深入研究
**值得**。
理由：Google 官方迟迟未推出 NotebookLM API，该项目完美填补了这一巨大空白（1.2万+ Stars 证明了强烈的市场需求）。它不仅提供了开箱即用的自动化工具，其逆向工程和封装非公开 Google 接口的思路，对开发者也极具参考价值。

### ⚠️ 主要缺点或风险
1. **极高的不稳定性风险**：项目基于未公开（undocumented）的内部 API 开发，Google 随时可能更改接口或鉴权方式，导致项目随时“猝死”。
2. **账号限流与封禁风险**：高频的自动化调用极易触发 Google 的风控策略（Rate limits），可能导致账号被限流。
3. **部署环境依赖**：首次登录依赖 Playwright 调起浏览器获取 Cookie，在纯 Serverless 或无头（Headless）服务器环境中自动化部署可能会遇到挑战。

### 🔗 与同类项目对比
相比于 GitHub 上零星的 NotebookLM 自动化脚本，这是目前**生态最完整、完成度最高**的库。
它的绝对差异化优势在于 **“超越官方 UI”**（挖掘并暴露了内部隐藏的 JSON/PPTX 导出能力）以及 **“Agent-First 设计”**（直接提供标准化 Skill 接入），不仅是一个 API 包装器，更是一个强大的中间件。