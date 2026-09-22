---
name: scenarios
description: Build a 2x2 scenario set from a topic or a set of signals — extract critical uncertainties, pick the two that matter, name four scenarios, and give each one tells and a strategic posture. Use when the user asks "what could happen", "scenarios for", "possible futures", "how might this play out", or wants to plan against uncertainty rather than a forecast. Stage: project.
---

# scenarios

Four futures that are each plausible, distinct and useful. The 2x2 is a
constraint, not a template: the work is choosing the axes.

Read first: `../../core/envisioning.md`, `../../core/signal-schema.md`,
`../../core/voice.md`.

## Input

A focal question, a horizon (default 10 years), and signal cards. If the
user gives a topic without cards, ground; if fewer than three cards exist,
say so and either run `signal` on sources they provide or proceed with a
`grounding: thin` flag in frontmatter.

## Procedure

1. **Focal question.** One sentence, decision-shaped: "How should <actor>
   position for <domain> by <year>?" Not "What is the future of X."
2. **Driving forces.** From the cards and grounding, list 8–12 forces.
   Each one: name, current direction, STEEP layer, which cards support it.
3. **Sort by impact × uncertainty.** High impact + low uncertainty →
   *predetermined elements*: true in every scenario, listed once, not an
   axis. High impact + high uncertainty → axis candidates.
4. **Choose two axes.** Must be independent (knowing one tells you nothing
   about the other) and each must have two genuinely different poles. Write
   the poles as states, not as "more/less". Reject an axis if all four
   resulting quadrants would recommend the same action.
5. **Name four scenarios.** Names are two or three words, evocative, no
   puns. For each:
   - *Narrative* — 120–180 words in the present tense of the horizon year.
   - *How we got here* — three dated events between now and then.
   - *Who wins, who loses* — named actor types.
   - *Tells* — two early indicators, observable within 18 months, that this
     quadrant is becoming more likely.
   - *Posture* — what the focal actor should do *if* this is where it goes.
6. **Robust moves.** Actions that are sensible in three or four quadrants.
   This is the deliverable most readers want; give it its own section.
7. **Persist** per envisioning.md.

## Output

```markdown
---
kind: scenarios
title: <focal question>
horizon: <year>
axes:
  - { name:, low:, high: }
  - { name:, low:, high: }
sources: [<cards>]
grounding: <ok | thin>
---
## Focal question
## Predetermined elements
## Axes
## Scenarios
### <name> (<axis1 pole> × <axis2 pole>)
## Robust moves
## Tells to monitor   ← all eight in one table
```

## Refusals

- Do not produce "good / bad / status quo / wildcard" — that is not a 2x2.
- Do not assign probabilities to quadrants. Scenarios are for rehearsal,
  not forecasting; say so if asked.
