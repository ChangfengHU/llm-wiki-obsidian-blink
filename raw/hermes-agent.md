---
url: https://github.com/NousResearch/hermes-agent
stars: 127946
language: Python
tags: [ai, ai-agent, ai-agents, anthropic, chatgpt, claude, claude-code, clawdbot, codex, hermes, hermes-agent, llm, moltbot, nous-research, openai, openclaw]
research_date: 2026-05-01
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
由著名开源 AI 机构 Nous Research 打造的**具备“自我进化”能力的跨平台 AI Agent**，通过闭环学习机制伴随用户成长，支持无缝接入终端与各主流通讯软件。

### ⚡ 核心功能
1. **闭环学习与长期记忆**：不仅仅是 RAG，Agent 能从交互经验中自主创建并优化“技能（Skills）”，利用 Honcho 构建跨会话的用户画像，实现越用越懂你。
2. **全渠道无缝接入**：提供强大的终端 UI（TUI），同时内置 Gateway，可直接接入 Telegram、Discord、Slack 等通讯软件，实现“云端干活，手机端交互”。
3. **极低成本的 Serverless 部署**：原生支持 Modal、Daytona 等 Serverless 架构，闲置时自动休眠，唤醒按需计费；也支持 $5 的廉价 VPS 部署。
4. **自主调度与并发执行**：内置自然语言驱动的 Cron 定时任务系统（如“每天早上发一份日报”），并能拉起隔离的子 Agent 并行处理复杂工作流。
5. **高度可扩展的工具链**：无缝切换各类 LLM（OpenRouter、本地、OpenAI 等），内置 40+ 工具，支持接入 MCP（Model Context Protocol）标准扩展能力，并包含浏览器自动化（基于 Camofox）。

### 🎭 适用场景
* **全天候个人助理**：部署在云端，在外通过 Telegram 发送语音或文字，让 Agent 帮你查资料、跑脚本、发邮件，保持跨平台上下文连贯。
* **自动化研发/运维监控**：利用内置的 Cron 和子 Agent 功能，设定每天半夜自动拉取代码、执行审计或检查服务器状态，并在早晨将报告推送到 Slack。
* **重度知识工作者伴侣**：需要一个能记住你的写作风格、代码习惯和历史项目背景的 AI，避免每次开启新对话都要重新输入长串 Prompt。

### ✅ 是否值得深入研究
**绝对值得（Highly Recommended）。**
**理由**：Nous Research 出品保证了其在 Agent 领域的学术与工程前沿性。超过 12 万的 Stars（极其罕见）证明了其巨大的社区影响力。该项目展示了下一代 Agent 的标准形态：**脱离单一网页端、具备程序化记忆、支持 MCP 生态、以及 Serverless 友好**。非常适合作为 Agent 架构设计的顶级参考。

### ⚠️ 主要缺点或风险
1. **架构复杂度高**：融合了 Python 后端、Node.js 浏览器工具、Docker/Nix 环境配置以及多种数据库和网关，初学者本地跑通和排错（尤其是多平台 Gateway）有一定门槛。
2. **API 成本不可控风险**：由于具备自主创建技能、拉起子 Agent 并行工作以及 Cron 定时任务的功能，如果没有设置好消费上限，容易在后台消耗大量 Token。
3. **多端环境兼容性陷阱**：虽然号称 Run anywhere，但 README 中已提及 Android/Termux 环境存在语音依赖冲突，Windows 必须依赖 WSL2，底层依赖较重。

### 🔗 与同类项目对比
* **对比 AutoGPT / BabyAGI**：Hermes 更注重**“人机协同与日常陪伴”**（通过通讯软件交互、用户画像），而不是纯粹的“给个目标让它自己瞎跑”。它的落地实用性远超早期自主 Agent。
* **对比 OpenDevin / Cline (Claude Code)**：后者是垂直于写代码和控制 IDE 的工具，而 Hermes 是**通用型助理**。Hermes 可以写代码，但更擅长跨场景的任务调度和长期记忆。
* **对比 Coze / Dify**：Coze/Dify 侧重于通过可视化工作流（GUI）编排 Agent；Hermes 则是**代码优先、CLI 原生**，极客属性拉满，更适合开发者做深度定制和底层资源（如 GPU 集群）调度。