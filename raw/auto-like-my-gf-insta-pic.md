# 📦 项目：auto-like-my-gf-insta-pic

**项目主页**：
[https://github.com/gulzar1996/auto-like-my-gf-insta-pic](https://github.com/gulzar1996/auto-like-my-gf-insta-pic)

**核心描述**：
Bot to automatically like your friend's Instagram post and notify you on Slack

**技术标签**：
bot, crone-job, instagram-post, nodejs, slack

**language**：
JavaScript

**stars**：
815

**date**：
2026-05-06 05:08:41

---

### 🎯 一句话定位
这是一个主打“男友求生欲”的 Node.js 娱乐脚本，通过定时任务轮询 Instagram API，自动秒赞特定用户的最新帖子并推送到 Slack。

### ⚡ 核心功能
*   **自动点赞**：通过 Instagram Developer API 获取指定 `user_id` 的最新动态并执行点赞操作。
*   **Slack 通知**：点赞成功后，通过 Webhook 机制向指定的 Slack 频道发送通知。
*   **灵活的触发机制**：暴露 `/run` HTTP 接口，既支持本地 `node-cron` 轮询，也支持接入外部 Cron 服务（如 cron-job.org）。
*   **多环境部署**：开箱即用地支持本地运行、Docker 容器化部署以及 Heroku 云端部署。

### 🎭 适用场景
*   **恋爱求生/社交关注**：确保自己永远是“第一个”点赞女朋友或暗恋对象 Instagram 帖子的人，节省刷社交媒体的时间。
*   **Node.js 自动化入门教学**：适合作为新手学习“API 对接 + 定时任务 + Webhook 通知 + Docker 部署”的基础 Demo。

### ✅ 是否值得深入研究
**不建议深入研究。**

**理由**：
该项目是一个典型的“点子驱动”的整活项目（Meme Project），其 800+ Stars 主要归功于有趣的场景立意，而非技术深度。代码逻辑极度简单（仅为 Express 接口 + API 调用），且由于技术栈陈旧和外部平台政策变化，其实际可用性和学习价值已经很低。

### ⚠️ 主要缺点或风险
*   **API 失效风险极高**：项目严重依赖 Instagram 官方开发者 API。现今 Meta/Instagram 对个人开发者的 API 限制极其严格，普通人极难申请到读取和点赞权限，代码大概率已无法直接运行。
*   **技术栈严重老化**：`package.json` 显示其基于 Node 8.x 开发，且使用了早已被官方废弃的 `request` 库，不符合现代 Node.js 开发规范（如 Fetch 或 Axios）。
*   **缺乏风控对抗**：固定频率（15分钟）的简单轮询极易触发社交平台的 Rate Limit（频率限制）或账号风控。

### 🔗 与同类项目对比
*   **对比原生爬虫/RPA（如 Puppeteer/Selenium）**：本项目直接调用官方 API，代码体积更小、运行资源消耗极低；但劣势在于**毫无绕过反爬和风控的能力**，一旦 API 权限被封死则项目彻底瘫痪，不如无头浏览器方案灵活。
*   **对比原版 Python 项目**：本项目受 `cyandterry/Like-My-GF`（Python版）启发，用 JS 重写并增加了 Docker 和 Heroku 部署支持，对前端/Node 开发者更友好，但在核心逻辑上并无本质创新。