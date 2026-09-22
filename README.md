# Envisioning skills

Foresight methods, packaged as skills. Each one encodes a procedure we run on
client work, in the order the loop actually runs:

| stage | question | skills |
| --- | --- | --- |
| **sense** | what is changing? | `signal` |
| **structure** | what does it connect to? | `implications` |
| **project** | where could it go? | `scenarios` |
| **stress** | what does my plan assume? | `grill-the-future` |
| **make** | what do I hand someone? | `artifact-from-the-future` |

They chain. `signal` emits a card; `implications` and `scenarios` consume cards;
`grill-the-future` cites them as evidence; `artifact-from-the-future` renders
any of the above as a thing you can put on a table.

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
skills/<name>/SKILL.md
```

Skills are flat on disk because that is what plugin loaders discover; the
stage lives in each skill's frontmatter and in this table.
