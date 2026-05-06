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
2026-05-06 02:56:53

---

### 🎯 一句话定位
一款开箱即用的**微信公众号 Markdown 排版工具**，通过底层 DOM 重塑和图片转码，彻底解决跨平台复制到微信后台时的格式错乱和防盗链问题。

### ⚡ 核心功能
1. **富文本“净化”粘贴（魔法粘贴）**：基于 `turndown` 引擎，支持从 Notion、飞书、Word 等处复制富文本，粘贴瞬间自动降级并清洗为纯净 Markdown，支持直接粘贴图片。
2. **微信原生级兼容 (`wechatCompat`)**：一键复制到公众号时，自动将外链图片转为 Base64（破解微信“此图片来自第三方”报错），并重写列表和表格的 DOM 结构以防止微信编辑器样式塌陷。
3. **30+ 高质量预设主题**：告别简陋样式，内置 30 套针对不同场景打磨的独立 CSS 主题（如 Notion风、硅谷风、代码暗黑风等）。
4. **多端实时预览与导出**：支持 PC/平板/手机 视口切换，所见即所得，并集成 `html2pdf.js` 支持导出 PDF/HTML。

### 🎭 适用场景
- **跨平台创作者**：主阵地在 Notion、飞书或 Obsidian，需要将写好的文章无损、快速同步到微信公众号。
- **技术博主/程序员**：厌倦了“秀米”等传统拖拽式排版工具，希望用纯 Markdown 高效完成带代码高亮的公众号排版。
- **文档分享**：需要快速将一份 Markdown 格式的技术文档渲染成美观的 PDF 发送给他人。

### ✅ 是否值得深入研究
**结论：值得（特别是前端工程师）。**

**理由**：
该项目是一个极其标准的现代前端工程（React 18 + Vite + TS + Tailwind），且配备了完整的 E2E 测试（Playwright）和单元测试（Vitest）。
如果你想学习以下技术点，它的源码是绝佳范例：
1. **剪贴板劫持与处理**（如何拦截 Paste 事件并解析 HTML/RTF）。
2. **Markdown 解析与 AST 转换**（`markdown-it` 和 `turndown` 的深度应用）。
3. **针对特定平台的 DOM Hack 技巧**（研究 `src/lib/wechatCompat.ts` 可以学到如何对抗微信这种封闭平台的渲染规则）。

### ⚠️ 主要缺点或风险
1. **Base64 体积隐患**：为了绕过微信防盗链，将图片转为 Base64。如果文章包含大量高清大图，可能导致生成的 HTML 源码体积超标，触发微信后台的字数/体积限制。
2. **微信规则变更风险**：微信公众号编辑器的底层逻辑若发生暗改，项目内 `wechatCompat` 的黑魔法可能会随时失效，维护成本较高。
3. **排版自由度上限**：本质上仍是 Markdown 转换器，无法实现类似“秀米”那种复杂的 SVG 交互动画或绝对定位的图文混排。

### 🔗 与同类项目对比
- **对比 Markdown Nice (mdnice)**：
  - **优势**：技术栈极其现代，代码结构清晰，二次开发体验完爆 mdnice（mdnice 历史包袱较重）；“富文本直转 Markdown”的魔法粘贴体验更平滑。
  - **劣势**：生态和知名度不如 mdnice，缺乏 mdnice 庞大的社区自定义主题库和多平台（知乎、掘金等）一键分发插件。
- **对比 Doocs/md**：
  - 功能定位高度重合，但 Raphael Publish 在视觉 UI 设计和主题审美上更具现代感（Tailwind 驱动），且对 Notion 等现代笔记软件的粘贴兼容做得更细致。