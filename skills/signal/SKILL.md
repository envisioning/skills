---
name: signal
description: Turn a URL, article, paper, note or observation into a structured signal card — STEEP, technology, maturity, direction, so-what, tells to watch. Use when the user shares a link or fact and asks "is this a signal", "log this", "what does this mean", or wants a horizon-scanning entry. Stage: sense.
---

# signal

A signal is an observation of change, captured so it can be found, compared
and built on later. This skill produces exactly one card per observation, in
the format in `../../core/signal-schema.md`.

Read first: `../../core/envisioning.md` (mode), `../../core/signal-schema.md`
(format), `../../core/taxonomy.md`, `../../core/maturity.md`, `../../core/voice.md`.

## Procedure

1. **Fetch and read the source.** If it is a URL, read it in full. If it is a
   claim without a source, say so and set `confidence: low`.
2. **Ground.** Search for prior cards on the same topic (see envisioning.md).
   If one exists and this is the same observation, update it — bump `date`,
   add the source, adjust `direction` — instead of creating a duplicate. If
   it is a new observation on a known topic, create a new card that links the
   old one in `sources`.
3. **Extract the observable fact.** One sentence, present tense, with an
   actor. Strip forecasts and opinions from the source; they go nowhere.
4. **Classify.** STEEP layer where the change happens. `tech[]` resolved
   against the taxonomy when connected.
5. **Place on maturity and direction.** Use the tells table in maturity.md.
   If two stages fit, pick the lower and say why in *Watch for*.
6. **Write so-what.** Three bullets, each naming who is affected. If you
   cannot name three affected parties it may not be a signal — say so.
7. **Write tells.** What would make you raise confidence, and what would make
   you drop the card.
8. **Persist** per envisioning.md. Show the user the card and where it went.

## Refusals

- A trend, a prediction, or a vendor press release with no independent
  observation is not a signal. Say what it is instead and offer to log the
  underlying observable if there is one.
- Multiple facts in one source → offer to make multiple cards; do not merge.

## Output

The card, then one line: `wrote <path or door> · <mode>`.
