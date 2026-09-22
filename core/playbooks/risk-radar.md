# Risk Radar

> Ported from the Signals AI playbook `risk-radar`. The same structure runs at scale in [Signals AI](https://signals.envisioning.com).

Surfaces downside indicators across an organization's exposure surface — operational, geopolitical, supply-chain, cyber, climate-physical, and reputational — so leadership can see emerging threats before they crystallize. Grounded in public incident reports, regulator and agency advisories, scientific assessments, and reputable press.

- **Audience:** Risk, operations, resilience, and security
- **Use when:** Surfacing downside indicators across a defined exposure surface — business unit, supply-chain leg, region, or function.

## Boundary

Identify concrete downside indicators — incidents, precursors, advisories, or hazard developments — that bear on the **exposure surface** defined for this run (a named business unit, supply-chain leg, region, or function). Stay **inside that boundary**; do not broaden into generic risk panoramas. Skip developments that lack any defensible public footprint.

## What counts as a signal here

Each item is a **specific risk event, precursor, or vulnerability** — not a general anxiety or speculative scenario.

## Categories (pick exactly one)

| category | meaning |
| --- | --- |
| Operational | Incidents and weaknesses inside the organization's own operations, processes, and assets. |
| Geopolitical | State-level instability, conflict, sanctions, trade actions, and political risk. |
| Supply Chain | Disruptions to inputs, logistics, suppliers, and dependent infrastructure. |
| Cyber | Cyber threats, vulnerabilities, incidents, and adversary activity relevant to the exposure surface. |
| Climate Physical | Acute and chronic climate hazards affecting assets, workforce, or operations. |
| Reputational | Public-facing developments that materially threaten trust, license to operate, or stakeholder relations. |

## Metrics (score every signal on each)

### Likelihood (`likelihood`)

Estimated probability of the threat materializing within the exposure surface.

1 · Rare · 2 · Unlikely · 3 · Possible · 4 · Likely · 5 · Almost certain

### Severity (`severity`)

Magnitude of harm to operations, finances, people, or reputation if the threat materializes.

1 · Negligible · 2 · Minor · 3 · Moderate · 4 · Major · 5 · Catastrophic

### Time Horizon (`time-horizon`)

When the threat is expected to manifest, based on observed precursors.

1 · Immediate · 2 · Within months · 3 · 1–2 years · 4 · 2–5 years · 5 · Beyond 5 years

## Sourcing

Search the web for credible **primary** risk sources that substantiate or refute this signal **within the exposure surface**. Prefer official agency advisories (CISA, ENISA, ICS-CERT, FEMA, IPCC, WHO, regulator releases), incident reports from named vendors or operators, peer-reviewed assessments, and reputable specialist press. Avoid threat-marketing blog posts, partisan commentary, and AI-generated overview pages.

## Merging

Merge near-duplicate risk signals that point to the same incident, advisory, vulnerability, or hazard. Prefer the title that names the threat specifically and avoids alarmist framing. When merging, preserve the stronger primary-advisory hook in the summary.

## Defaults

- signals per category: 5
- sources per signal: up to 5
