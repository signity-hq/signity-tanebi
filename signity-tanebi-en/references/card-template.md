# Hypothesis Card Template

One hypothesis = one file. Save to `hypotheses/YYYY-MM-DD_<slug>.md`. The purpose of a card is that **a decision-maker can read the hypothesis sentence in 5 seconds and decide in 2 minutes whether to validate it**.

## Template

```markdown
---
generated: <YYYY-MM-DDTHH:MM:SS+TZ>
model: <model used for generation>
status: draft            # draft → approved candidate if it survives refutation / rejected if refuted / after field validation: supported | rejected | revised
refutation: not yet run  # survived (date, confidence) / rejected (date, confidence)
slug: <alphanumeric kebab-case; must match the filename>
---

# <Short name of the hypothesis>

> **Hypothesis**: [Customer segment] already [customer struggle = behavior they already engage in], so they should accept [solution].

| Field | Content |
|---|---|
| Customer segment | The subject. Real people or a real stratum. If it traces to a named person in the records, say so |
| Customer struggle (behavior) | Written as a **behavior they already engage in**. Wishes and feelings are not allowed |
| Opportunity provenance | Customer-interview-derived or desk-derived. If desk-derived, explicitly label it "opportunity hypothesis" |
| Solution | Minimal form. One card, one solution |
| Experiment | Who, when, and what you will do to check. Down to the specific person and venue |
| Success criteria | A number and a deadline (e.g. confirm the behavior actually exists with N people by MM/DD) |
| Rejection criteria | A number and a deadline (e.g. reject if N conversations surface zero instances of the behavior) |
| Evidence | Links to and quotes from the record files consulted |
| Risk and reversibility | Does the experiment have external effects? If so, state explicitly that human approval is required |

## Refutation result (appended in Step 4)

Verdict: survived / rejected (confidence high/medium/low)
1. Segment existence: …
2. Behavior existence (swap-in check): …
3. Contamination by our own problems: …
4. Willingness to pay and feasibility: …

If survived → weave the "conditions for survival" into the experiment design.
If rejected → record the "facts required for revival" and keep the card.

## Field validation result (appended in Step 5)

Date, who, behaviors confirmed, what could not be confirmed, verdict (supported / rejected / revised), where the learning was written back
```

## Worked example (fictional, desk-derived)

```markdown
> **Hypothesis**: Small professional practices that hand-build a monthly newsletter for their advisory clients
> already spend several hours each month assembling the copy in Word,
> so they should accept a service that auto-drafts each issue from past issues and client records.

| Customer segment | Tax accountants and labor consultants with fewer than 20 advisory clients (in our records: Dr. C) |
| Customer struggle (behavior) | Spends 3–4 hours at each month-end hand-building the newsletter in Word (observed in customer notes, 2026-06) |
| Opportunity provenance | Desk-derived = **opportunity hypothesis** (Dr. C's behavior comes from records; not yet confirmed with the person) |
| Experiment | At the next regular meeting with Dr. C (2nd week of July), spend 30 minutes asking how the latest issue was made. No pitching |
| Success criteria | By end of July, hear "3+ hours a month on production" from the person directly, and be shown the actual artifact |
| Rejection criteria | Reject if 2 conversations yield "actually it doesn't bother me / already outsourced" |
```

**Guard, restated**: a card missing any of the four elements of the hypothesis sentence (segment, behavior, solution, experiment), or lacking rejection criteria, is not saved. The very fact that a blank cannot be filled is itself the signal that "it is not yet time to form a hypothesis."
