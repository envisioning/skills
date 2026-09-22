---
name: frames
description: Synthesize a set of signal cards into frames — named narrative groupings such as drivers of change, tensions, or emerging themes — each with a title, summary, body and the signals it binds, many-to-many. Use when the user asks "what are the themes", "drivers of change", "cluster these signals", "what's the story here", "frames", or needs the layer between raw signals and a report. Stage: structure.
---

# frames

A frame is a narrative that several signals belong to. Frames are how a
scan becomes readable without losing the cards underneath: every claim in
a frame points back to the signals that support it.

Read first: `../../core/signal-schema.md`, `../../core/envisioning.md`,
`../../core/voice.md`.

## Input

Active signal cards (a scan index, folder, or list; frozen `merged_into`
cards are skipped), and a **frame kind**. Default kinds:

| kind | a frame is… | good count |
| --- | --- | --- |
| `drivers` | a force pushing the scope in one direction | 4–7 |
| `tensions` | two forces pulling against each other | 3–5 |
| `themes` | a pattern several signals share | 5–8 |
| `bets` | a claim the corpus supports that a strategist could act on | 3–5 |

The user can name another kind; write its definition into the output.

## Procedure

1. **Read every card.** Frames come from the *What* and *So what*
   sections, not the titles.
2. **Propose frames.** Each needs at least two signals; a one-signal frame
   is that signal restated. A signal may sit in several frames — that is
   the point of many-to-many, and a signal in three frames is usually the
   most important one in the corpus.
3. **Write each frame:**
   - `title` — 3–6 words, a claim not a topic ("Regulators move before
     standards bodies", not "Regulation").
   - `summary` — two sentences, present tense.
   - `content` — 150–250 words: the mechanism, the actors, the evidence,
     with each signal cited inline by slug the first time it is used.
   - `signals[]` — the bound cards.
4. **Check coverage.** List signals bound to no frame. Either they are
   noise (say so) or a frame is missing (add it). Don't force them in.
5. **Append, don't replace.** If a frame set already exists for this
   scope, new frames are added alongside; existing ones are edited only
   when the user asks. Provenance is the version history.
6. **Persist** to `/foresight/frames/<scope>-<kind>` (`category:
   research`), or `./foresight/frames/`. `message`: `frames · <kind> · <n> frames`.

## Output

```markdown
---
kind: frames
frame_kind: <drivers|tensions|themes|bets|custom>
title: <scope> · <frame kind>
scope:
sources: [<scan index or cards>]
signals_total: <n>
signals_unbound: [<slugs>]
---
## <frame title>
<summary>

<content>

**Signals:** slug · slug · slug
```

## Refusals

- Fewer than 6 active cards → say a frame set won't be meaningful; offer
  to run a scan or `signal` first.
- No forecasts inside frames. A frame describes what the signals show
  now; `scenarios` is where futures live.
