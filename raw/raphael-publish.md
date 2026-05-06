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
749

**date**：
2026-05-06 03:05:10

---

### 🎯 一句话定位
一款基于 React 的现代 Markdown 编辑器，核心解决**富文本无缝转 Markdown** 与 **微信公众号排版（防盗链、样式塌陷）** 的痛点。

### ⚡ 核心功能（3~5条）
1. **魔法粘贴（富文本逆向解析）**：底层基于 `turndown`，支持将飞书、Notion、Word 等富文本直接粘贴并自动净化为纯净 Markdown，支持直接粘贴图片。
2. **微信生态特化引擎**：内置 `wechatCompat.ts`，将外链图片自动转 Base64 绕过微信防盗链限制，并重塑列表/表格 DOM 结构防止在微信中塌陷。
3. **开箱即用的高定主题**：内置 30 套针对不同场景优化的 CSS 主题（如 Notion风、Claude风、少数派风），一键切换，免去手写 CSS 的烦恼。
4. **多端预览与导出**：支持手机/平板/PC实时预览，并支持通过 `html2pdf.js` 导出为 PDF 或 HTML。

### 🎭 适用场景
* **自媒体与内容创作者**：习惯在 Notion、飞书、Obsidian 中写稿，需要一键将内容完美同步到微信公众号后台。
* **技术博主/程序员**：希望用纯 Markdown 写作，但受够了微信公众号后台糟糕的代码块渲染和排版体验。
* **前端工具开发者**：需要开发类似“富文本转MD”、“特定平台富文本兼容”工具，可作为优秀的源码参考。

### ✅ 是否值得深入研究
**结论：值得（特别是前端工程师）。**
**理由**：
该项目代码极度干净（React 18 + Vite + TS），且工程化完善（包含 Vitest 单元测试和 Playwright E2E 测试）。其最核心的价值在于 `src/lib` 目录下的几个文件：**如何处理剪贴板的 HTML 转 Markdown (`htmlToMarkdown.ts`)**，以及 **如何用纯前端方案 Hack 微信公众号的渲染规则 (`wechatCompat.ts`)**。非常适合作为学习 DOM 操作、AST 转换和编辑器开发的实战范例。

### ⚠️ 主要缺点或风险
1. **Base64 图片的体积隐患**：为了解决外链防盗链，项目将图片转为 Base64。但微信公众号后台对单篇图文的总字符数/体积有严格限制，如果文章包含大量高清大图，转换后的 Base64 极易导致公众号保存失败。
2. **跨域限制（CORS）**：纯前端将外部网络图片转 Base64 时，必然会遇到浏览器的跨域拦截，除非目标图片服务器允许跨域，或者用户直接粘贴本地截图。
3. **平台强绑定**：部分底层 DOM 改造逻辑（如 `wechatCompat`）是专为微信公众号妥协的，如果用于常规网页发布，可能会产生冗余的 HTML 标签。

### 🔗 与同类项目对比
* **对比 Markdown Nice (mdnice)**：mdnice 是老牌工具，但目前商业化严重、广告多，且技术栈较老。Raphael 更加纯粹、现代化，UI 审美（如 Claude、Linear 主题）更契合当下工程师品味。
* **对比 Doocs/md**：Doocs 也是优秀的开源公众号排版工具，但 Raphael 在**“富文本逆向解析（魔法粘贴）”**这一前置节点做得更深，更适合重度依赖 Notion/飞书作为内容源的用户。