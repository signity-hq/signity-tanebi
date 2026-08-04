# Signity Tanebi（種火）— 日本語版

> 本ドキュメントはローカライズ版です。**正本は英語版（[README.md](README.md)・`signity-tanebi-en/`）**——記述が食い違う場合は英語版が優先されます。

**Signity Tanebi** は、会社に既にある記録——議事録・決定ログ・顧客メモ・日報・失敗の教訓——を材料に、**検証可能なビジネス仮説**を生成し、反証で鍛え、最小の実地検証まで設計する Claude Code / Claude 用スキルです。

売れるプロダクトは「初期仮説→実地で当てる→学ぶ」の繰り返しから生まれます。人間の起業家がやっているこの過程を、AI と会社の記憶で回せるようにしました。「Tanebi」は種火——会社の記憶という熾火から、検証可能な仮説の火を起こす、という意味です。

> **ひとつのスキルが、主要エージェントすべてで動きます。** Signity Tanebi は**エージェント業界標準のスキル**です——業界標準形式「Agent Skills オープン標準」（`SKILL.md`）に準拠し、**Claude Code・Claude アプリ・OpenAI Codex・xAI Grok Build** でそのまま使えます。各ツールの導入方法は下記のインストール節へ。

## 特徴

- **仮説は必須文型でしか書けない** — 「［顧客セグメント］は、［顧客課題＝すでにとっている行動］があるので、［解決策］を受け入れてくれるはずだ」。願望やアイデアの羅列は仮説として保存されません
- **机上と事実を混ぜない** — AI が生成したものはすべて「機会の仮説」。「<a href="https://sprintjapan.com/articles/hypothesis-verification/" target="_blank" rel="noopener">顧客インタビュー</a>」で確認されて初めて「機会」に昇格します
- **反証で鍛える** — 生成した仮説は独立の反証パスで潰しに行き、生き残ったものだけが提示されます。棄却された仮説も理由ごと保存されます
- **生成と実行の分離** — AI は仮説と検証設計まで。実地に当てる判断は必ず人間が行います
- **エージェント業界標準・ベンダー非依存** — Agent Skills オープン標準形式のフォルダひとつが、Claude・OpenAI Codex・xAI Grok Build で無変更のまま動きます。あなたの会社の仮説の規律は、特定のAIベンダーに縛られません

## インストール（日本語版）

### Claude Code（CLI）

```bash
git clone https://github.com/signity-hq/signity-tanebi.git /tmp/signity-tanebi && cp -r /tmp/signity-tanebi/signity-tanebi-ja ~/.claude/skills/signity-tanebi
```

### Claude アプリ（デスクトップ / Web）

1. [最新リリース](https://github.com/signity-hq/signity-tanebi/releases/latest)から `signity-tanebi-ja.zip` をダウンロード
2. Claude の **設定 → カスタマイズ → スキル → 「+ スキルを作成」**（または [claude.ai/customize/skills](https://claude.ai/customize/skills) に直接アクセス）で、ZIPをそのままアップロード
3. カスタムスキルは有料プラン（Pro / Max / Team / Enterprise）＋コード実行が有効な場合に使えます。claude.ai に登録したスキルはデスクトップアプリにも自動で同期されます

### OpenAI Codex・xAI Grok Build ほか Agent Skills 対応ツール

Signity Tanebi は **Agent Skills オープン標準**（`SKILL.md`）に準拠しており、Claude 以外の主要エージェントでも使えます。

OpenAI Codex（`~/.agents/skills/` から自動読み込み）:

```bash
git clone https://github.com/signity-hq/signity-tanebi.git /tmp/signity-tanebi && cp -r /tmp/signity-tanebi/signity-tanebi-ja ~/.agents/skills/signity-tanebi
```

xAI Grok Build は Claude 互換の `SKILL.md` パックをそのまま読めます——同じフォルダをスキルディレクトリに置けば次セッションから有効です。反証（Step 4）は、サブエージェントが無いツールでは自動的に「視点を切り替えた自己反証」へ縮退する設計なので、どの環境でもパイプラインは一周します。

## 使い方

自社の記録があるプロジェクトで、「この記録から新規事業の初期仮説を立てて、検証計画まで作って」と頼むだけで起動します。出力は `hypotheses/` に1仮説1ファイルの「仮説カード」として保存され、実験（誰に・いつ・何を確かめるか）と成功／棄却基準が付きます。

| ファイル | 内容 |
|---|---|
| `SKILL.md` | エンジン本体（棚卸し→機会仮説スキャン→カード生成→反証→実地検証の5段） |
| `references/doctrine.md` | 用語定義の正本（問題/課題/機会/仮説・OST・R1〜R6）。チームの用語正本としてそのまま採用可 |
| `references/card-template.md` | 仮説カードのテンプレートと記入例 |
| `references/interview-guide.md` | 実地検証（機会検証の30分対話）のガイド |

## 背景

Signity Tanebi は、SPRINT Japan / signity が自社運営（AIと人間の協働による会社経営の実験）の中で実際に使っている仮説エンジンの公開版です。この定義体系は、AIが「自社の問題」を「顧客の機会」として提示する誤りを実際に犯した経験から正本化されました。方法論の土台: Teresa Torres / Marty Cagan『Continuous Discovery Habits』。

## ライセンス

MIT — [LICENSE](LICENSE) 参照。Built in public by [signity](https://signityos.io) / [SPRINT Japan](https://sprintjapan.net).
