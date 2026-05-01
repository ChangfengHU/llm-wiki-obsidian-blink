---
url: https://github.com/NousResearch/hermes-agent
stars: 127953
language: Python
tags: [ai, ai-agent, ai-agents, anthropic, chatgpt, claude, claude-code, clawdbot, codex, hermes, hermes-agent, llm, moltbot, nous-research, openai, openclaw]
research_date: 1777659771
status: 已研究
---

# 📦 项目：hermes-agent

**项目主页**：
[https://github.com/NousResearch/hermes-agent](https://github.com/NousResearch/hermes-agent)

**核心描述**：
The agent that grows with you

**技术标签**：
ai, ai-agent, ai-agents, anthropic, chatgpt, claude, claude-code, clawdbot, codex, hermes, hermes-agent, llm, moltbot, nous-research, openai, openclaw

---

### 🎯 一句话定位
由知名开源 AI 机构 Nous Research 打造的**具备自我进化能力（闭环学习）的跨端 AI Agent 框架**，主打长效记忆、多平台消息网关及极低成本的 Serverless 部署。

### ⚡ 核心功能（3~5条）
1. **闭环学习与长效记忆**：Agent 能在交互中自主提炼、创建和优化技能（Skills），具备跨会话的记忆检索（FTS5），并能通过 Honcho 持续构建用户画像。
2. **全平台消息网关**：一套代码同时支持强大的终端 TUI（带多行编辑、自动补全）和主流 IM 平台（Telegram, Discord, Slack, WhatsApp 等），实现跨设备会话接力。
3. **极高的基础设施自由度**：模型层支持任意主流 API（OpenRouter/OpenAI/本地等，无缝切换）；运行层支持本地、Docker、及 Serverless 平台（Modal、Daytona），闲置时零成本。
4. **强大的工具链与任务调度**：内置 40+ 工具，原生支持 **MCP（Model Context Protocol）** 扩展；支持 Cron 定时任务自动化调度，并可派生子 Agent 并行处理复杂任务。
5. **为 AI 研究提供基建**：内置轨迹生成（Trajectory generation）和 RL 环境，可用于收集高质量的工具调用数据，反哺下一代 Agent 模型的训练。

### 🎭 适用场景
* **极客的跨端超级助理**：在电脑前用终端 CLI 处理复杂编程或检索任务，离开工位后用 Telegram 语音/文字继续让 Agent 汇报后台进度。
* **自动化运维与数据监控**：利用内置 Cron 和子 Agent，定时（如每天凌晨）拉取服务器数据、分析日志，并自动用自然语言推送到 Slack 或 Discord。
* **AI 开发者与研究员**：作为开发高级 Agent 应用的脚手架，或用于收集真实人机交互轨迹（Trajectories）来微调自己的大语言模型。

### ✅ 是否值得深入研究
**强烈建议深入研究。**
理由：出自 Nous Research 之手，代表了当前开源 Agent 架构的极佳品味。它不仅跳出了“玩具脚本”的范畴，真正解决了“跨端使用”、“长期记忆（自我进化）”和“部署成本”三大痛点，且紧跟前沿接入了 MCP 协议。其代码库对学习如何构建工业级 Agent 极具参考价值。

### ⚠️ 主要缺点或风险
1. **混合技术栈依赖**：主语言是 Python，但底层高级工具链（如浏览器自动化 `agent-browser`, `camofox-browser`）依赖 Node.js，部署和维护环境相对繁琐。
2. **不支持原生 Windows**：强依赖类 Unix 环境，Windows 用户必须使用 WSL2，对部分纯 Windows 开发者不友好。
3. **概念复杂度高**：融合了 Skills、Memory、MCP、Cron、Sub-agents 等众多高级特性，新手通读源码和排查 Bug 的心智负担较重。

### 🔗 与同类项目对比
* **对比 AutoGPT / BabyAGI**：Hermes 不追求毫无头绪的“完全自主死循环”，而是注重“与人协作（Grows with you）”，强调长效记忆和用户画像的沉淀。
* **对比 LangChain / LlamaIndex**：Hermes 不是底层拼图式的积木库，而是一个**开箱即用的完整产品/框架**，自带优秀的 TUI 和多平台 IM 网关。
* **对比 OpenDevin / Claude Computer Use**：Hermes 更偏向于“私人通用助理”和“后台自动化调度”，而非专门针对代码编写或系统级 GUI 控制，它的优势在于无缝融入你日常使用的通讯软件中。