# 小红书文案 Skill

[简体中文](./README.md) | [English](./README.en.md) | 日本語

> 👉 こちらもどうぞ [小红书封面制作 Skill](https://github.com/beatra-ai/xiaohongshu-cover-maker-skill)

商品、体験、テーマ、読者層のブリーフから、小紅書のタイトル案、読みやすい本文、カバー文、ハッシュタグ、自然な最初のコメント案を作成。Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw のどれからでもそのまま使えます。

> [!IMPORTANT]
> 生成には [Beatra](https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=xiaohongshu-copywriter-skill) アカウントが必要で、クレジットを消費します。スキル自体のインストールは無料です。

| 項目 | 内容 |
| --- | --- |
| **できること** | 商品、体験、投稿テーマ、想定読者から、小紅書のタイトル、本文、表紙コピー、ハッシュタグ、自然なコメント案を整えます。 |
| **モデル** | Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro、MiniMax Image 01 Live |
| **動作要件** | Python 3.10 以上と、`SKILL.md` を読み込めるエージェント |
| **費用** | インストールは無料。生成のたびに Beatra アカウントのクレジットを消費しますが、課金されるのは、その生成を明示的に依頼したとき、または確認カードを承認したときだけです。 |
| **対応エージェント** | Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw |

<p align="center"><img src="assets/hero.webp" width="800" alt="架空のポータブルコーヒーミル DOUSHI の小紅書ノート：コピーはこのスキルが書き、カバー写真は Beatra AI で生成。"></p>

*架空のポータブルコーヒーミル DOUSHI の小紅書ノート：コピーはこのスキルが書き、カバー写真は Beatra AI で生成。*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`zhongcao-note-copywriter`](skills/zhongcao-note-copywriter) | [SKILL.md](skills/zhongcao-note-copywriter/SKILL.md) | 0.2.6 |

このリポジトリは [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/zhongcao-note-copywriter) から自動的に公開されています。問題の報告はそちらへお願いします。

## インストール

[`skills`](https://skills.sh) CLI を使う場合：

```bash
npx skills add beatra-ai/xiaohongshu-copywriter-skill
```

GitHub CLI を使う場合：

```bash
gh skill install beatra-ai/xiaohongshu-copywriter-skill zhongcao-note-copywriter
```

または、このリポジトリをクローンして `skills/zhongcao-note-copywriter` を次の場所にコピーします：Claude Code は `~/.claude/skills/`、Cursor は `~/.cursor/skills/`、Codex は `~/.agents/skills/`、Windsurf は `~/.codeium/windsurf/skills/`、Cline は `~/.cline/skills/`、OpenClaw は `~/.openclaw/skills/`。

または、次の文をエージェントに貼り付けてください：

```text
https://github.com/beatra-ai/xiaohongshu-copywriter-skill から zhongcao-note-copywriter スキル（フォルダ skills/zhongcao-note-copywriter）をインストールし、その SKILL.md に従って私の Beatra アカウントに接続してください。
```

## 技術仕様と出力上限

2026-10-18 時点。最新の一覧：https://docs.beatra.ai/ja/docs/models

- **テキストから画像** — 10 モデル（Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro、MiniMax Image 01 Live）／PNG／1 リクエストあたり最大 4 枚／キャンバス最大 16.8 MP
  - 16.8 MP（4K ティア）：Wan Image 2.7 Pro（1 リクエストあたり最大 4 枚）／GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2（1 リクエストにつき 1 枚）

## 得られるもの

- **タイトル5案から、ひとつを選ぶ** — フィードでの読まれ方を踏まえた5案を比べ、本命をひとつ選び、残りは次の投稿用に取っておけます。
- **読ませるリズムのある本文** — 短い段落、具体的なディテール、保存したくなる一文。指定したトーンで書き、テンプレートの言い回しに逃げません。
- **言い切りはあなたのもの** — 価格、実感、資格、体験はすべてあなたから。仕上がった文面は表現チェックを通し、アカウントとして背負えない言葉を残しません。

## 活用シーン

- **商品のおすすめ** — その商品が特定の読者の何を解決するのかを軸に、信じられるディテールを添えて書きます。
- **体験・来店レポート** — 来店、レッスン、旅、食事を一人称の投稿にし、読者が自分で行くときに必要な情報まで入れます。
- **ノウハウ・比較** — 使える部分が先に来るように構成し、保存する価値のある投稿にします。
- **お店・スポット紹介** — 店舗、スタジオ、場所を、たどり着ける具体情報と足を運ぶ理由とともに紹介します。
- **手元の画像にコピーをつける** — 他でつくった表紙やカルーセルに、文字と画像が同じことを語るように文字レイヤーを用意します。

## よくある質問

### テーマだけでも書けますか？

書けます。テーマがあれば下書きは作れますし、読者と伝えたい一点を添えるほど内容が絞り込まれます。

### 決まった言い回しは残せますか？

残せます。ブランド表現、商品名、必ず入れたい一文を指定すれば、そのままコピーに反映します。

### 商品の言い回しはどこから来ますか？

あなたからです。価格、実感、資格、体験は提供された事実をもとに書き、足りない点は質問として返ります。

### 別の言語でも書けますか？

書けます。言語を指定すれば、構成と分量の考え方はそのままに、その言語で仕上げます。

## 更新とセキュリティ

2026 年 10 月のリリース以降、このスキルに自動更新機能はありません。インストールしたファイルだけを実行し、
自動的に置き換えることはありません。更新はインストールに使ったツール（`npx skills update zhongcao-note-copywriter` または
`gh skill update zhongcao-note-copywriter`）で行ってください。詳細はスキル内の `references/updates-and-security.md` を参照してください。

## ライセンス

[MIT-0](LICENSE)：商用を含め、自由に使用・改変・再配布できます。クレジット表記は不要です。ClawHub 上のこれらのスキルと同じ条件です。

## リンク

- ウェブサイト — https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=xiaohongshu-copywriter-skill
- ドキュメント — https://docs.beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=xiaohongshu-copywriter-skill
- コンソール — https://console.beatra.ai
- AI エージェント向け — https://beatra.ai/llms.txt（インデックス）· https://beatra.ai/llms-full.txt（全スキルを 1 ファイルに）
