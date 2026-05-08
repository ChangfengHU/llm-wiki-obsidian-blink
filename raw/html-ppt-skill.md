# 📦 项目：html-ppt-skill

**项目主页**：
[https://github.com/lewislulu/html-ppt-skill](https://github.com/lewislulu/html-ppt-skill)

**核心描述**：
HTML PPT Studio — AgentSkill with 24 themes, 31 layouts, 20+ animations for building professional HTML presentations

**技术标签**：
HTML, CSS, Presentation, AgentSkill, Canvas

**language**：
HTML

**stars**：
2964

**date**：
2026-05-08 01:47:54

---

### 🎯 一句话定位
【FACT】这是一个**无需构建步骤的纯静态 HTML/CSS/JS 幻灯片渲染引擎**，同时作为一个 **AgentSkill**，旨在让 AI 助手（Agents）通过自然语言指令直接生成包含丰富动效和专业排版的演示文稿。
*来源：GitHub README ("A world-class AgentSkill...", "pure static HTML/CSS/JS, no build step")*

### ⚡ 核心功能
【FACT】
1. **AI 技能集成 (AgentSkill)**：提供 `SKILL.md`，可通过一行命令 (`npx skills add`) 接入 AI Agent 运行时，支持通过自然语言（如“做一份8页的技术分享”）直接生成 PPT。
2. **纯静态零构建**：完全基于 HTML/CSS/JS，无需 Webpack/Vite 等打包工具，通过切换 `<link>` 标签即可全局更换主题。
3. **专业级演讲者模式**：按 `S` 键开启双屏模式。使用 `BroadcastChannel` 实现主窗口与演讲者窗口的无延迟同步，并通过 `iframe` 配合 URL 参数实现完美像素级预览（无重绘、无闪烁）。
4. **海量视觉资产预设**：内置 36 种主题、15 套完整模板、31 种页面布局。
5. **原生高级动效库**：包含 27 种 CSS 动画和 20 种手写 Canvas 特效（如力导向知识图谱、黑客帝国代码雨、粒子爆炸等），进入幻灯片时自动初始化。
*来源：GitHub README / 代码结构分析*

---

### 🎭 适用场景
【INFERENCE】
- **AI 产品/平台开发者**：需要赋予 LLM 或 Agent 生成可视化报告、PPT、图文排版能力时，可将其作为底层的 HTML 渲染引擎和 Prompt 技能库。
- **程序员/极客的技术分享**：喜欢用代码控制排版，需要终端风（Terminal）、代码高亮、知识图谱等硬核视觉效果，但又不想折腾 Node.js 构建环境的开发者。
- **自媒体/社交平台图文生成**：利用其预设的“小红书白底杂志风”等模板，配合 AI 批量自动化生成 3:4 比例的社交媒体图片（通过内置的 Headless Chrome 导出脚本）。

**判断依据**：README 中明确列出了 "AgentSkill" 的安装方式、自然语言 Prompt 示例（如“做一份小红书图文”），以及纯静态免构建的技术特性。
**confidence**：high

---

### ✅ 是否值得深入研究
【INFERENCE】
**结论：值得**

**理由**：
- **信号1：极佳的 AI-Native 架构参考**。它展示了如何让 LLM 稳定输出复杂 UI：通过提供极度模块化的 HTML 骨架、CSS Token 和预设布局库，将 LLM 的任务从“写代码”降维成“填空和拼装”，这是目前 AI 生成 UI 的最佳实践。
- **信号2：巧妙的原生 Web 技术应用**。其演讲者模式没有使用复杂的 WebSocket 或状态管理库，而是用原生的 `BroadcastChannel` 做跨窗口通信，用 `iframe` 做隔离预览，用 `postMessage` 做无刷新翻页，代码极具学习价值。
- **信号3：高质量的零依赖图形库**。`assets/animations/fx/` 下的 20 个 Canvas 动效均为无第三方依赖的手写实现，是学习前端物理动效（如力导向图、磁场、粒子系统）的优秀源码。

**confidence**：high

---

### ⚠️ 主要缺点或风险
【INFERENCE】
- **缺点1：人工编辑的门槛极高**。由于没有提供 WYSIWYG（所见即所得）的图形化编辑器，且没有采用 Markdown 语法，如果 AI 生成的结果有偏差，用户必须直接修改 HTML 代码进行微调，对非技术人员极度不友好。
- **缺点2：导出格式受限**。目前仅提供基于 Headless Chrome 的 PNG 导出脚本 (`render.sh`)，不支持一键导出为 `.pptx` 格式，在传统的企业办公审批流或跨部门协作中很难流转。
- **缺点3：排版自由度不如传统软件**。受限于预设的 31 种 Layout，如果需要进行复杂的绝对定位、随意拖拽元素，在 HTML 中手写会非常繁琐。

**对使用场景的影响**：该项目注定是一个“极客玩具”或“AI 渲染后端”，无法替代 PowerPoint/Keynote 成为大众的日常办公工具。

---

### 🔗 与同类项目对比
【INFERENCE】

**对标项目**：Reveal.js, Slidev, Marp

| 维度 | 本项目 (html-ppt-skill) | Reveal.js | Slidev | Marp |
|-----|--------|----------|----------|------|
| **定位** | AI Agent 技能 / 纯静态引擎 | 老牌 HTML 演示框架 | 面向开发者的 Markdown 演示 | 极简 Markdown 转 PPT 工具 |
| **核心优势** | AI 原生整合、零构建、预设极度丰富（尤其是 Canvas 动效） | 生态庞大、插件丰富、可高度定制 | 基于 Vue/Vite，组件化强，支持 Markdown 编写 | 语法极简，VS Code 插件体验好，支持导出 PDF/PPTX |
| **核心劣势** | 只能写 HTML，不支持 Markdown，无 `.pptx` 导出 | 框架较重，默认样式陈旧，需自己找主题 | 需要 Node.js 环境，有打包构建步骤 | 排版死板，动效极弱，只能做最基础的演示 |

**对比依据**：基于前端演示工具生态的客观现状，结合本项目 README 中强调的 "no build step"、"AgentSkill" 及纯 HTML 编写的特性得出。
**confidence**：high

---
*元数据（系统必填）*
*信息来源：GitHub README + 代码结构分析*