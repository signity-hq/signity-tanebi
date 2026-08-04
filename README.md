# Tanebi（種火）— 会社の記憶からビジネス仮説を生む Claude スキル

**Tanebi** は、あなたの会社に既にある記録——議事録・決定ログ・顧客メモ・日報・失敗の教訓——を材料に、**検証可能なビジネス仮説**を生成し、反証で鍛え、最小の実地検証まで設計する Claude Code / Claude 用スキルです。

売れるプロダクトは「初期仮説→実地で当てる→学ぶ」の繰り返しから生まれます。人間の起業家がやっているこの過程を、AI と会社の記憶で回せるようにしたものです。

## 特徴

- **仮説は必須文型でしか書けない** — 「［顧客セグメント］は、［顧客課題＝すでにとっている行動］があるので、［解決策］を受け入れてくれるはずだ」。願望やアイデアの羅列は仮説として保存されません
- **机上と事実を混ぜない** — AI が生成したものはすべて「機会の仮説」。インタビューで確認されて初めて「機会」に昇格します
- **反証で鍛える** — 生成した仮説は独立の反証パスで潰しに行き、生き残ったものだけが提示されます。棄却された仮説も理由ごと保存され、次の材料になります
- **生成と実行の分離** — AI は仮説と検証設計まで。実地に当てる判断は必ず人間が行います

## インストール（Claude Code）

```bash
git clone https://github.com/Kenji-Natsumoto/tanebi.git ~/.claude/skills/tanebi
```

## 使い方

自社の記録があるプロジェクトで:

```
/tanebi 議事録と顧客メモ（./docs 配下）を材料に、新サービスの仮説を作って
```

または自然に「この記録から新規事業の初期仮説を立てて、検証計画まで作って」と頼むだけで起動します。

出力は `hypotheses/` ディレクトリに1仮説1ファイルの「仮説カード」として保存され、それぞれに実験（誰に・いつ・何を確かめるか）と成功／棄却基準が付きます。

## 構成

| ファイル | 内容 |
|---|---|
| `SKILL.md` | エンジン本体（5段パイプライン: 棚卸し→機会仮説スキャン→カード生成→反証→実地検証） |
| `references/doctrine.md` | 用語定義の正本（問題/課題/機会/仮説の階層・OST・運用ルールR1〜R6）。チームの用語正本としてそのまま採用可 |
| `references/card-template.md` | 仮説カードのテンプレートと記入例 |
| `references/interview-guide.md` | 実地検証（機会検証の30分対話）のガイド |

## 背景

このスキルは SPRINT Japan / signity が自社運営（AI と人間の協働による会社経営の実験）の中で実際に使っている仮説エンジンの公開版です。定義体系は、AI が「自社の問題」を「顧客の機会」として提示する誤りを実際に犯した経験から正本化されました。方法論の土台として Teresa Torres / Marty Cagan の Continuous Discovery（書籍 *Continuous Discovery Habits*）の考え方を参照しています。

## English summary

**Tanebi** ("ember" in Japanese) is a Claude skill that turns your company's existing records — meeting minutes, decision logs, customer notes, lessons from failures — into **testable business hypotheses**. Every hypothesis must fit a strict sentence form (segment / observed behavior / solution), is adversarially refuted before it reaches you, and ships with a minimal field-validation design. Generation is AI's job; pulling the trigger is always yours. Japanese-first for now; the doctrine in `references/doctrine.md` defines the full method.

## License

MIT License — see [LICENSE](LICENSE).

Built in public by [SPRINT Japan](https://sprintjapan.net) / signity.
