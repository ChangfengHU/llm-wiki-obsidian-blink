---
type: source
tags: [github, open-source, ai-tool, agent, presentation]
summary: HTML PPT Studio 是一个无需构建步骤的纯静态 HTML/CSS/JS 幻灯片制作引擎，同时也是专为 AI Agent 设计的技能库（AgentSkill）。
sources: [raw/html-ppt-skill.md]
created: 2026-05-08
updated: 2026-05-08
layer: L1
confidence: high
reasoning: 直接从源文件提取事实，无推断。
---

# html-ppt-skill

## 基本信息
- **项目主页**： https://github.com/lewislulu/html-ppt-skill
- **语言**： HTML
- **Stars**： 2964
- **更新时间**： 2026-05-08 01:47:54

## 核心要点
1. 无需构建步骤的纯静态 HTML/CSS/JS 幻灯片渲染引擎，同时作为一个 AgentSkill。
2. 内置 36 种主题、15 套完整模板、31 种页面布局。
3. 包含 27 种 CSS 动画和 20 种手写 Canvas 特效（如力导向知识图谱、黑客帝国代码雨、粒子爆炸等）。
4. 演讲者模式：按 `S` 键开启双屏模式，使用 `BroadcastChannel` 实现无延迟同步，通过 `iframe` 配合 URL 参数实现像素级预览。
5. 自动化导出：内置 `render.sh` 脚本，可通过 Headless Chrome 将幻灯片渲染导出为图片。

## 关联实体/概念链接
- [[wiki/entities/html-ppt-skill]]
- [[wiki/concepts/ai-内容发布自动化]]