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
2026-05-02 14:53:39

---

### 🎯 一句话定位
一个基于 Python 的“胶水”脚本，用于自动抓取邮箱中的电子书附件，调用 Calibre 转换为 MOBI 格式后推送到 Kindle。

### ⚡ 核心功能
1. **自动抓取附件**：通过 IMAP 协议定时读取指定邮箱，提取匹配的电子书文件（EPUB/PDF等）。
2. **格式转换**：调用宿主机或容器内的 Calibre CLI，将文件转换为 Kindle 兼容格式。
3. **自动投递**：通过 SMTP 将转换后的电子书发送至用户的专属 Kindle 接收邮箱。
4. **容器化运行**：提供 Dockerfile，方便在 NAS 或云服务器上配合 Cron 实现后台静默运行。

### 🎭 适用场景
1. **资源站自动化**：经常从提供“邮件推送”功能的资源网站或 Telegram Bot 获取电子书，希望零手动操作直接在 Kindle 上阅读。
2. **NAS 极客玩家**：拥有 7x24 小时运行的闲置服务器或 NAS，希望搭建个人电子书自动化流转管道。

### ✅ 是否值得深入研究
**不建议深入研究（代码层面），且直接使用存在失效风险。**

**理由**：
该项目仅有 14 Stars，本质上是将 `imaplib`、`smtplib` 和 `subprocess`（调用 Calibre）拼接在一起的个人练手脚本。代码结构极其简单，没有复杂的架构设计或高级特性，作为 Python 自动化脚本的参考案例尚可，但不具备深入研读的工程价值。

### ⚠️ 主要缺点或风险
1. **核心逻辑已过时（致命问题）**：亚马逊 Send to Kindle 服务已于 2023 年底**彻底废弃 MOBI 格式**，转而原生支持 EPUB 推送。该项目强依赖 Calibre 转 MOBI，不仅多此一举，且目前大概率会被亚马逊服务器拒收。
2. **运行依赖过重**：为了一个简单的格式转换，需要在 Docker 镜像中打包庞大的 Calibre 依赖，导致镜像体积臃肿，违背了轻量化自动化的初衷。
3. **安全性较弱**：邮箱账密明文硬编码在 `config.ini` 中。且现代主流邮箱（如 Gmail/Outlook）已逐步禁用基础账号密码 SMTP 登录，脚本未提及对应用专用密码（App Passwords）或 OAuth 的适配。

### 🔗 与同类项目对比
*   **对比 Calibre-Web**：本项目极度轻量，无 UI 负担，纯后台运行；但完全丧失了 Calibre-Web 强大的图书元数据管理和在线阅读能力。
*   **对比原生邮箱转发规则**：鉴于目前 Kindle 官方邮箱已原生支持 EPUB/PDF，用户完全可以在自己的邮箱里设置一条**自动转发规则**，直接将带附件的邮件转发给 Kindle。本项目的核心价值已被亚马逊官方的更新大幅削弱。