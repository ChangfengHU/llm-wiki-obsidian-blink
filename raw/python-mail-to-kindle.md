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
2026-05-02 14:50:13

---

### 🎯 一句话定位
一个基于 Python 和 Calibre 的自动化“胶水脚本”，用于抓取邮箱附件（EPUB/PDF）、自动转换为 MOBI 格式并推送到 Kindle。

### ⚡ 核心功能
*   **邮件附件抓取**：通过 IMAP 协议自动连接邮箱，提取指定格式的电子书附件。
*   **自动格式转换**：在后台调用 Calibre CLI，将 EPUB/PDF 等格式自动转换为 Kindle 曾经的主流格式 MOBI。
*   **Kindle 自动推送**：将转换后的文件通过 SMTP 直接发送至用户的 Kindle 专属接收邮箱。
*   **容器化部署**：提供 Dockerfile，方便在服务器上结合 Cronjob 实现无人值守的自动化运行。

### 🎭 适用场景
*   **电子书重度阅读者**：经常在手机或电脑上下载 EPUB/PDF，希望只需把文件作为附件转发到一个特定邮箱，就能自动出现在 Kindle 上。
*   **资讯/期刊自动化订阅**：接收定期发送 PDF/EPUB 附件的 Newsletter（如某些独立杂志），并希望它们自动推送到 Kindle。

### ✅ 是否值得深入研究
**不建议深入研究**。

**理由**：这是一个典型的个人练手工具（仅 14 Stars）。本质上只是将 `IMAP 库`、`subprocess (调用 Calibre)` 和 `SMTP 库` 拼凑在一起的脚本。对 Python 新手学习“如何处理邮件”和“如何写 Dockerfile”有微小的参考价值，但毫无架构深度。更重要的是，它的核心业务逻辑已经过时。

### ⚠️ 主要缺点或风险
*   **核心逻辑已过时（致命伤）**：亚马逊 Send-to-Kindle 服务目前已**原生支持 EPUB 并正式淘汰了 MOBI 格式**。该项目强制转换为 MOBI 的做法不仅多此一举，甚至可能导致推送失败。
*   **运行依赖过重**：为了转换格式，必须在系统或 Docker 镜像中安装庞大的 Calibre 软件，作为一个轻量级脚本来说，极其臃肿。
*   **配置安全性差**：账号、密码等敏感信息要求明文写在 `config.ini` 文件中，未使用更标准、安全的的环境变量（Env Vars）注入。

### 🔗 与同类项目对比
*   相比于 **Calibre-Web**（提供完整的 Web UI、强大的书籍管理和 Kindle 推送），该项目只是一个简陋的单向管道。
*   相比于 **亚马逊官方 Send-to-Kindle**：官方现已直接支持将 EPUB 作为邮件附件发送并自动解析，完全不再需要这种中间件来做格式转换，该项目的核心存在价值已基本消失。