---
name: scope
description: Turn a vague foresight request into a briefing — the decision it serves, the boundary, the horizon, the audience, what's out, and which playbook fits — by asking a few questions and writing the answers down before any scanning starts. Use when the user says "we want to look at the future of X", "scope this", "set up a scan", "what should we research", or when any scan skill is invoked without a clear boundary. Stage: sense (before it).
---

# scope

Most foresight work fails at the start: the question is a topic, not a
decision, and the boundary is "everything". This skill produces the
briefing every downstream skill reads.

Read first: `../../core/envisioning.md`, `../../core/playbooks/` (the seven
boundaries), `../../core/voice.md`.

## Procedure

Ask, in order, one at a time. Skip anything the user already stated.
Offer a default in each question so a one-word answer works.

1. **Decision.** *What will someone decide differently because of this?*
   If there is no decision, it is curiosity — fine, say so and set
   `decision: none`, but the scan will be broad and the report short.
2. **Boundary.** *Where does it stop?* Named industry / geography /
   function / competitor set / home position / exposure surface /
   jurisdiction. Push once if the answer is a topic ("AI") rather than a
   boundary ("AI in claims handling, EU insurers").
3. **Horizon.** *When does it need to be true to matter?* 1 · 3 · 10
   years. Default 3.
4. **Audience.** *Who reads the result, and in what meeting?* This sets
   the report type.
5. **Out of scope.** *What are we explicitly not looking at?* Two items
   minimum; "nothing" is an answer that predicts a panorama.
6. **Prior work.** Ground: search for existing cards, scans, reports on
   this boundary. Show what exists; the briefing links it.

Then **pick the playbook** from the boundary shape:

| the boundary is a… | playbook |
| --- | --- |
| topic / domain, macro | `horizon-scan` |
| field / sector, capabilities | `technology-scan` |
| industry / function, practices | `innovation-radar` |
| named competitor set | `competitive-scan` |
| home position | `adjacency-scan` |
| jurisdiction + topic | `regulatory-scan` |
| exposure surface | `risk-radar` |

Two playbooks may fit; say which runs first and why. Downstream skills
after the scan (`frames`, `scenarios`, `grill-the-future`, `report`) are
listed as the *plan*.

## Output

```markdown
---
kind: briefing
title: <boundary> · <horizon>y
decision:
boundary:
horizon: <1|3|10>
audience:
report_type:
out_of_scope: []
playbook: <slug>
plan: [<skills in order>]
prior: [<cards, scans, reports found>]
subject: <core:kind:id, if for a client>
---
## Decision
## Boundary
## Out of scope
## Plan
```

Persist to `/foresight/briefings/<slug>` with `category: brief`, or
`./foresight/briefings/`. `message`: `scope · new briefing`.

Every scan skill reads this file first when it exists for the boundary.

## Refusals

- Don't write a briefing the user hasn't answered; a guessed briefing is
  worse than none because downstream skills trust it.
- Don't start the scan from here. End with the briefing and the first
  command to run.
