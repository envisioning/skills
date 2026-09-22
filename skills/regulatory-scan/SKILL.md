---
name: regulatory-scan
description: Track rulemaking, enforcement, court rulings, self-regulation and standards activity for a named jurisdiction and topic, grounded in primary regulator sources, scored for compliance impact, time to effect and jurisdictional breadth. Use when the user asks "what regulation is coming", "regulatory scan", "compliance landscape", "is there a rule on", "what has the regulator done about". Stage: sense.
---

# Regulatory Scan

A scan, run against the **Regulatory Scan** playbook. The steps live in
`../../core/scan.md`; the categories, metrics, sourcing rules and boundary
live in `../../core/playbooks/regulatory-scan.md`. Read both before starting, plus
`../../core/envisioning.md` and `../../core/grounding.md`.

**Audience:** Legal, policy, compliance, public affairs.

## Boundary

This scan needs a **jurisdiction and topic** (e.g. "EU — AI in medical devices", "California — data broker registration"). Both are required; neither may be widened mid-scan.

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

Example: `/regulatory-scan "UK — buy-now-pay-later"`
