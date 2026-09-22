---
name: merge
description: Deduplicate a set of signal cards — find near-duplicates that describe the same underlying development, keep the most specific title, preserve the stronger evidence, and freeze the duplicates with a pointer instead of deleting them. Use when the user says "dedupe these", "merge duplicates", "these overlap", "clean up the scan", or after generating cards from several sources. Stage: structure.
---

# merge

Two cards that point at the same development are one signal with two
titles. This skill finds them and folds them without losing the trail.

Read first: `../../core/signal-schema.md`, `../../core/envisioning.md`.

## Input

A set of cards: a scan index, a folder, a list of paths or doors. Cards
already carrying `merged_into` are skipped.

## Procedure

1. **Pair.** Compare cards on the *What* section, not the title. Two cards
   are candidates when they describe the same underlying development —
   the same programme, rule, launch, deal, capability, or measured shift.
   The same *topic* is not enough: "EU AI Act enforcement begins" and
   "EU AI Act fines first company" are two signals.
2. **Domain rule.** If the cards carry a `playbook`, apply that playbook's
   *merging* line for what "same" means (same competitor + move; same
   docket; same incident; same one-hop opportunity).
3. **Choose the target.** The card with the most specific, concrete title
   free of marketing, consulting, advocacy or alarmist framing. Ties → the
   better-grounded one.
4. **Fold.** Into the target: the stronger evidence hook in the summary,
   the union of `sources[]` (dedupe by URL, keep the higher-confidence
   verdict), the union of `actors[]` and `tech[]`. Keep the target's
   category and metrics; if the merged-from card was scored higher on a
   metric, note it in *Watch for* rather than silently raising the score.
5. **Freeze.** Each merged-from card keeps every field and gains
   `merged_into: <target slug>`. It is not deleted, not edited otherwise.
   Unmerging is removing that one line.
6. **Ask before folding when unsure.** Present the pair with the sentence
   that makes them the same; a human decides. Never merge more than the
   user can review in one screen without pausing.
7. **Persist.** Target and frozen cards per envisioning.md. `message`:
   `merge · <n> into <target>`.

## Output

A table: `target · merged-from · why they are the same`. Then the count:
`<n> cards → <m> active, <k> frozen`.

## Refusals

- Cards from different scopes or playbooks are not merged; the same fact
  can be a different signal to a different audience.
- Never merge a `verified` card into a `rejected` one, or vice versa; that
  is a grounding disagreement to resolve with `ground`, not a duplicate.
