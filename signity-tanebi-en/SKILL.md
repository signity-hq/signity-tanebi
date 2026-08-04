---
name: signity-tanebi
description: signity Tanebi — a hypothesis engine that turns company records (meeting minutes, decision logs, customer notes, daily reports, lessons from failures) into testable business hypotheses, hardens them with adversarial refutation, and designs the minimal field validation. Always use this skill when forming early hypotheses for a new business, service, or feature, or when asked to "form a hypothesis", "think up a new business", "find opportunities in our records", or "prep for customer interviews". Use it for idea generation and brainstorming too, whenever the output should ultimately land as something testable.
version: 1.0.0
---

# signity Tanebi — Hypothesis Engine

A company's memory is a bed of live coals. Decision records, notes from customer conversations, lessons from failures — buried in them are seeds of businesses that have never been tested. signity Tanebi ("tanebi" is Japanese for an ember — the small seed fire you carry to start a new one) raises from those coals a **tanebi: a testable business hypothesis**, hardens it with refutation, and designs the minimal field validation.

**Prime directive: separation of generation and execution.** signity Tanebi produces the hypothesis and the validation design — nothing more. The decision to take it into the field (meeting a customer, sending, publishing, spending money) is made by a human, every single time. Never perform any operation inside this skill that sends externally, publishes, or spends.

## Foundational doctrine (applies to every step — no deviation)

Always read [references/doctrine.md](references/doctrine.md) for the full definitions and the reasons behind them. The essentials:

1. **The required sentence form for a hypothesis**: "**[Customer segment] already [customer struggle = behavior they already engage in], so they should accept [solution].**" Anything that cannot be written in this form is not called a hypothesis
2. **An "everyday annoyance" is not a "customer struggle."** A customer struggle is a behavior they **already engage in** to overcome an anxiety or inconvenience. Collecting wishes and complaints is not observing a struggle
3. **Only interview-derived facts may be called "opportunities."** Everything generated from records is desk-derived and must be labeled an "**opportunity hypothesis**." It is promoted to "opportunity" only after field validation confirms it
4. **Keep two separate trees.** Do not mix the customer tree (outcome → opportunity → solution → experiment) with the business tree (problem → task → to-do). KPIs and internal metrics belong on the business side
5. **"We don't know / we can't measure" is not an opportunity — it is our own problem.** Do not turn it into a hypothesis; route it out as a to-do
6. **Do not hypothesize everything.** An operational defect is a to-do, not a hypothesis

## Procedure (one session = Steps 0–4)

### Step 0 — Confirm scope
Confirm with the user where the source records live (e.g. meeting minutes, decision logs, customer notes, daily reports, CRM exports, records of failures). If nothing is specified, explore the project, present the candidates you find, and get agreement. If the records are thin, say so honestly — **the thinner the material, the more desk-derived the hypotheses become** — so generate fewer cards and state the weak provenance on each card.

### Step 1 — Inventory
Read the specified records. Pay particular attention to three kinds of material: **observed behavior** (what customers actually did and paid for), **failures and lessons** (withdrawals, price cuts, records of being turned down), and **people and accounts** (who is struggling with what, and what they are doing about it).

### Step 2 — Opportunity-hypothesis scan
Generate "opportunity hypotheses" from **intersections** between records. Productive intersection patterns: customer behavior × our own lessons; past failures × market shifts; existing products × unanswered inquiries sitting in the records. Sort everything you produce into two lanes:
- **Customer side** (rooted in customer behavior) → proceed to Step 3
- **Our own problems** (the "we don't know" / "revenue is short" type) → do not hypothesize; route out to a separate to-do lane

**Enter through customer outcome → opportunity, never through the solution.** The pattern of starting with something we want to sell and retrofitting a segment must be consciously detected at the scan stage and honestly recorded in the card's "provenance" field.

### Step 3 — Hypothesize (generate cards)
One hypothesis = one file. Save to `hypotheses/YYYY-MM-DD_<slug>.md` (create the directory if it does not exist). Use the template and worked example in [references/card-template.md](references/card-template.md).

**Save-refusal guard** (why it exists: to drop weak hypotheses before they reach a decision-maker's time):
- Does not fill the required sentence form (any of customer segment, behavior, solution, or experiment is missing) → do not save
- No rejection criteria (a number or a deadline) → do not save. **A hypothesis that cannot be rejected is not validation — it is wishful thinking**
- Contains our own problem → if it cannot be rewritten in the customer-side sentence form, route it to the to-do lane

### Step 4 — Refute
Deliberately try to **kill** every card you generated. In environments where subagents are available, spawn an independent refutation agent per card (fresh eyes with no memory of the generating context sharpen the refutation). Where subagents are not available, explicitly switch to a viewpoint separate from generation and self-refute.

Four angles: (1) Does the customer segment actually exist, and is there a path to reach it? (2) Is the customer struggle observed as **behavior** — check for the swap-in of an "everyday annoyance" (3) Contamination by our own problems or our own convenience (4) Grounds for willingness to pay, and feasibility within the time and capacity of the human who would execute.

Append the verdict (survived / rejected) and the reasoning to the card. **Do not delete rejected cards — keep them, together with the rejection reasons and the "facts required for revival"** — the record of rejections is raw material for the next scan.

### Wrap-up — Batch report
Report the counts (generated / survived / rejected) and the gist of the reasons, and for each surviving card present the "next step = minimal field validation." Whether to carry it out is a human decision. Hand over [references/interview-guide.md](references/interview-guide.md) as the conversation pattern for field validation.

### Step 5 — Field validation → imprint (after approval, in a separate session)
Once the human has run the field validation (interview, etc.), append the results to the card and settle the verdict: **supported / rejected / revised**. An "opportunity hypothesis" whose behavior was confirmed to exist in an interview is promoted — only here — to an "opportunity." Write the learning back into the records (lessons files, etc.) — **one full cycle includes this step**; stopping at generation delivers only half the value of this skill.

## Output conventions

- The hypothesis sentence always appears as a single bold sentence at the top of the card (so a reader can judge it in 5 seconds)
- Report survival and rejection honestly. If everything died, say everything died — **one strong survivor is worth more than a crowd of pretend survivors**
- When prompting field validation, get concrete down to the specific person, venue, and time required ("ask someone" is not an experiment)
