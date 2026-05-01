---
name: intake-calibration
description: Calibrate a new seed idea at Intake phase. Distinguishes greenfield, iteration, and synthesis seed types; assesses leaf-node, architectural core, and non-architectural core exposure; records definition of done and arc pace. Permits and structures re-calibration when seeds reshape mid-arc. Load when /seed is invoked or when intake state needs recalibration.
---

# Intake calibration

Calibration happens at the start of an idea's arc and *again* when interrogation or shape surface that the real idea is adjacent to what was first described. Calibration is not single-pass when the seed reshapes. Silent drift against an outdated calibration is how the *flatten the unconventional* failure mode happens.

Wrong calibration cascades. An iteration mistaken for greenfield will be interviewed wrong. A core-exposure idea treated as a leaf will be under-scaffolded. A non-architectural core (political, relational) treated as architectural will get the wrong kind of scaffolding.

## The four calibration questions

Ask in sequence, one at a time. Do not batch. Do not proceed without answers or explicit deferrals.

**1. Is this a new seed, an iteration on a running system, or a synthesis of existing scattered material?**

- **Greenfield** — no existing system or content to consolidate from. The interrogation opens wide; the idea may need shape-forming.
- **Iteration** — modifying or extending a system that already runs. Interrogation opens with diagnosis: what's working, what's not, what's *actually* broken vs. what *feels* broken? For iteration seeds, the existing system *is* the architecture exposure must be assessed against, not just the new work being added.
- **Synthesis** — building a new artifact from existing scattered material (notes across vaults, content across SharePoint pages, code across repos). Interrogation needs a discovery move that greenfield and iteration don't: what's already out there that this consolidates from, who owns each piece, what gets included vs. left in place?

Some seeds are mixed. Note which parts are which.

**2. What's the exposure profile?**

- **Leaf-node** — isolated, self-contained; failures don't cascade. Be bold. Less scaffolding needed.
- **Architectural core** — touches cross-cutting concerns, public interfaces the user maintains, technical dependencies, or systems other work depends on. Slow down. Scaffold harder. Challenge more aggressively.
- **Non-architectural core** — depends on political, relational, or organizational state the user doesn't unilaterally control. Stakeholder coordination, organizational alignment, framing claims that depend on others' cooperation. Same logic applies as architectural core (slow down, more scaffolding, harder challenge), but the texture is different. For non-architectural core, *political-shift robustness* becomes a real attack surface during challenge.

Most non-trivial ideas are mixed. Note which parts are which. The exposure read shapes how aggressively scope-perimeter and challenge run.

**3. What does "done" mean for *this* idea?**

Not generically "implementation-ready." What does execution actually produce? A running system? A publishable artifact? A personal protocol? A consolidated repository?

Apply the testability bar: **the definition of done must be testable by the user alone.** If the criterion requires another person's engagement or response to verify, it's not done — it's launched. "I can hand it to a stakeholder" is launch, not done. "The repository contains X content organized by Y" is done.

Apply the artifact-or-behavior bar: **done is a checkable artifact or behavior, not a quality.** "Tractable," "clean," "clear," "reliable" are hopes. They're often the *user's actual goal*, but they fail as criteria because they're unfalsifiable. If the user's done definition is a quality, push: "what artifact, run, or check would tell you it's tractable?"

**4. What's the user's arc pace?**

Single session or multi-session? Multi-session means staging legibility is load-bearing — `STATE.md` must orient a cold return. Single session permits more momentum, less re-orientation overhead.

## Output

Write to `STATE.md`:
- Seed framing (one sentence — current understanding of what the idea is)
- Seed type: greenfield | iteration | synthesis
- Exposure: leaf | architectural core | non-architectural core | mixed (specify)
- Definition of done: [one sentence, testable by user alone, checkable]
- Arc pace: single session | multi-session

Set next move: `/interrogate`.

## Re-calibration

When interrogation or shape surface that the real idea is adjacent to what was originally described — different shape, different exposure profile, different definition of done — return to this skill and re-run the four questions against the new framing. Update `STATE.md` seed framing and any other fields that changed.

This is a normal move, not a failure. Shape-forming seeds especially are likely to reshape during interrogation. Iteration seeds may reshape if diagnosis reveals the real problem is structural rather than what the user reported.

## Common failure modes

- **Mistaking shape-forming for concrete.** If the user can't answer "what does done look like" with specificity, the seed is shape-forming. Record the ambiguity; don't force a concrete answer.
- **Accepting "it's a leaf" too quickly.** Users underestimate exposure. For iteration seeds, the existing system is itself architecture being modified. For seeds with stakeholder texture, the relational/political layer is exposure even when the technical work is leaf.
- **Skipping calibration on small ideas.** Small ideas still benefit. Answers may be fast — the four questions set the shape.
- **Letting a hope-disguised "done" pass.** If the user defines done as a quality, push for the artifact or behavior that would demonstrate the quality.
- **Calibrating once and never re-calibrating.** When the seed reshapes, re-run the four questions. Don't continue against outdated framing.
