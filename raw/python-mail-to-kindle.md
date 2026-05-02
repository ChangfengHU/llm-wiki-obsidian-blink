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
2026-05-02 14:47:46

---

### 🎯 一句话定位
一个基于 Python 和 Docker 的个人自动化“胶水”脚本，用于抓取特定邮箱的电子书附件，借助 Calibre 转换格式后自动推送到 Kindle。

### ⚡ 核心功能
1. **IMAP 邮件监听**：自动登录配置的邮箱，检索并下载指定格式（如 epub, pdf）的附件到临时目录。
2. **本地格式转换**：调用宿主机或 Docker 容器内的 Calibre CLI 工具，将下载的书籍强制转换为 MOBI 格式。
3. **SMTP 自动投递**：将转换后的文件作为附件，通过邮件发送至用户的 `@kindle.com` 专属收件箱。
4. **容器化运行**：提供 Dockerfile，方便在 NAS 或云服务器上结合 Cronjob 进行无人值守的定时执行。

### 🎭 适用场景
*   **个人图书中转站**：习惯在手机/电脑上随手将电子书发送到一个固定邮箱，希望服务器自动处理格式并同步到 Kindle 的重度阅读者。
*   **Python 自动化学习**：适合 Python 初学者作为学习 IMAP 收件、SMTP 发件以及调用外部系统命令（CLI）的参考案例。

### ✅ 是否值得深入研究
**不建议**。

**理由**：
1. **核心逻辑已过时/失效**：亚马逊官方已于 2022 年底正式废弃了对 MOBI 格式的 Send-to-Kindle 支持，全面转向原生支持 EPUB。该项目核心卖点是“转换为 MOBI”，在当前环境下不仅多此一举，甚至会导致亚马逊拒收邮件。
2. **技术深度极低**：仅仅是一个 14 Star 的个人练手脚本，本质是把内置库（`imaplib`, `smtplib`）和外部工具（Calibre）拼凑在一起，缺乏架构设计和深入研读的价值。

### ⚠️ 主要缺点或风险
1. **格式兼容性灾难**：如上所述，强绑定 MOBI 格式导致项目在现代 Kindle 生态中完全失效，除非用户自己修改源码跳过转换步骤。
2. **安全风险**：需要在明文配置文件 (`config.ini`) 中写入私人邮箱的账号和密码。如果没有使用“应用专用密码”，存在极大的隐私泄露风险。
3. **依赖过于笨重**：为了处理格式转换，必须依赖庞大的 Calibre 软件。将 Calibre 打包进 Docker 镜像会导致镜像体积臃肿，性价比极低。

### 🔗 与同类项目对比
*   **相比 Calibre-Web**：Calibre-Web 是成熟的电子书管理平台，带 Web 界面，支持一键推送 EPUB 到 Kindle，且持续维护更新。本项目仅仅是个简陋的后台脚本，完全被降维打击。
*   **相比单纯的邮件转发规则**：既然目前 Kindle 已经原生支持 EPUB，用户完全可以在主流邮箱（如 Gmail/Outlook）中设置一条自动转发规则，直接把带 EPUB 附件的邮件转发给 Kindle 邮箱即可，连这个 Python 脚本都不再需要。