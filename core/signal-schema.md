# Signal card

The one format every skill reads and writes. Markdown, YAML frontmatter, no
other structure. Keep the body under 300 words; the card is a pointer, not
a report.

```markdown
---
kind: signal
title: <short, specific, present tense — "X is doing Y", not "The rise of Y">
date: <YYYY-MM-DD observed>
steep: <social | technological | economic | environmental | political>   # one
tech: [<canonical taxonomy names, or free text standalone>]
maturity: <core/maturity.md stage>
direction: <emerging | accelerating | plateauing | fading>
confidence: <low | medium | high>          # in the observation, not the future
horizon: <1 | 3 | 10>                       # years until it matters broadly
actors: [<who is moving>]
sources: [<url | document:<id> | ./path>]
subject: <core:kind:id, optional>
---

## What

Two sentences. The observable fact. No adjectives.

## So what

Three bullets. Why a strategist should care. Each bullet names who is affected.

## Watch for

Two or three concrete tells that would raise or lower `confidence` or move
`direction`.
```

## Rules

- A signal is an **observation**, not a trend or a prediction. If the title
  needs "will", it is not a signal.
- One signal per card. Two facts → two cards, cross-linked in `sources`.
- `confidence` is about the observation (did this happen, is the source
  solid). Future likelihood belongs to `scenarios`, not here.
- `horizon` is a guess; say so in `Watch for` if the guess is soft.
