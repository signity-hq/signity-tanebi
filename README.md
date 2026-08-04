# signity Tanebi（種火）

**日本語 | [English below](#english)**

**signity Tanebi** は、会社に既にある記録——議事録・決定ログ・顧客メモ・日報・失敗の教訓——を材料に、**検証可能なビジネス仮説**を生成し、反証で鍛え、最小の実地検証まで設計する Claude Code / Claude 用スキルです。

売れるプロダクトは「初期仮説→実地で当てる→学ぶ」の繰り返しから生まれます。人間の起業家がやっているこの過程を、AI と会社の記憶で回せるようにしました。「Tanebi」は種火——会社の記憶という熾火から、検証可能な仮説の火を起こす、という意味です。

## 特徴

- **仮説は必須文型でしか書けない** — 「［顧客セグメント］は、［顧客課題＝すでにとっている行動］があるので、［解決策］を受け入れてくれるはずだ」。願望やアイデアの羅列は仮説として保存されません
- **机上と事実を混ぜない** — AI が生成したものはすべて「機会の仮説」。インタビューで確認されて初めて「機会」に昇格します
- **反証で鍛える** — 生成した仮説は独立の反証パスで潰しに行き、生き残ったものだけが提示されます。棄却された仮説も理由ごと保存されます
- **生成と実行の分離** — AI は仮説と検証設計まで。実地に当てる判断は必ず人間が行います

## インストール（日本語版）

```bash
git clone https://github.com/Kenji-Natsumoto/signity-tanebi.git /tmp/signity-tanebi && cp -r /tmp/signity-tanebi/signity-tanebi-ja ~/.claude/skills/signity-tanebi
```

## 使い方

自社の記録があるプロジェクトで、「この記録から新規事業の初期仮説を立てて、検証計画まで作って」と頼むだけで起動します。出力は `hypotheses/` に1仮説1ファイルの「仮説カード」として保存され、実験（誰に・いつ・何を確かめるか）と成功／棄却基準が付きます。

| ファイル | 内容 |
|---|---|
| `SKILL.md` | エンジン本体（棚卸し→機会仮説スキャン→カード生成→反証→実地検証の5段） |
| `references/doctrine.md` | 用語定義の正本（問題/課題/機会/仮説・OST・R1〜R6）。チームの用語正本としてそのまま採用可 |
| `references/card-template.md` | 仮説カードのテンプレートと記入例 |
| `references/interview-guide.md` | 実地検証（機会検証の30分対話）のガイド |

---

<a name="english"></a>
# signity Tanebi — English

**signity Tanebi** ("tanebi" means *ember* in Japanese) is a Claude Code / Claude skill that turns your company's existing records — meeting minutes, decision logs, customer notes, lessons from failures — into **testable business hypotheses**, hardens them through adversarial refutation, and designs the smallest possible field validation for each survivor.

## What makes it different

- **Hypotheses must fit a required sentence form** — "[Customer segment] already [observed behavior], so they should accept [solution]." Wishes and idea lists are not saved as hypotheses
- **Desk work is never confused with facts** — everything the AI generates is an *opportunity hypothesis*; it is only promoted to an *opportunity* after interview evidence confirms the behavior
- **Adversarial refutation built in** — every generated hypothesis is attacked by an independent refutation pass; only survivors reach you, and rejected cards are kept with their rejection reasons
- **Generation and execution stay separate** — the AI designs hypotheses and experiments; a human always decides what touches the real world

## Install (English edition)

```bash
git clone https://github.com/Kenji-Natsumoto/signity-tanebi.git /tmp/signity-tanebi && cp -r /tmp/signity-tanebi/signity-tanebi-en ~/.claude/skills/signity-tanebi
```

Then, in any project that holds your company records: *"Form initial hypotheses for a new business from these records, with a validation plan."* Hypothesis cards are saved under `hypotheses/`, each with an experiment and explicit success / rejection criteria.

## Background

signity Tanebi is the public edition of the hypothesis engine used inside SPRINT Japan / signity's own AI-native company operations. The doctrine was canonized after an AI presented a *company problem* as a *customer opportunity* — the exact failure this skill is built to prevent. Methodological foundations: Teresa Torres / Marty Cagan, *Continuous Discovery Habits*.

## License

MIT — see [LICENSE](LICENSE). Built in public by [SPRINT Japan](https://sprintjapan.net) / signity.
