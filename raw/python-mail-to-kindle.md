# 📦 项目：python-mail-to-kindle

**项目主页**：
[https://github.com/DahlitzFlorian/python-mail-to-kindle](https://github.com/DahlitzFlorian/python-mail-to-kindle)

**核心描述**：
Helps you saving your mail attachments (e.g. epub-files, PDFs) to a temporary directory, convert the files to MOBI-format and send them directly to your Kindle, so that you can read them later and do not have to do all this by hand.

**技术标签**：
automation, docker, docker-image, dockerfile, email, kindle, mail, python, python-3, python-script, python3

**language**：
Python

**stars**：
14

**date**：
2026-05-06 05:10:27

---

### 🎯 一句话定位
一个基于 Python 和 Calibre 的轻量级胶水脚本，用于自动抓取邮箱附件、转换格式并推送到 Kindle。

### ⚡ 核心功能
*   **邮件监听**：通过 IMAP 协议自动读取指定邮箱中的 EPUB、PDF 等附件。
*   **格式转换**：调用底层 Calibre CLI，将附件自动转换为 MOBI 格式。
*   **自动推送**：将转换后的文件通过 SMTP 邮件发送至用户的 Kindle 专属接收邮箱。
*   **容器化部署**：提供 Docker 支持，方便在个人 VPS 或 NAS 上配合 Cronjob 实现无头自动化运行。

### 🎭 适用场景
1.  **资源自动中转**：经常通过邮件接收行业报告 (PDF) 或网络小说 (EPUB)，希望零手动操作直接在 Kindle 上阅读。
2.  **个人自动化工作流**：喜欢在 NAS 或服务器上部署轻量级脚本，搭建属于自己的“稍后阅读”管道的极客。

### ✅ 是否值得深入研究
**不建议**。

**理由**：
1. **业务逻辑已严重过期**：亚马逊官方已于 2022 年底正式停止对 MOBI 格式的 Send to Kindle 支持（现已原生支持并推荐 EPUB）。该项目强制转换为 MOBI 的核心逻辑不仅多此一举，甚至会导致推送失败。
2. **技术含量低**：项目本质只是一个简单的 `IMAP收取 + Subprocess调用Calibre + SMTP发送` 的脚本，代码量极小，缺乏架构设计和深入学习的价值。

### ⚠️ 主要缺点或风险
1. **核心功能失效**：未跟进 Kindle 官方政策，强行转 MOBI 会被亚马逊服务器拒收。
2. **依赖过于臃肿**：为了一个简单的格式转换强依赖庞大的 Calibre，会导致 Docker 镜像体积巨大，违背轻量化脚本的初衷。
3. **安全性薄弱**：邮箱账号密码直接以明文形式存储在 `config.ini` 中，不支持 OAuth2 等现代安全认证方式（部分邮箱如 Gmail 现已很难使用纯密码进行 IMAP 登录）。

### 🔗 与同类项目对比
*   **相比 Calibre-Web / calibre-server**：本项目是一个纯粹的单向推送脚本，无 UI、无书籍管理能力，极其简陋；优势仅在于配置简单。
*   **相比官方 Send to Kindle**：完全劣势。目前直接将 EPUB 附件发送给 Kindle 邮箱即可原生支持，本项目的转换逻辑属于“画蛇添足”的无效造轮子。