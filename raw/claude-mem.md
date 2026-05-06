# 📦 项目：claude-mem

**项目主页**：
[https://github.com/thedotmack/claude-mem](https://github.com/thedotmack/claude-mem)

**核心描述**：
A Claude Code plugin that automatically captures everything Claude does during your coding sessions, compresses it with AI (using Claude's agent-sdk), and injects relevant context back into future sessions.

**技术标签**：
ai, ai-agents, ai-memory, anthropic, artificial-intelligence, chromadb, claude, claude-agent-sdk, claude-agents, claude-code, claude-code-plugin, claude-skills, embeddings, long-term-memory, mem0, memory-engine, openmemory, rag, sqlite, supermemory

**language**：
TypeScript

**stars**：
72660

**date**：
2026-05-06 07:38:40

---

### 🎯 一句话定位
为 Claude Code（及同类 AI 终端工具）打造的**持久化记忆插件**，通过 AI 压缩与 RAG 技术，让大模型在跨会话编程时“记住”你的历史上下文和技术决策。

### ⚡ 核心功能
1. **自动化记忆捕获与 AI 压缩**：后台静默记录编码过程中的工具调用与对话，利用 Claude Agent SDK 生成语义摘要，降低存储与检索成本。
2. **智能上下文注入 (RAG)**：基于本地向量库，在新会话启动时自动检索并注入高相关性历史记忆，保持项目连贯性。
3. **MCP 技能集成**：提供 `mem-search` 技能，允许 Claude 主动搜索项目历史记录（基于 Model Context Protocol）。
4. **可视化记忆面板**：提供本地 Web UI (localhost:37777)，供开发者实时查看、管理记忆流并追溯引用 (Citations)。
5. **隐私控制**：支持通过 `<private>` 标签主动排除敏感信息（如密钥、内部数据）进入记忆库。

### 🎭 适用场景
1. **长期/复杂项目开发**：每天重启 Claude Code 时，无需反复向 AI 解释项目架构、代码规范和过往的技术决策。
2. **跨天 Bug 调试中断**：周五下班前没解完的 Bug，周一打开终端继续问，AI 依然记得之前的排查路径和试错过程。
3. **多任务/多分支切换**：在不同功能模块间频繁切换时，AI 能通过历史记忆快速找回当前任务的上下文。

### ✅ 是否值得深入研究
**强烈建议研究（值得）**。
该项目拥有惊人的 72k+ Stars，证明其精准击中了当前 AI 编程“上下文遗忘”的痛点。从工程角度看，它是学习 **MCP (Model Context Protocol) 插件开发**、**RAG 落地实践**以及 **Agent 长期记忆（Long-term Memory）工程化**的绝佳范例。

### ⚠️ 主要缺点或风险
1. **Token 消耗成本**：后台持续进行“AI 记忆压缩”和“摘要生成”会产生额外的 API Token 开销。
2. **记忆污染（Stale Context）**：随着项目快速重构，过时的历史记忆可能会被错误检索并注入，反而干扰 AI 的当前判断（依赖其记忆更新/遗忘机制的健壮性）。
3. **开源协议限制**：采用严格的 **AGPL-3.0** 协议，若想将其核心代码直接集成到闭源商业产品中，存在极高的法务风险。

### 🔗 与同类项目对比
* **对比通用记忆库（如 Mem0, Supermemory）**：claude-mem 不是泛用的记忆框架，而是**高度垂直的 IDE/CLI 插件**。它深度绑定 Claude Code 和 MCP 协议，开箱即用，无需开发者自己写粘合代码。
* **对比 IDE 内置功能（如 Cursor 的上下文）**：Cursor 更依赖对代码库文件本身的索引，而 claude-mem 侧重于记录**“交互过程与思考路径”**（Observations & Actions），在延续解决问题的逻辑断层上更具优势。