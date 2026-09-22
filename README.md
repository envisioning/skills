# Envisioning skills

Foresight methods, packaged as skills. Each one encodes a procedure we run on
client work, in the order the loop actually runs:

| stage | question | skills |
| --- | --- | --- |
| **scope** | what decision, what boundary? | `scope` |
| **sense** | what is changing? | `signal` · `ground` · the seven scans below |
| **structure** | what does it connect to? | `merge` · `frames` · `implications` |
| **project** | where could it go? | `scenarios` |
| **stress** | what does my plan assume? | `grill-the-future` |
| **make** | what do I hand someone? | `report` · `artifact-from-the-future` |

### The seven scans

Each runs the same pipeline — generate → merge → ground → score — against a
playbook that fixes the boundary, categories, metrics and sourcing rules.
These are the playbooks we run for clients in [Signals AI](https://signals.envisioning.com).

| skill | boundary you give it | categories | scored on |
| --- | --- | --- | --- |
| `horizon-scan` | a topic or domain | STEEP | impact |
| `technology-scan` | a field, sector or region | hardware · software · applications · ethics & security | readiness · impact · investment |
| `innovation-radar` | an industry or function | business model · operating model · process · product · channel · CX | novelty · adoption momentum · fit |
| `competitive-scan` | a named competitor set | product · pricing · GTM · hiring · funding · messaging | threat · momentum · confidence |
| `adjacency-scan` | your home position | category · customer · geography · channel · capability | fit · defensibility · time to entry |
| `regulatory-scan` | a jurisdiction + topic | proposed · enacted · enforcement · self-reg · court · standards | compliance impact · time to effect · breadth |
| `risk-radar` | an exposure surface | operational · geopolitical · supply chain · cyber · climate · reputational | likelihood · severity · horizon |

They chain. `scope` writes the briefing; scans emit cards; `ground` makes
them traceable; `merge` and `frames` structure them; `scenarios`,
`implications` and `grill-the-future` use them as evidence; `report` and
`artifact-from-the-future` turn them into something you can hand over.

Every card carries a grounding state and per-source verdicts
([`core/grounding.md`](core/grounding.md)) — a signal is never asserted
without saying what was read and what it said.

## Install

```bash
claude plugin marketplace add envisioning/skills
claude plugin install envisioning
```

or, without Claude Code: copy `skills/<name>/SKILL.md` and `core/` into your
agent's skills directory. Every skill reads `core/` by relative path.

## Standalone vs. connected

Every skill works with no account and no network. Outputs land in
`./foresight/` in your project, as markdown with frontmatter.

When an **Envisioning MCP** is connected (`search`, `open`, `docs_write` are
present), the same skills:

- **ground** — check what Envisioning already knows before generating
  (`search` for prior signals, methodology, taxonomy entries)
- **persist** — write the output into Docs at a predictable path with the
  right category, so it is findable, annotatable and shareable
- **classify** — map to the Envisioning technology taxonomy instead of the
  generic STEEP fallback

The contract is in [`core/envisioning.md`](core/envisioning.md). The same
markdown file is what gets written either way; the MCP only changes *where*.

## Layout

```
core/          shared references every skill reads — never invoked directly
  signal-schema.md   the one card format
  taxonomy.md        STEEP fallback + how to resolve the live taxonomy
  maturity.md        readiness scale
  voice.md           house style
  envisioning.md     ground / persist protocol
  grounding.md       grounding states, source verdicts, override rules
  scan.md            the generate → merge → ground → score pipeline
  playbooks/<slug>.md  one per scan: boundary, categories, metrics, sourcing
skills/<name>/SKILL.md
```

Skills are flat on disk because that is what plugin loaders discover; the
stage lives in each skill's frontmatter and in this table.
