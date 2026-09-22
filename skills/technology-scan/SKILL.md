---
name: technology-scan
description: Map publicly documented technologies inside a defined scope — hardware, software, applications, ethics & security — with readiness level, impact and investment scores, each grounded in open sources. Use when the user asks "what technologies exist for", "technology landscape", "tech scan", "TRL of", "who is building", or wants a radar of capabilities in a field. Stage: sense.
---

# Technology Scan

A scan, run against the **Technology Scan** playbook. The steps live in
`../../core/scan.md`; the categories, metrics, sourcing rules and boundary
live in `../../core/playbooks/technology-scan.md`. Read both before starting, plus
`../../core/envisioning.md` and `../../core/grounding.md`.

**Audience:** Innovation, R&D, technology strategy.

## Boundary

This scan needs a **scan scope** — a named industry, sector, technical field, region, or combination (e.g. "grid-scale storage, EU", "computer vision in agriculture"). Capabilities, not STEEP trends.

If the user hasn't stated it, ask for it in one line and wait. If a briefing
exists (`scope` writes one), use its boundary verbatim.

## Run

1. Ground on the boundary — reuse prior cards as the starting corpus.
2. Generate per category, following the playbook's *what counts* line and
   the writing rules in `scan.md`. Assign exactly one category.
3. Merge near-duplicates per the playbook's *merging* line; freeze, don't
   delete.
4. `ground` each card using the playbook's *sourcing* line.
5. Score every card on each playbook metric, comparatively.
6. Persist cards and the scan index per `scan.md` §5.

## Output

The scan index, then one line: `wrote <n> cards + index to <path or folder> · <mode>`.

Example: `/technology-scan "non-invasive glucose monitoring"`
