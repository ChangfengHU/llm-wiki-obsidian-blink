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
753

**date**：
2026-05-07 12:35:13

---

🎯 一句话定位
【FACT】专为微信公众号与内容创作者打造的纯前端 Markdown 排版引擎，核心解决从第三方平台（如 Notion、飞书）复制内容到微信公众号时的格式错乱和图片防盗链问题。
*来源：GitHub README*

⚡ 核心功能
【FACT】
1. **魔法粘贴（富文本转 MD）**：基于 `turndown`，支持将飞书、Notion 等富文本直接粘贴并净化为标准 Markdown。
2. **微信格式兼容引擎**：通过底层 DOM 重塑（`wechatCompat.ts`），解决微信公众号列表/表格塌陷问题，并将外链图片转为 Base64 绕过防盗链。
3. **多主题渲染**：内置 30 套基于 Tailwind CSS 设计的排版主题，覆盖代码块、引用等元素的独立设计。
4. **多端实时预览**：支持手机、平板、PC 三种视口宽度的实时渲染预览。
*来源：GitHub README / 代码结构 (`src/lib/wechatCompat.ts`, `src/lib/htmlToMarkdown.ts`)*

---

🎭 适用场景
【INFERENCE】
- **微信公众号运营者**：习惯在 Notion、飞书或 Obsidian 中撰写文章，需要快速排版并发布到微信公众号的创作者。
- **技术博主**：需要高频发布带有代码块（`highlight.js` 支持）的技术文章，且对排版审美有较高要求。

*判断依据：README 明确强调了“魔法粘贴”解决跨平台复制痛点，且代码中包含了专门针对微信平台的 DOM 兼容处理逻辑。*
*confidence：high*

✅ 是否值得深入研究
【INFERENCE】
**结论：值得（特别是前端工程师和编辑器开发者）**

理由：
- **信号1：优秀的特定场景工程解法**。项目中的 `src/lib/wechatCompat.ts` 是一个极佳的参考，展示了如何用纯前端手段（DOM 操作、图片转 Base64）对抗封闭平台（微信）的富文本编辑器限制。
- **信号2：富文本与 Markdown 转换的优秀实践**。结合了 `markdown-it` (MD转HTML) 和 `turndown` (HTML转MD)，处理了复杂的剪贴板事件，对开发类 Notion 块级编辑器或内容中台很有借鉴意义。
- **信号3：现代且规范的前端工程**。使用 React 18 + Vite + Tailwind，且配置了 `vitest` 单元测试和 `playwright` E2E 测试，代码结构清晰，适合作为中小型开源项目的学习模板。

*confidence：high*

⚠️ 主要缺点或风险
【INFERENCE】
- **缺点1：强依赖微信公众号底层规则**。由于绕过图片防盗链使用的是 Base64 注入，如果微信公众号后台更新规则，限制 Base64 图片大小或拦截特定 DOM 结构，该工具的核心竞争力将失效。
- **缺点2：纯客户端处理的性能瓶颈**。图片转 Base64 和长文的 DOM 解析全在浏览器端进行，如果文章包含大量高清图片，可能导致浏览器卡顿或超出剪贴板体积限制。
- **缺点3：缺乏云端存储与同步**。作为一个纯静态工具，用户数据依赖本地浏览器缓存，意外刷新或清理缓存可能导致未导出的草稿丢失。

*对使用场景的影响：用户在处理多图长文时可能会遇到复制失败的问题；不能作为主力写作软件，只能作为发布前的“排版管道”。*
*confidence：medium*

🔗 与同类项目对比
【INFERENCE】

对标项目：Markdown Nice (mdnice), Doocs/md

| 维度 | 本项目 (Raphael Publish) | Markdown Nice (mdnice) | Doocs/md |
|-----|--------|----------|----------|
| **定位** | 现代极简的排版“管道”工具 | 大而全的公众号排版社区 | 开源极简的微信排版工具 |
| **核心优势** | 跨平台富文本“魔法粘贴”体验极佳，UI现代，纯净无广 | 主题极其丰富，生态成熟，支持多平台一键发布 | 完全开源，社区活跃度高，功能稳定 |
| **核心劣势** | 刚起步生态较小，无云端同步，无法自定义 CSS | 商业化严重，广告多，部分主题收费 | UI/UX 相对传统，富文本直接粘贴的兼容性一般 |

*对比依据：基于 GitHub 活跃度、技术栈分析以及国内微信 Markdown 排版工具圈的现状。mdnice 已高度商业化，Doocs/md 偏传统，本项目切入了“现代审美 + 纯净开源 + Notion/飞书工作流”的细分空白。*
*confidence：high*

---
*信息来源：GitHub README + 代码结构分析*