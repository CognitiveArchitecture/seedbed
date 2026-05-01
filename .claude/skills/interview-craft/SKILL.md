---
name: interview-craft
description: The craft of interrogating an idea. Question sequencing, opening moves by seed type, push-vs-accept judgment, and discretion clauses for stakeholder texture. Records interview state continuously so mid-session context loss doesn't destroy the record. Load when /interrogate is invoked.
---

# Interview craft

The interview's job: surface what the user hasn't yet articulated, not confirm what they already know.

## Core rules

**One question at a time.** A batched set gets answered shallowly; a single question gets thought about.

**Don't ask obvious questions.** If the answer is inferable from what the user has said, from calibration, or from prior staging content, don't ask. Obvious questions signal inattention and burn the user's patience for the questions that matter.

**Dig into the hard parts.** Look for:
- Assumptions treated as given that shouldn't be
- Edge cases not yet named
- Tradeoffs between things the user wants that may conflict
- Dependencies that constrain choices
- Where the user's mental model may differ from how the idea will behave in execution

**Record as you go.** Write each Q+A to `INTERVIEW.md` immediately. Do not batch writes.

## Opening by seed type

**Iteration seeds: diagnosis first, and structure over symptoms.**

The user's reported problem is a symptom. The interrogation target is the *structural diagnosis* — what about the existing system invites the failure mode the user is reporting? "Scope balloons every time I extend it" is a symptom; the diagnosis question is "what about the current system's structure makes extension invite sprawl?" That points at the existing architecture, not the user's discipline.

Most iteration interrogations fail by accepting the symptom-level account and designing a fix for the symptom. The structural fix is usually different and more durable.

**Synthesis seeds: discovery first.**

Before asking what the consolidated artifact should look like, ask what's already out there. Where does the scattered material live? Who owns each piece? What's currently working in its scattered form vs. what's failing? Synthesis interrogations that skip discovery design consolidations against an imagined source rather than the real one.

**Shape-forming greenfield: open wide.**

Let the user talk. Listen for the question they're circling without naming. Don't constrain to features yet — features they already have in mind. Constraints, tradeoffs, and what they're trying to make possible are where the real shape comes from.

**Concrete greenfield: open with constraints and tradeoffs, not features.**

Features are pre-articulated. Tradeoffs and constraints are where choices get made and where assumptions live.

## Push vs. accept

Push when:
- The user hedges (indicates unfinished thinking)
- The answer conflicts with an earlier answer
- The answer is specific where specificity isn't yet warranted (premature convergence)
- The answer is vague where specificity is required for the downstream session
- The user is describing a symptom when the question was about structure

Accept when:
- The answer is a legitimate design-time unknown — resolvable only during execution
- Pushing would require the user to invent a decision they shouldn't make here
- The user has explicitly declared the question out of scope with sound reasoning

Record accepted unknowns as *live questions* in `DECISIONS.md` so the handoff surfaces them to the downstream session rather than hiding them.

## Discretion for stakeholder texture

Some seeds involve other people — colleagues, leadership, family, communities. Interrogation may surface political reads, working-relationship considerations, or context about other people that informs the design but shouldn't be recorded in `INTERVIEW.md` verbatim.

Distinguish:
- **Substantive answers shaping the design** → `INTERVIEW.md` as recorded
- **Context that informs interrogation but doesn't get written down** → held in working memory only

This isn't secrecy. It's appropriate scoping. Bundle artifacts may be reviewed by others or by future-you outside the original context. A senior PM wouldn't put every Slack DM about a stakeholder into a project doc; the same discretion applies here.

If a piece of stakeholder context turns out to be load-bearing for a decision, record the *decision* and its reasoning in `DECISIONS.md`, not the surrounding political read. The reasoning can be stated abstractly: "this iteration excludes work that depends on a stakeholder's commitment because their team is mid-reorganization," not the specifics of why you read the situation that way.

## Detecting seed reshape

If the interview surfaces that the real idea is adjacent to what was originally described — different problem, different exposure, different definition of done — stop. Recommend the user re-run `/seed` calibration with the new framing. Don't continue interrogating against an outdated framing.

## Exit conditions

Done when:
- Remaining unknowns are design-time unknowns (noted in `DECISIONS.md`)
- The user declares enough is enough and can articulate why
- `INTERVIEW.md` is sufficient to enter Shape without re-interviewing

*Not* done when:
- The user is tired (that's a pause, not an exit)
- Questions feel repetitive (phrasing or line of inquiry is off — try a different angle)
- You could produce a plausible-looking SPEC (plausibility ≠ sufficiency)

## Common failure modes

- **Asking questions already answered in calibration.** Re-read `STATE.md` before every question.
- **Shallow-stack questions.** Three weak questions that feel like progress but produce nothing. One deep question > three shallow ones.
- **Letting the user drive.** If they're narrating instead of answering, redirect.
- **Accepting plausible answers too quickly.** If an answer fits a familiar pattern too neatly, probe whether that pattern actually applies.
- **Designing around symptoms.** For iteration seeds, the symptom-level fix is usually wrong. Push to structural diagnosis.
- **Recording stakeholder context verbatim.** Use the discretion split.
