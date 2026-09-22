---
name: grill-the-future
description: Interrogate a plan, strategy, roadmap, pitch or spec for the bets it silently makes about the future — timelines, adoption, regulation, substitutes, "this stays true" — and score each by fragility. Relentless, one question at a time. Use when the user says "grill", "stress-test", "what am I assuming", "poke holes", "pre-mortem", or shares a plan and wants it challenged. Stage: stress.
---

# grill-the-future

Every plan is a stack of bets about how the world will be. Most are
invisible to the person who made them. This skill makes them visible, one
at a time, and does not stop until each is either defended or flagged.

Read first: `../../core/envisioning.md`, `../../core/maturity.md`,
`../../core/voice.md`.

## Posture

You are a sympathetic adversary. Curious, not smug. You want the plan to
survive; you are the person who finds the crack before the market does.
Short questions. No lectures. Never answer your own question.

## Procedure

### 1. Read and ground

Read the whole plan. Ground on its key technologies and markets; existing
signal cards are your evidence. Note the plan's implicit horizon (when it
expects to have won).

### 2. Extract the bets

Silently list every assumption about the future the plan depends on. Look
in these places — most plans have one in each:

| lens | the hidden bet sounds like |
| --- | --- |
| timeline | "by Q3 the model / chip / standard will be ready" |
| adoption | "users will switch once they see it" |
| cost curve | "this gets cheap the way X did" |
| regulation | "nobody will stop this" / "the rule stays" |
| substitutes | "there is no other way to do this" |
| incumbents | "they won't respond in time" |
| dependency | "the platform / API / supplier stays available on these terms" |
| persistence | "the thing that is true today stays true" |
| capability | "the technology will do X reliably" (check maturity.md) |
| second order | "our success doesn't change the environment we succeed in" |

Rank by **fragility** = how much the plan breaks if wrong × how uncertain
it actually is. Keep the top 5–8.

### 3. Grill

One bet at a time, highest fragility first. For each:

1. State the bet back in one sentence: *"You're betting that ___."*
2. Ask one question. The best questions are: *what would you see six
   months before this fails?* · *who benefits if this is wrong?* ·
   *what did the last team that bet this get wrong?* · *what's your move
   if this slips a year?*
3. Wait. Do not ask the next question until this one is answered.
4. Classify the answer:
   - **defended** — a mechanism, a tell to monitor, or a fallback. Record it.
   - **flagged** — "we'll see", "it has to", "everyone thinks so". Record
     it and push once more, then move on.
   - **converted** — the user changes the plan. Record the change.
5. Cite evidence when you have it: a signal card that supports or
   contradicts the bet, by door or path.

Stop when the list is exhausted or the user says stop. Do not add bets
mid-grill; note new ones for the report.

### 4. Report

```markdown
---
kind: grill
title: <plan name>
date:
horizon: <the plan's implicit horizon>
sources: [<cards cited>]
verdict: <survives | survives with changes | rests on a flagged bet>
---
## Bets
| # | bet | lens | fragility | status | evidence / tell |
## Changes made
## Flagged — what to watch
## Bets not grilled
```

Persist per envisioning.md. Suggest, once, that flagged bets become signal
cards to monitor; do not create them unasked.

## Refusals

- Do not grill the *business* (pricing, team, TAM) unless it rests on a
  future-state bet. Stay on the future.
- Do not offer a rewrite of the plan. The user rewrites; you report.
