--- 
type: entity
tags: [github, open-source, ai-tool, agent, presentation]
summary: HTML PPT Studio 是一个无需构建步骤的纯静态 HTML/CSS/JS 幻灯片制作引擎，同时也是专为 AI Agent 设计的技能库（AgentSkill）。
sources: [raw/html-ppt-skill.md]
created: 2026-05-08
updated: 2026-05-08
layer: L1
---

# html-ppt-skill

## 基本信息
- **项目主页**： https://github.com/lewislulu/html-ppt-skill
- **语言**： HTML
- **Stars**： 2958
- **更新时间**： 2026-05-08 01:11:23

## 核心功能
1. **AI Agent 技能集成**：通过 `npx skills add` 注册后，AI 可直接接收 Prompt（如“做一份赛博朋克风的技术分享”）并输出对应幻灯片。
2. **零构建纯静态架构**：完全基于 HTML/CSS/Vanilla JS，无需 Webpack/Vite 等构建工具，开箱即用。
3. **海量内置资产**：内置 36 种 CSS 主题、15 套完整模板、31 种页面布局以及 47 种动画（包含 20 种手写 Canvas 炫酷特效如知识图谱、粒子爆炸等）。
4. **创新的演讲者模式**：按 `S` 键开启，利用 `BroadcastChannel` 实现双窗口同步，通过加载带 `?preview=N` 参数的 `iframe` 实现与观众视图 100% 像素级一致的无刷新预览。
5. **自动化导出**：内置 `render.sh` 脚本，可通过 Headless Chrome 将幻灯片渲染导出为图片。

## 适用场景
- **AI 应用开发者**：在开发“文本生成 PPT”类 AI 智能体时，将其作为底层的渲染引擎和 Prompt 目标格式，解决 AI 难以直接生成高颜值 PPT 的痛点。
- **极客/前端开发者技术分享**：想要用代码控制幻灯片，且需要极高的定制化视觉效果（如 Canvas 粒子动画、代码高亮），但又不想配置复杂前端工程的开发者。
- **快速生成标准化图文内容**：例如通过 AI 批量生成小红书风格的图文卡片（项目中包含 `xhs-post` 模板）。

## 价值评估
- **值得深入研究**：理由包括巧妙的架构设计（演讲者模式使用 BroadcastChannel + iframe）、拥抱 AI 的产品定位（AgentSkill）、极高的视觉完成度（近 3000 Stars）。
- **主要缺点或风险**：对非技术人员门槛极高（无 WYSIWYG）、纯静态维护的局限性（大型幻灯片文件臃肿）、导出方案的脆弱性（依赖 Headless Chrome 脚本）。

## 与同类项目对比
| 维度 | 本项目 (html-ppt-skill) | Reveal.js | Slidev |
|------|--------|----------|----------|
| 定位 | AI Agent 技能 / 纯静态 HTML | 行业标准的 HTML PPT 框架 | 专为开发者打造的 Markdown PPT |
| 核心优势 | 专为 AI 生成优化，零构建，自带海量高颜值主题和 Canvas 特效 | 生态极其庞大，插件丰富，稳定性极高 | 基于 Markdown 编写体验极佳，融合 Vue 组件生态 |
| 核心劣势 | 手写 HTML 繁琐，缺乏现代前端组件化能力 | 默认主题较老旧，配置项繁杂 | 需要 Node.js 环境和构建步骤，偏重 |

*信息来源：GitHub README + 代码结构分析*