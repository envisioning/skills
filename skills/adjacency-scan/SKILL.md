---
name: adjacency-scan
description: Map where to play next from a defined home position — adjacent categories, customers, geographies, channels, capabilities — one hop out, each anchored in evidence and scored for strategic fit, defensibility and time to entry. Use when the user asks "where could we expand", "adjacent markets", "what's next to our core", "growth options", "adjacency". Stage: sense.
---

# Adjacency Scan

A scan, run against the **Adjacency Scan** playbook. The steps live in
`../../core/scan.md`; the categories, metrics, sourcing rules and boundary
live in `../../core/playbooks/adjacency-scan.md`. Read both before starting, plus
`../../core/envisioning.md` and `../../core/grounding.md`.

**Audience:** Corporate strategy, corporate development, product.

## Boundary

This scan needs a **home position** — what the business is and does today, stated concretely (e.g. "mid-market payroll software, US, 2k customers, strong compliance engine"). One hop only.

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

Example: `/adjacency-scan home: "specialty coffee roaster, DTC subscription, 40k subscribers, own roastery"`
