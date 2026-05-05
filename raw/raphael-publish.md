# 📦 项目：raphael-publish

**项目主页**：
[https://github.com/liuxiaopai-ai/raphael-publish](https://github.com/liuxiaopai-ai/raphael-publish)

**核心描述**：
Raphael Publish - 公众号排版大师 | 现代 Markdown 排版引擎

**技术标签**：
markdown, markdown-editor, wechat

**language**：
TypeScript

**stars**：
748

**date**：
2026-05-05 17:20:35

---

### 🎯 一句话定位
一个基于 React 18 的现代 Markdown 编辑器，专为解决微信公众号排版痛点（如图片防盗链、富文本格式错乱、样式单一）而生。

### ⚡ 核心功能
- **富文本“魔法粘贴”**：监听剪贴板事件，底层基于 `turndown`，将飞书、Notion 或网页的富文本直接粘贴并自动净化为纯净 Markdown。
- **微信底层 DOM 适配**：通过 `wechatCompat` 引擎重塑列表和表格 DOM，解决微信公众号中常见的样式塌陷问题。
- **图片防盗链破解**：一键复制时，自动将外链图片转为 Base64 注入剪贴板，彻底绕过微信“此图片来自第三方”的报错。
- **开箱即用的高定主题**：内置 30 套基于 CSS 深度定制的主题（如 Notion风、少数派风），一键切换，免去手写内联样式的繁琐。

### 🎭 适用场景
- **技术博主/自媒体**：习惯在 Obsidian/Notion 中使用 Markdown 写作，需要无损、美观地发布到微信公众号。
- **内容搬运与多发平台**：需要将飞书文档、Word 或网页内容快速转换为标准化 Markdown 格式进行多平台分发。
- **公众号运营团队**：希望摆脱微信原生编辑器，通过快捷键和模板实现高效的图文排版。

### ✅ 是否值得深入研究
**结论：前端工程师（特别是涉及富文本和剪贴板操作的）值得深入研究。**

**理由**：
1. **工程化规范极佳**：基于 Vite + React 18 + TS，配备了完整的 Vitest 单元测试和 Playwright E2E 测试，是优秀的现代前端开源范例。
2. **解决特定痛点的代码有高参考价值**：其 `src/lib/htmlToMarkdown.ts`（剪贴板富文本解析）和 `src/lib/wechatCompat.ts`（微信 DOM 兼容处理）对开发类似编辑器、浏览器插件极具借鉴意义。

### ⚠️ 主要缺点或风险
- **图片 Base64 转换的隐患**：长图或大量高清图转为 Base64 后，可能导致剪贴板体积过大，甚至触发微信图文素材的字符数上限限制。
- **过度依赖微信生态规则**：核心价值建立在微信公众号当前对内联样式（Inline CSS）的解析逻辑上。一旦微信更改底层规则或加强安全过滤，部分排版可能会瞬间失效。
- **定位局限**：它是一个“排版发布中转站”，而非文档管理工具，缺乏云端存储和多版本同步能力。

### 🔗 与同类项目对比
- **对比 Markdown Nice (mdnice)**：mdnice 历史悠久但目前商业化较重、代码老旧。Raphael Publish 技术栈更现代（Vite + Tailwind），UI 交互更优（Framer Motion 动画），且完全开源无广告。
- **对比 Doocs/md**：Doocs/md 同样是优秀的开源公众号排版工具。Raphael 的差异化优势在于更强大的**“魔法粘贴”（富文本逆向解析）**体验，以及更具设计感的 30 套预设主题。