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
2026-05-02 14:52:50

---

### 🎯 一句话定位
一个将邮件附件（如 EPUB/PDF）自动转换为 MOBI 格式并推送到 Kindle 的 Python 个人自动化脚本。

### ⚡ 核心功能
*   **附件自动提取**：通过 IMAP 协议连接邮箱，自动下载指定格式的电子书附件到临时目录。
*   **格式强制转换**：调用本地或容器内的 Calibre CLI (`ebook-convert`)，将文件转换为 MOBI 格式。
*   **Kindle 邮件推送**：通过 SMTP 协议，将转换后的电子书发送至用户的 Kindle 专属收件箱。
*   **开箱即用的容器化**：提供 Dockerfile，支持在 NAS 或 VPS 上结合 Cronjob 实现定时静默运行。

### 🎭 适用场景
*   **个人阅读流自动化**：习惯在电脑/手机上搜集 EPUB 电子书，希望通过转发邮件自动同步到 Kindle 阅读的重度用户。
*   **NAS/VPS 后台服务**：在个人服务器上跑一个定时任务，实现“即发即收”的无缝阅读体验。

### ✅ 是否值得深入研究
**不建议深入研究。**

**理由**：
1. 项目仅为极其简单的个人练手脚本（14 Stars），代码结构和工程化参考价值极低。
2. **核心业务逻辑已过时**：亚马逊官方已于 2022 年底正式废除 Send-to-Kindle 对 MOBI 格式的支持，全面转向原生支持 EPUB。该项目核心的“转为 MOBI”功能不仅多此一举，甚至会导致推送失败。

### ⚠️ 主要缺点或风险
*   **历史遗留产物（致命缺陷）**：强行将文件转为 MOBI 格式，这在当前的 Kindle 生态中已经失效。现在的正确做法是直接推送 EPUB。
*   **依赖过于臃肿**：为了格式转换，需要在 Docker 镜像中安装极其庞大的 Calibre 软件，导致镜像体积臃肿，部署成本过高。
*   **安全性极差**：邮箱账号和密码直接明文硬编码在 `config.ini` 中，不支持环境变量注入，极易造成凭据泄露；且未适配现代邮箱（如 Gmail/Outlook）的 OAuth2 或应用专用密码机制。

### 🔗 与同类项目对比
*   **对比 Calibre-Web**：Calibre-Web 是成熟的电子书管理和推送系统，带完善的 Web UI 和原生 Kindle 推送支持。本项目仅为单一脚本，毫无竞争力。
*   **对比手写脚本**：在亚马逊原生支持 EPUB 的今天，实现同样的功能只需要 30 行 Python 代码（IMAP 收件 -> SMTP 发件），完全不需要引入 Calibre 依赖进行格式转换。该项目已失去存在的意义。