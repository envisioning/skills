---
name: competitive-scan
description: Track the observed moves of a named competitor set within a category — product, pricing, GTM, hiring, funding, messaging — grounded in the competitors' own filings, pages and postings, scored for threat, momentum and confidence. Use when the user says "what are competitors doing", "competitive scan", "track rivals", "battlecard input", or names companies and asks what they are up to. Stage: sense.
---

# Competitive Scan

A scan, run against the **Competitive Scan** playbook. The steps live in
`../../core/scan.md`; the categories, metrics, sourcing rules and boundary
live in `../../core/playbooks/competitive-scan.md`. Read both before starting, plus
`../../core/envisioning.md` and `../../core/grounding.md`.

**Audience:** Strategy, competitive intelligence, corporate development.

## Boundary

This scan needs a **competitor set and category** — named companies plus the category you compete in (e.g. "Notion, Coda, Slite in team docs"). No generic market commentary.

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

Example: `/competitive-scan "Wise, Revolut, Airwallex — SMB cross-border payments"`
