# Scan procedure

The pipeline every `*-scan` / `*-radar` skill runs. The skill supplies the
playbook (`playbooks/<slug>.md`); this file supplies the steps. Same three
tasks as Signals AI: **generate → merge → ground**.

Read alongside: `envisioning.md`, `signal-schema.md`, `grounding.md`,
`voice.md`, and the playbook.

## 0. Scope

Every scan runs inside a boundary the playbook names (a scan scope, a home
position, a competitor set, an exposure surface, a jurisdiction + topic).
If the user hasn't given it, ask for it in one line — a scan without a
boundary is a panorama, and the playbook forbids panoramas. If a briefing
document exists (from `scope`), read it and use it.

Ground on the boundary (envisioning.md): prior cards on this scope are the
starting corpus, not competition.

## 1. Generate

For **each category** in the playbook, produce up to *signals per category*
(playbook default) candidates. Each is a **specific development** with a
public footprint, not a trend headline. Follow the playbook's "what counts"
line strictly.

Writing rules (identical across playbooks):

- **Title** — 30–40 characters, 3–6 words, noun phrase, no verbs or
  superlatives, punctuation limited to hyphen. Competitive scans include
  the competitor name when it fits.
- **Summary** — exactly two sentences, ≤ 25 words each:
  1. *Objective*: present tense; what exists, ships, funds, or demonstrably
     works today.
  2. *Impact*: begins with **"Signals"** or **"Indicates"**; immediate
     relevance to the boundary; no forecasts, no future tense.
- Active voice. Ban vague quantifiers (many, several, growing), filler
  adverbs (very, extremely), first person, hype adjectives (innovative,
  disruptive, unprecedented, paradigm-shifting). Name actors.
- Validation: reject a summary without exactly two periods or with either
  sentence over 30 words.

Assign exactly one playbook category. Leave metrics and grounding empty for
now.

## 2. Merge

Near-duplicates that point to the same underlying development become one
card. Use the playbook's merging line for what "same" means in that domain.
Rules:

- Prefer the title that is specific, concrete, and free of marketing or
  consulting framing.
- Preserve the stronger evidence hook in the summary.
- The merged-from cards are **frozen, not deleted**: keep them with
  `merged_into: <slug>` so the merge is reversible and the trail survives.

## 3. Ground

Run `ground` on every surviving card, using the playbook's sourcing
guidance. Up to *sources per signal* (playbook default). Sets `grounding`
and `sources[]` per `grounding.md`.

## 4. Score

Score every card on each playbook metric, using the metric's scale labels.
Score **comparatively across the whole corpus**, not card by card — a scan
where everything is "High" scored nothing. Put the scores under `metrics:`.

## 5. Persist and index

Each card persists per envisioning.md as a signal (`/foresight/signals`,
`category: research`) with `scan: <slug>` and `playbook: <playbook-slug>` in
frontmatter. Then write one **scan index** (`/foresight/scans/<slug>`,
`category: research`):

```markdown
---
kind: scan
playbook: <playbook-slug>
title: <playbook name> · <boundary>
boundary: <the scope as given>
date:
cards: <n>
merged: <n>
verified: <n>
rejected: <n>
---
## Boundary
## By category      ← table: category · count · verified · top card
## Top signals      ← by the playbook's first metric, top 10, with door/path
## Rejected         ← what was dropped and why; this is evidence too
## Coverage gaps    ← categories with < 2 verified cards, and why
```

Standalone, the index lives at `./foresight/scans/<slug>.md`.

## Refusals

- No boundary → no scan. Ask once.
- The user asks for a "trends report" → explain the difference, offer
  `frames` on the cards afterwards.
- Never pad a category to hit the default count. A thin category is a
  finding; say so in *Coverage gaps*.
