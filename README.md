# 小红书文案 Skill

简体中文 | [English](./README.en.md)

把商品、体验、选题或受众信息整理成小红书标题、笔记正文、首图文案、话题标签和自然的评论互动引导，在 Claude Code、Codex 或 OpenClaw 里直接完成。

> [!IMPORTANT]
> 生成需要 [Beatra](https://beatra.ai) 账号并消耗积分，安装本身不收费。

| 问题 | 回答 |
| --- | --- |
| **能做什么** | 把商品、体验、选题或受众信息整理成小红书标题、笔记正文、首图文案、话题标签和自然的评论互动引导。 |
| **运行要求** | Python 3.10+，以及能加载 `SKILL.md` 的 Agent |
| **费用** | 安装免费。每次生成消耗 Beatra 账号积分，只有你明确要求这次生成或批准确认卡后才会付费。 |
| **支持的 Agent** | Claude Code、Codex、OpenClaw |

<p align="center"><img src="assets/hero.webp" width="800" alt="虚构品牌「豆拾 DOUSHI」手摇磨豆机的小红书笔记：文案由 Skill 生成，封面图由 Beatra AI 生成。"></p>

*虚构品牌「豆拾 DOUSHI」手摇磨豆机的小红书笔记：文案由 Skill 生成，封面图由 Beatra AI 生成。*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`zhongcao-note-copywriter`](skills/zhongcao-note-copywriter) | [SKILL.md](skills/zhongcao-note-copywriter/SKILL.md) | 0.2.4 |

本仓库由 [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/zhongcao-note-copywriter) 自动发布，问题请到那里反馈。

## 安装

使用 [`skills`](https://skills.sh) CLI：

```bash
npx skills add beatra-ai/xiaohongshu-copywriter-skill
```

使用 GitHub CLI：

```bash
gh skill install beatra-ai/xiaohongshu-copywriter-skill zhongcao-note-copywriter
```

也可以克隆本仓库，把 `skills/zhongcao-note-copywriter` 复制到 `~/.claude/skills/`（Claude Code）、`~/.agents/skills/`（Codex）或 `~/.openclaw/skills/`（OpenClaw）。

或者把下面这段话发给你的 Agent：

```text
从 https://github.com/beatra-ai/xiaohongshu-copywriter-skill 安装 zhongcao-note-copywriter skill（目录 skills/zhongcao-note-copywriter），然后按它的 SKILL.md 连接我的 Beatra 账号。
```

## 技术规格与输出限制

截至 2026-10-16。实时列表：https://docs.beatra.ai/zh/docs/models

- **文生图** — 10 个模型（Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro、MiniMax Image 01 Live）；PNG；单次最多 4 张；画布最大 16.8 MP
  - 16.8 MP（4K 档）：Wan Image 2.7 Pro（单次最多 4 张）；GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2（单次 1 张）

## 为什么用 Beatra，而不是直接调用模型 API

- **一个账号用到本 skill 的全部模型** — 文生图 10（截至 2026-10-16），一次 Beatra 登录即可使用，不必分别管理各家模型的 key。
- **花不花钱由你决定** — 只有你明确要求这次生成，或批准显示实时积分估算的确认卡后才会付费。
- **先策划，再生成** — skill 先帮你规划、指导和检查，再在 Beatra 上生成。
- **文件可以核验** — `skills/` 下的每个文件都与 cdn.beatra.ai 上的发布归档逐字节一致，每次推送前用 SHA-256 校验。
- **更新由你掌控** — 不含自更新程序；用安装时的工具更新。
- **在你的 Agent 里运行** — Claude Code、Codex、OpenClaw。

## 你能得到什么

- **5 个标题，选定一个** — 给出 5 个按信息流阅读习惯写的标题，选一个做主标题，其余留给下一篇。
- **正文有真实的节奏** — 短段落、具体细节、值得收藏的那一句，按你要的语气写，而不是套模板。
- **说法都归你** — 价格、效果、资质和亲身体验都来自你；成稿还会过一遍措辞筛查，不让账号担不起的话留在笔记里。

## 适用场景

- **商品种草** — 围绕商品对某一类读者到底解决了什么写推荐，把让人信得过的细节写进去。
- **体验与探店** — 把一次到店、一堂课、一段旅行或一顿饭写成第一人称笔记，带上读者自己去时用得上的信息。
- **干货与攻略** — 把教程或对比的结构排好，让有用的部分先出现，笔记值得被收藏。
- **同城好去处** — 介绍一家店、一间工作室或一个地方，写清到得了的细节和值得跑一趟的理由。
- **给已有图集配文案** — 为你在别处做好的封面和图集补上文字层，让文字和画面讲的是同一件事。

## 常见问题

### 只有一个选题也能写吗？

可以。有选题就能起草；再说清读者和要传达的那一个点，笔记会更聚焦。

### 能保留指定的措辞吗？

可以。把品牌用语、商品名称或必须出现的那句话标为必须保留，文案里会原样写进去。

### 商品说法从哪里来？

来自你。价格、效果、资质和亲身体验都按你提供的事实来写；缺了哪一条，会先来问你要。

### 可以写成别的语言吗？

可以。指定语言即可，结构和篇幅要求保持一致。

## 更新与安全

自 2026 年 10 月的版本起，本 skill 不再包含自更新程序：它只运行你安装的文件，从不自行替换。
请用安装时的工具更新——`npx skills update zhongcao-note-copywriter` 或 `gh skill update zhongcao-note-copywriter`。
详见 skill 内的 `references/updates-and-security.md`。

## 许可证

[MIT-0](LICENSE)：可自由使用、修改和再分发，包括商用，无需署名；与这些 skill 在 ClawHub 上的条款一致。

## 相关链接

- 官网 — https://www.beatra.cn
- 文档 — https://docs.beatra.cn
- 控制台 — https://console.beatra.cn
- 给 AI Agent 读的说明 — https://www.beatra.cn/llms.txt（索引）· https://www.beatra.cn/llms-full.txt（全部 skill 合成一个文件）

- 微信小程序 — 国内用户微信扫码使用

<img src="assets/beatra-mini-program-qr.jpg" alt="Beatra 微信小程序码" width="160">
