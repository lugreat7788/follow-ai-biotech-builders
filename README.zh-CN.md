[English](README.md) | **中文**

# 追踪 AI×生物医药建造者，而非网红

一个 AI 驱动的信息聚合工具，追踪创新药与 AI for biology 领域最顶尖的建造者——科学家、创始人和龙头公司负责人——并将他们的最新动态整理成易于消化的摘要推送给你。

**理念：** 追踪那些真正在做产品、有独立见解的人，而非只会搬运信息的网红。

## 你会得到什么

每日或每周推送到你常用的通讯工具（Telegram、Discord、WhatsApp 等），包含：

- 顶级生物医药 / AI-bio 播客新节目的精华摘要（Ground Truths、The Long Run、Raising Health、Training Data）
- 20 位精选 AI×生物医药建造者在 X/Twitter 上的关键观点和洞察（科学家、创始人与公司官方号）
- 所有原始内容的链接
- 支持英文、中文或双语版本

## 快速开始

1. 在你的 AI agent 中安装此 skill（OpenClaw 或 Claude Code）
2. 输入 "set up follow builders" 或执行 `/follow-builders`
3. Agent 会以对话方式引导你完成设置——不需要手动编辑任何配置文件

Agent 会询问你：
- 推送频率（每日或每周）和时间
- 语言偏好
- 推送方式（Telegram、邮件或直接在聊天中显示）

不需要任何 API key——所有内容由中心化服务统一抓取。
设置完成后，你的第一期摘要会立即推送。

## 修改设置

通过对话即可修改推送偏好。直接告诉你的 agent：

- "改成每周一早上推送"
- "语言换成中文"
- "把摘要写得更简短一些"
- "显示我当前的设置"

信息源列表（建造者和播客）由中心化统一管理和更新——你无需做任何操作即可获得最新的信息源。

## 自定义摘要风格

Skill 使用纯文本 prompt 文件来控制内容的摘要方式。你可以通过两种方式自定义：

**通过对话（推荐）：**
直接告诉你的 agent——"摘要写得更简练一些"、"多关注可操作的洞察"、"用更轻松的语气"。Agent 会自动帮你更新 prompt。

**直接编辑（高级用户）：**
编辑 `prompts/` 文件夹中的文件：
- `summarize-podcast.md` — 播客节目的摘要方式
- `summarize-tweets.md` — X/Twitter 帖子的摘要方式
- `summarize-blogs.md` — 博客文章的摘要方式
- `digest-intro.md` — 整体摘要的格式和语气
- `translate.md` — 英文内容翻译为中文的方式

这些都是纯文本指令，不是代码。修改后下次推送即生效。

## 默认信息源

### 播客（4个）
- [Ground Truths — Eric Topol](https://erictopol.substack.com)
- [The Long Run — Luke Timmerman](https://timmermanreport.com/the-long-run/)
- [Raising Health — a16z Bio + Health](https://a16z.com/raising-health/)
- [Training Data — Sequoia](https://www.youtube.com/playlist?list=PLOhHNjZItNnMm5tdW61JpnyxeYH5NDDx8)

### X 上的 AI×生物医药建造者（20位）
[Demis Hassabis](https://x.com/demishassabis), [Eric Topol](https://x.com/EricTopol), [Mohammed AlQuraishi](https://x.com/MoAlQuraishi), [Patrick Hsu](https://x.com/pdhsu), [Jure Leskovec](https://x.com/jure), [Pranav Rajpurkar](https://x.com/pranavrajpurkar), [Anima Anandkumar](https://x.com/AnimaAnandkumar), [Sergey Ovchinnikov](https://x.com/sokrypton), [Alex Zhavoronkov](https://x.com/biogerontology), [Alexander Rives](https://x.com/alexrives), [Ali Madani](https://x.com/thisismadani), [Joshua Meier](https://x.com/joshim5), [Stef van Grieken](https://x.com/stefvangrieken), [Simon Kohl](https://x.com/saakohl), [蛋白质设计研究所 IPD](https://x.com/UWproteindesign), [Arc Institute](https://x.com/arcinstitute), [Chai Discovery](https://x.com/chaidiscovery), [Profluent](https://x.com/ProfluentBio), [Recursion](https://x.com/RecursionPharma), [Moderna](https://x.com/moderna_tx)

### 官方博客（2个）
- [Anthropic Engineering](https://www.anthropic.com/engineering) — Anthropic 团队的技术深度文章
- [Claude Blog](https://claude.com/blog) — Claude 的产品公告与更新

## 安装

### Claude Code
```bash
git clone https://github.com/lugreat7788/follow-ai-biotech-builders.git ~/.claude/skills/follow-ai-biotech-builders
cd ~/.claude/skills/follow-ai-biotech-builders/scripts && npm install
```

### OpenClaw
```bash
git clone https://github.com/lugreat7788/follow-ai-biotech-builders.git ~/skills/follow-ai-biotech-builders
cd ~/skills/follow-ai-biotech-builders/scripts && npm install
```

## 系统要求

- 一个 AI agent（OpenClaw、Claude Code 或类似工具）
- 网络连接（用于获取中心化 feed）

仅此而已。不需要任何 API key。所有内容（博客文章 + YouTube 字幕 + X/Twitter 帖子）由中心化服务每日抓取更新。

## 工作原理

1. 中心化 feed 每日更新，抓取所有信息源的最新内容（博客文章通过网页抓取，YouTube 字幕通过 Supadata，X/Twitter 通过官方 API）
2. 你的 agent 获取 feed——一次 HTTP 请求，不需要 API key
3. 你的 agent 根据你的偏好将原始内容重新混编为易消化的摘要
4. 摘要推送到你的通讯工具（或直接在聊天中显示）

查看 [examples/sample-digest.md](examples/sample-digest.md) 了解输出示例。

## 隐私

- 不发送任何 API key——所有内容由中心化服务获取
- 如果你使用 Telegram/邮件推送，相关 key 仅存储在本地 `~/.follow-builders/.env`
- Skill 只读取公开内容（公开的博客文章、YouTube 视频和 X 帖子）
- 你的配置、偏好和阅读记录都保留在你自己的设备上

## 许可证

MIT
