---
name: risk-radar
description: Surface downside indicators — incidents, precursors, advisories, hazards — across a defined exposure surface: operational, geopolitical, supply chain, cyber, climate-physical, reputational; grounded in agency advisories and incident reports, scored for likelihood, severity and horizon. Use when the user asks "what could hit us", "risk radar", "emerging threats to", "what should risk be watching", "supply chain risks for". Stage: sense.
---

# Risk Radar

A scan, run against the **Risk Radar** playbook. The steps live in
`../../core/scan.md`; the categories, metrics, sourcing rules and boundary
live in `../../core/playbooks/risk-radar.md`. Read both before starting, plus
`../../core/envisioning.md` and `../../core/grounding.md`.

**Audience:** Risk, operations, resilience, security.

## Boundary

This scan needs an **exposure surface** — a named business unit, supply-chain leg, region, or function (e.g. "lithium supply for our Polish plant", "APAC customer-support operations"). No generic risk panoramas.

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

Example: `/risk-radar "cold-chain logistics, West Africa"`
