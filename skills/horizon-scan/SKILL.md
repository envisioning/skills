---
name: horizon-scan
description: Run a STEEP horizon scan on a topic or domain: surface weak signals of change across social, technological, economic, environmental and political layers, merge duplicates, ground each in primary sources, score impact, and write a scan index. Use when the user says "horizon scan", "scan the macro environment", "weak signals on", "what is changing around X", or needs input for scenario or board work. Stage: sense.
---

# Horizon Scan

A scan, run against the **Horizon Scan** playbook. The steps live in
`../../core/scan.md`; the categories, metrics, sourcing rules and boundary
live in `../../core/playbooks/horizon-scan.md`. Read both before starting, plus
`../../core/envisioning.md` and `../../core/grounding.md`.

**Audience:** Foresight, strategy, executive leadership.

## Boundary

This scan needs a **scan scope** — a topic, domain or question (e.g. "urban mobility in Europe", "the future of skilled trades"). Horizon scans are the least bounded playbook; still refuse "everything".

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

Example: `/horizon-scan "food systems in Southeast Asia, 10-year view"`
