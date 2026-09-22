---
name: artifact-from-the-future
description: Render a signal, scenario or idea as a concrete object from a future date — a press release, product page, news headline set, regulator's notice, support ticket, obituary, onboarding email — in the voice of that world, so a team can react to it. Design fiction, disciplined. Use when the user asks for "a press release from 2035", "what would the headline be", "show me what this looks like", "design fiction", or needs a workshop provocation. Stage: make.
---

# artifact-from-the-future

Abstract futures don't provoke; objects do. This skill makes one object
from one future, precise enough that people argue with it.

Read first: `../../core/envisioning.md`, `../../core/voice.md`.

## Input

- **Source**: a scenario (name + set), a signal card, or a stated premise.
- **Year**: explicit, or taken from the scenario's horizon.
- **Form**: pick from the table or take the user's. If unspecified, choose
  the form that makes the premise most *ordinary* — a future is convincing
  when it is boring to the people living in it.

| form | good for |
| --- | --- |
| press release | a capability arriving |
| product page with pricing | a cost curve bending |
| three news headlines + standfirsts | a norm shifting |
| regulator's notice / recall | a backlash |
| customer support ticket | a failure mode at scale |
| job posting | a new role existing |
| onboarding email | adoption becoming default |
| obituary (of a product, practice or company) | a substitution completing |
| museum placard | the long view |

## Procedure

1. **Anchor.** Ground on the source; list 3–5 facts from the cards or
   scenario that the artifact must respect. Write them in frontmatter as
   `anchors[]` so a reader can check the fiction against the evidence.
2. **Extrapolate one step.** The artifact lives one step *past* the
   anchors, not ten. Include one detail that is mundane in the future and
   startling now (a price, a default setting, a line in the terms).
3. **Write in the world's voice.** The document is written by someone in
   that year who does not know it is a provocation. No winking, no "in
   this future". Institutions have names; prices have currencies; dates are
   real dates.
4. **Keep it short.** 200–400 words. A real press release is skimmed; so is
   this.
5. **Add the reading guide** *after* the artifact, separated by a rule:
   three questions for the team — *what here is already true?* · *what
   would have to happen for this to exist?* · *who in this room would fight
   it?*
6. **Persist** per envisioning.md.

## Output

```markdown
---
kind: artifact
title: <the artifact's own headline>
form: <from the table>
year: <YYYY>
scenario: <name, if from a set>
anchors: [<facts respected>]
sources: [<cards / scenario doc>]
---
<the artifact, in-world>

---
## Reading guide
```

## Refusals

- No utopia, no apocalypse. If the premise only works as either, say so
  and offer the nearest ordinary version.
- Never use a real company as the subject of a failure artifact. Fictional
  names for actors; real names only for institutions that would plausibly
  still exist (regulators, standards bodies).
