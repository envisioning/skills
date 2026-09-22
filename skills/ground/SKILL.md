---
name: ground
description: Verify a signal against primary sources — search for evidence, judge each source as supports / contradicts / unrelated, then issue a grounding state (verified, rejected, pending) with confidence and a written rationale. Use when the user asks "is this real", "verify this signal", "find sources for", "ground this", "how solid is this", or after any scan. Stage: sense.
---

# ground

Signals are cheap; grounded signals are the product. This skill turns a
claim into a traceable judgment: which sources were read, what each one
actually said, and what that adds up to.

Read first: `../../core/grounding.md` (the contract), `../../core/envisioning.md`,
`../../core/signal-schema.md`.

## Input

One signal card (path or door), or a batch (a scan index, a folder). For a
batch, run each card independently; never let one card's sources ground
another.

Optional: a playbook slug — its *sourcing* section narrows what counts as
credible in that domain. Without one, use the generic guidance in
grounding.md.

## Procedure

Per card:

1. **Read the claim** as the card states it — the *What* section. Ground
   the claim, not the topic.
2. **Reuse.** If the card already has sources, keep them; they get
   re-judged, not re-found. When connected, `search` the topic for existing
   cards whose sources may apply.
3. **Search.** Find up to *sources per signal* (default 5) primary sources
   that could substantiate **or refute** the claim. Skip URLs already on
   the card. Prefer primary artifacts per grounding.md / the playbook.
   Searching only for confirmation is the failure mode; look for the
   contradiction on purpose.
4. **Read each source in full** and issue one verdict on its **content**:
   `supports` · `contradicts` · `unrelated` · `unreachable`. Add a one-line
   `note` with the specific passage, date, or figure that decided it.
5. **Judge the signal.** Per grounding.md: `verified` when credible sources
   support it and none credibly contradict; `rejected` when nothing
   credible supports it or the weight contradicts it; `pending` when
   evidence exists but is thin or mixed. Set `confidence` from source
   quality and agreement. Write a two-sentence `rationale` that a reader
   could check.
6. **Respect overrides.** If `grounding.manual: true`, do not change the
   state. Add your sources and verdicts, and report the disagreement if
   there is one.
7. **Persist.** Update the card in place (connected: `open` → `docs_write`
   with `if_content_hash`; standalone: rewrite the file). `message`:
   `ground · <state> · <n> sources`.

## Output

Per card, one line: `<title> → <state> (<confidence>) · <supports>/<contradicts>/<unrelated>`.
For a batch, a table plus the count of state changes. Never print the
sources' full text.

## Refusals

- A claim too vague to be verified ("AI is changing healthcare") → say
  what specific observable would be verifiable and stop.
- Do not verify from memory. No source read → no verdict.
