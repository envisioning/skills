---
name: implications
description: Cascade the consequences of a change — first, second and third order — as a futures wheel, with who is affected at each ring and where the cascades collide. Use when the user asks "what happens if", "what are the implications", "second-order effects", "knock-on effects", or has signal cards and wants to see what they lead to. Stage: structure.
---

# implications

A futures wheel, done rigorously: every consequence has an actor, a
mechanism and a ring. The value is in the third ring and the collisions,
not the obvious first ring.

Read first: `../../core/envisioning.md`, `../../core/signal-schema.md`,
`../../core/voice.md`.

## Input

One of: a signal card (path or door), a plain statement of change, or a
topic. If it is a topic, ground first and build from the cards found; if
none exist, run `signal` on the best source before continuing.

## Procedure

1. **State the change** in one sentence, present tense, as the hub.
2. **Ring 1 — direct.** 4–6 consequences that follow with no intermediary.
   Each: `<consequence> — <actor affected> — <mechanism>`. Mechanism is the
   causal verb: substitutes, cheapens, requires, exposes, enables, removes.
3. **Ring 2 — responses.** For each ring-1 item, 1–3 things actors *do* in
   response. Responses, not effects: someone decides something.
4. **Ring 3 — systemic.** For each ring-2 item, what changes in the
   system when many actors respond that way. This is where norms, prices,
   laws and defaults move.
5. **Collisions.** Find pairs of ring-2/ring-3 items that reinforce or
   oppose each other. Name each collision; these are the scenario seeds.
6. **Prune.** Delete anything that is generic enough to appear under any
   change ("regulation increases"). If a branch has no named actor, cut it.
7. **Tells.** For the three most consequential branches, one observable
   that would confirm the branch is live.
8. **Persist** per envisioning.md, `sources[]` naming the input cards.

## Output

```markdown
---
kind: implications
title: <hub statement>
date:
sources: [<cards>]
tech: []
---
## Hub
## Ring 1 · direct
## Ring 2 · responses
## Ring 3 · systemic
## Collisions
## Tells
```

Rings as nested bullets, actor and mechanism inline. Under 600 words.
Collisions in a table: `a | b | reinforce/oppose | why it matters`.

## Refusals

If the change is too vague to have a ring 1 with actors ("AI gets better"),
ask for the specific observable, or run `signal` on it first.
