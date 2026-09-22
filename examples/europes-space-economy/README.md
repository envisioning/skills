# Example run · Europe's space economy

The first end-to-end run of these skills, 22 September 2026. Real output, not
a mock-up — every source was fetched and read, and the coverage gaps are the
ones the run actually had.

**Chain:** `scope` → `horizon-scan` → `ground` → `merge` → `frames` → `report`

**Result:** 14 signal cards — 13 verified, 1 pending, 0 rejected, 0 merged.
13 sources read in full, 4 unreachable.

| file | skill | what it is |
| --- | --- | --- |
| [briefing.md](briefing.md) | `scope` | the decision, boundary, horizon and plan, written before any scanning |
| [scan.md](scan.md) | `horizon-scan` | the index: cards by category, ranked by impact, what was rejected, where coverage is thin |
| [signals/](signals) | `horizon-scan` + `ground` | three of the fourteen cards, chosen to show the range of grounding states |
| [frames-tensions.md](frames-tensions.md) | `frames` | four structural tensions, each citing the cards underneath it |
| [readout.md](readout.md) | `report` | the deliverable: three things that changed, what it means, what to watch |

The three cards are [IRIS² grows to 348 plus 66 defence
satellites](signals/iris2-grows-to-348-plus-66-defence-satellites.md)
(verified, high confidence — two primary sources), [European spacetech VC hits
$2bn in H1 2026](signals/european-spacetech-vc-hits-2bn-in-h1-2026.md)
(verified, medium — one secondary analysis of a named dataset), and [D-Orbit
GEO servicing demo set for 2028](signals/d-orbit-geo-servicing-demo-set-for-2028.md)
(**pending** — well-attested in search results but no source read in full, so
the card says so and the report does not cite it).

That last one is the point of the whole grounding contract: a signal that
looks right and has not been checked is marked, not quietly asserted.

## What this run taught us

- Merge had nothing to do. Fourteen cards from one generator produce no real
  duplicates; `merge` earns its keep across runs and sources, not within one.
- Some trade press blocks automated fetching and PDFs often don't parse.
  `ground` marks those sources `unreachable` and caps confidence rather than
  guessing — see the Isar and skills cards in the full set.
- Two STEEP layers came out thin (Social: one card; no Earth-observation or
  navigation cards at all). The scan index says so under *Coverage gaps*,
  because a quiet gap reads as confidence the corpus doesn't have.
- Cards per category were 2–4 rather than the playbook's default 5, to keep a
  first run tractable.

Written by the skills in this repo, running in Claude Code with an Envisioning
MCP connected; the originals live in Envisioning Docs. The `subject:` line that
ties them to a client engagement has been stripped here.
