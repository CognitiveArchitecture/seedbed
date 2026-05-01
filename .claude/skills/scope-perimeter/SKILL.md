---
name: scope-perimeter
description: Bound the idea's shape. Produce a defensible out-of-scope section, the this-iteration-vs-later split, and the exposure-aware judgment. The primary defense against downstream scope sprawl. Load when /shape is invoked.
---

# Scope perimeter

This skill exists because the meta-failure this workspace prevents is bundles that license downstream expansion. The perimeter is what prevents that. Weak perimeter = weak handoff.

## The three perimeter moves

**1. Define what's in.** For each major element of the idea, state what execution produces. Concrete. Not "a research workflow" — "a weekly synthesis protocol, a tagging skill, a literature-summary template." Granular enough that a fresh session could build a checklist from it.

**2. Define what's out.** As substantive as what's in. For each boundary, state what's excluded and why. "Out of scope: cross-document synthesis. Reason: current goal is summarizing each source individually, not weaving them together. Synthesis lives in a separate iteration." The reason matters — downstream sessions respect constraints with reasoning more than arbitrary-seeming ones.

For seeds with stakeholder dependencies, explicitly exclude *work that requires others' commitment* as out-of-scope, with reason. The bundle handles what the user can do unilaterally; coordination work, positioning conversations, and political moves belong to a different conversation. This is a recurring pattern in workplace seeds and earns explicit naming.

**3. Split this-iteration-vs-later.** Most interesting ideas have more surface than one iteration covers well. Capture later iterations as named-and-parked — they live in `DECISIONS.md` as future work, not lost, but they don't leak into the current handoff. This is how the workspace honors ambition without sprawl.

For iteration seeds: ask whether *this* iteration's perimeter includes structural choices that govern future iterations' tractability. Often the user's actual goal is "make extension easier next time," which is a structural decision about the system's shape, not just about this iteration's content. If so, those structural choices need their own decision records and scope-bounding — they're easy to leave implicit and they shouldn't be.

## Exposure-aware perimeter

The perimeter shape adjusts to the exposure read from calibration:

- **Leaf:** standard perimeter. In-scope, out-of-scope, this-vs-later. Done.
- **Architectural core:** add explicit constraints on *how* the work is done. Stronger verification criteria in done-definition. Possibly a staged execution plan rather than a one-shot handoff — flagging this in `SPEC.md` for handoff-packaging to consider.
- **Non-architectural core:** add explicit conditions for the work — what political/organizational state the bundle assumes. If those conditions break, the downstream session pauses rather than continues. The bundle isn't unconditional.

If an idea is majority-core (architectural or non-architectural), handoff shape changes. Consider whether the downstream session should itself be multi-stage with verification gates between stages, rather than one fresh-session execution.

## Writing the out-of-scope section

Every clause must pass: **would removing it cause the downstream session to expand its work?** If yes, the clause earns its place. If no, cut it — out-of-scope bloats the same way `CLAUDE.md` can.

Patterns that work:
- "X is out of scope. Reason: [substantive]. Owner: [where it lives instead — later iteration, different project, not-doing]."
- "If the downstream session identifies an opportunity to do X, the correct move is to stop and return, not to expand."
- Named anti-goals when relevant — things the idea must *not* become.
- For stakeholder-dependent seeds: "Work requiring [stakeholder]'s commitment is out of scope. Reason: this bundle handles what the user can do unilaterally. Coordination work belongs to a separate conversation."

## Common failure modes

- **Out-of-scope section that just negates in-scope.** That's tautology, not boundary-setting. Out-of-scope must name *specific* excluded territory plausibly in reach.
- **Aspirational "this iteration" framing that's really two iterations.** If in-scope has two distinct deliverables that could run independently, consider two bundles.
- **Reason-free exclusions.** "X is out of scope" with no reason gets ignored downstream. Every exclusion has a why.
- **Treating exposure as binary.** Most non-trivial ideas have leaf parts and core parts. Record which parts are which; don't force a single label.
- **Implicit structural decisions in iteration seeds.** When the user's real goal is making future extension easier, surface that as a structural decision and bound it explicitly.
- **No-conditions handoff for non-architectural core.** Bundles that depend on stakeholder/organizational state must surface those dependencies as conditions, not bury them.
