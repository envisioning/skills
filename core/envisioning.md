# Envisioning link — ground, persist, classify

Read this before any skill produces output. It decides where inputs come from
and where outputs go. The skill's procedure never changes; only these three
hooks do.

## Detect

You are **connected** if the tool list contains `search`, `open` and
`docs_write` from an Envisioning server (Meet's `/mcp`, or a public
Envisioning MCP). Any one missing → **standalone**. Never ask the user to
connect; say which mode you are in, once, in one line.

## Ground (before generating)

| connected | standalone |
| --- | --- |
| `search("<topic>", kinds: ["document"])` — look for existing signal cards, methodology chapters, newsletter issues, reports on the topic. `open` the top 3. Cite them by door (`document:<id>`) in the output's `sources`. | `grep -ril "<topic>" ./foresight/` — reuse cards already on disk. Cite by path. |
| If a `methodology` document covers the method you are running, follow it over this skill's defaults. | Use the skill's defaults. |

Grounding is a read. It never blocks: if search returns nothing, proceed.

## Classify

| connected | standalone |
| --- | --- |
| `search("<technology>", kinds: ["document"])` restricted to `methodology` / `research` categories returns taxonomy entries when they exist. Use the entry's canonical name as `tech[]`. | Use STEEP + free-text `tech[]` from `core/taxonomy.md`. |

## Persist (after generating)

The output is one markdown file with the frontmatter in
`core/signal-schema.md` (or the skill's own schema). Same bytes either way.

| output | connected: `docs_write` | standalone |
| --- | --- | --- |
| signal card | `folder_path: /foresight/signals`, `category: research` | `./foresight/signals/<slug>.md` |
| implications map | `folder_path: /foresight/implications`, `category: research` | `./foresight/implications/<slug>.md` |
| scenario set | `folder_path: /foresight/scenarios`, `category: research` | `./foresight/scenarios/<slug>.md` |
| grill report | `folder_path: /foresight/grills`, `category: brief` | `./foresight/grills/<slug>.md` |
| artifact | `folder_path: /foresight/artifacts`, `category: brief` | `./foresight/artifacts/<slug>.md` |
| briefing (`scope`) | `folder_path: /foresight/briefings`, `category: brief` | `./foresight/briefings/<slug>.md` |
| scan index | `folder_path: /foresight/scans`, `category: research` | `./foresight/scans/<slug>.md` |
| frame set | `folder_path: /foresight/frames`, `category: research` | `./foresight/frames/<slug>.md` |
| report | `folder_path: /foresight/reports`, `category: report` | `./foresight/reports/<slug>.md` |

Scan cards are ordinary signal cards in `/foresight/signals`; the scan index
lists them. `ground` and `merge` update cards in place — always `open` first
and pass `if_content_hash`.

Rules for `docs_write`:

- `title` = the card's `title`. Slug is derived by Docs; don't invent one.
- `message` = one line: `<skill> · <what changed>` — e.g. `signal · new card from arxiv 2409.1234`.
- If the user is working on a client subject, ask once whether to attach it;
  a `subject:` door from `search` can be named in `body_md`'s frontmatter as
  `subject: core:project:<id>` so Docs' `?subject=` view finds it.
- Updating an existing card: `open` it first, pass `if_content_hash`. A
  `hash_mismatch` means a human edited it — show the diff, don't overwrite.
- `docs_write` needs `write` scope. If refused, fall back to standalone for
  this run and say so.
- Never `record_decision`, `create_task` or `send_message` from a skill. The
  person decides what becomes a decision.

## Cross-links

Every output links what it consumed: `sources[]` holds doors when connected,
paths when standalone. `implications` and `scenarios` list the signal cards
they were built from; `grill-the-future` lists the cards it used as evidence.
A later `search` on any of these finds the chain.
