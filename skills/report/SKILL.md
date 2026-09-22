---
name: report
description: Write a narrative report from a scan's active signals and frames, shaped by a report type — executive readout, board narrative, watchlist, compliance memo, or a custom type — in house voice, with every claim traceable to a card. Use when the user says "write it up", "executive summary of the scan", "report for leadership", "turn this into a memo", "board slide notes". Stage: make.
---

# report

The deliverable. A report is a narrative over verified signals; nothing in
it may be untraceable to a card, and nothing verified should be missing
without a reason.

Read first: `../../core/voice.md`, `../../core/signal-schema.md`,
`../../core/envisioning.md`.

## Input

A scan index (or a set of cards) and optionally a frame set. Pick or take
a **report type**:

| type | reader | length | shape |
| --- | --- | --- | --- |
| `readout` | CEO / exec team | 600–900 words | 3 things that changed · what it means · what to watch |
| `board` | board / non-exec | 400–600 words | one narrative, three exhibits, one question for the board |
| `watchlist` | strategy / foresight team | table + notes | every verified card, ranked by the playbook's first metric, with tells |
| `compliance` | GC / compliance | 600–900 words | in force · coming · enforcement posture · actions with dates |
| `brief` | anyone | ≤ 400 words | the one-pager |

A custom type needs: reader, length, and the section list; write them
into frontmatter.

## Procedure

1. **Use only active, grounded cards.** `verified` cards are the spine;
   `pending` may appear if labelled as such; `rejected` cards appear only
   in a *what we ruled out* line, which is often the most credible
   paragraph. Frozen duplicates never appear.
2. **Lead with change, not with the method.** No paragraph about how the
   scan was done above the fold; that goes in a *Method* footer.
3. **Cite by slug.** Every factual claim carries `[slug]` the first time.
   Numbers carry their source's note. When connected, slugs render as doors.
4. **Rank by the metrics.** The playbook's metrics decide what comes
   first; don't reorder by narrative convenience.
5. **Write in voice.** See voice.md; no hype, name actors, end with a
   tell or a question.
6. **Gaps are content.** The scan index's *Coverage gaps* becomes a
   sentence in the report; silence about a thin category reads as
   confidence you don't have.
7. **Persist** to `/foresight/reports/<scope>-<type>` with `category:
   report` (or `./foresight/reports/`). Attach the client `subject` if the
   scan carried one. `message`: `report · <type>`.

## Output

```markdown
---
kind: report
report_type: <type>
title:
scope:
date:
sources: [<scan index>, <frame set>]
cards_cited: <n>
cards_verified_total: <n>
---
<body per the type's shape>

---
*Method:* <playbook>, <n> cards generated, <m> merged, <k> verified, <r> rejected. Cards: <folder or door>.
```

## Refusals

- No verified cards → no report. Offer `ground` first.
- Do not invent a recommendation the cards don't support. A report may
  end in "we don't know yet; here is what would tell us."
