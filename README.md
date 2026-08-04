# Signity Tanebi

**English (canonical) | [日本語版はこちら](README.ja.md)**

**Signity Tanebi** ("tanebi" means *ember* in Japanese) is a Claude Code / Claude skill that turns your company's existing records — meeting minutes, decision logs, customer notes, daily reports, lessons from failures — into **testable business hypotheses**, hardens them through adversarial refutation, and designs the smallest possible field validation for each survivor.

Products that sell are born from the loop every founder runs by hand: form an initial hypothesis, test it in the field, learn, repeat. Signity Tanebi lets AI run that loop on top of your company's memory — while a human always pulls the trigger.

## What makes it different

- **Hypotheses must fit a required sentence form** — "[Customer segment] already [observed behavior], so they should accept [solution]." Wishes and idea lists are not saved as hypotheses
- **Desk work is never confused with facts** — everything the AI generates is an *opportunity hypothesis*; it is only promoted to an *opportunity* after customer-interview evidence confirms the behavior
- **Adversarial refutation built in** — every generated hypothesis is attacked by an independent refutation pass; only survivors reach you, and rejected cards are kept with their rejection reasons
- **Generation and execution stay separate** — the AI designs hypotheses and experiments; a human always decides what touches the real world

## Install

English edition (canonical):

```bash
git clone https://github.com/signity-hq/signity-tanebi.git /tmp/signity-tanebi && cp -r /tmp/signity-tanebi/signity-tanebi-en ~/.claude/skills/signity-tanebi
```

Japanese localized edition:

```bash
git clone https://github.com/signity-hq/signity-tanebi.git /tmp/signity-tanebi && cp -r /tmp/signity-tanebi/signity-tanebi-ja ~/.claude/skills/signity-tanebi
```

## Usage

In any project that holds your company records: *"Form initial hypotheses for a new business from these records, with a validation plan."* Hypothesis cards are saved under `hypotheses/`, each with an experiment and explicit success / rejection criteria.

| File | Contents |
|---|---|
| `SKILL.md` | The engine itself (5 stages: inventory → opportunity-hypothesis scan → card generation → refutation → field validation) |
| `references/doctrine.md` | The terminology canon (problem / task / opportunity / hypothesis, OST, rules R1–R6). Teams may adopt it as-is |
| `references/card-template.md` | Hypothesis card template with a filled example |
| `references/interview-guide.md` | The 30-minute opportunity-validation interview guide |

## Editions

The **English edition (`signity-tanebi-en/`) is canonical**. The Japanese edition (`signity-tanebi-ja/`) is a localized edition kept in sync with it; if the two ever diverge, the English edition governs.

## Background

Signity Tanebi is the public edition of the hypothesis engine used inside SPRINT Japan / signity's own AI-native company operations. The doctrine was canonized after an AI presented a *company problem* as a *customer opportunity* — the exact failure this skill is built to prevent. Methodological foundations: Teresa Torres / Marty Cagan, *Continuous Discovery Habits*.

## License

MIT — see [LICENSE](LICENSE). Built in public by [signity](https://signityos.io) / [SPRINT Japan](https://sprintjapan.net).
