# Grounding

How a signal earns the right to be believed. This is the traceability
contract: every card carries a grounding state, every source carries a
verdict, and a human's judgment outranks the machine's.

## Grounding state

One per signal. Nothing outside the `ground` skill changes it.

| state | meaning |
| --- | --- |
| `ungrounded` | no sources attached |
| `pending` | sources attached, no judgment yet |
| `verified` | the weight of contributing sources supports the claim |
| `rejected` | no credible source supports it, or the weight contradicts it |

`confidence` (`low` · `medium` · `high`) qualifies a terminal state and is
about source quality and agreement, not about the future.

## Source verdicts

Each source gets exactly one, judged on its **content**, never its title
or domain:

| verdict | meaning |
| --- | --- |
| `supports` | directly backs the specific claim |
| `contradicts` | directly opposes the specific claim |
| `unrelated` | adjacent topic; does not address the claim |
| `unreachable` | could not be read |

A source is **contributing** when its verdict matches the terminal state
(`supports` ↔ `verified`, `contradicts` ↔ `rejected`). A terminal state with
zero contributing sources is invalid — drop back to `pending`.

## Rules

1. **Humans outrank.** A manual verdict (state + optional confidence +
   mandatory reason) is a **manual override**: an automated re-run may not
   change it. Only a human clears it.
2. **Latest evaluation wins**, otherwise. Terminal states are not sticky;
   re-grounding with new sources may flip `verified` to `rejected`.
3. **Removing a non-contributing source changes nothing.** Removing the last
   contributing source drops the state to `pending`.
4. **Grounding is about the signal as a whole.** A source verdict is about
   one source. Don't conflate them.
5. **Sources are recorded even when they contradict.** A rejected signal
   with its contradicting sources is more useful than a deleted one.

## What good sources look like

Prefer primary artifacts: regulator publications, filings, peer-reviewed
work, standards bodies, the actor's own product or engineering pages,
established outlets. Avoid link aggregators, SEO posts, vendor marketing
that summarizes other coverage, and AI-generated overview pages. Each
playbook in `playbooks/` narrows this for its domain.

## On the card

```yaml
grounding:
  state: verified
  confidence: medium
  rationale: "Two primary sources (regulator notice, company filing) agree on scope and date; press coverage adds nothing."
  manual: false
sources:
  - url: https://…
    verdict: supports
    note: "filing, 2026-08-14, p.12"
  - url: https://…
    verdict: unrelated
```
