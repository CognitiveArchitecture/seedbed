---
name: handoff-packaging
description: Run the seven-point promotion gate and produce the outbox bundle, or refuse promotion with reasons. Writes the execution prompt — the bundle's load-bearing artifact. Load when /promote is invoked.
---

# Handoff packaging

The workspace's quality claim lives or dies here. A bundle that passes the gate but fails downstream is a packaging failure — tighten the gate, don't loosen it.

## The seven-point gate

Run every check. Report pass/fail with specific evidence. Refuse promotion on any fail.

**1. Goals-clear.** `SPEC.md` opens with what this is *for* and what it is *not for*, one paragraph each. No euphemism, no hedging.

**2. Decisions closed.** `DECISIONS.md` contains every significant choice with reasoning. Test: pick three non-obvious decisions and check that the reasoning explains why that choice and not the alternatives.

**3. Scope bounded.** `SPEC.md` has an out-of-scope section as substantive as in-scope. Each out-of-scope item has a reason. The this-iteration-vs-later split is explicit. For non-architectural core seeds, conditions on which the bundle depends are explicit.

**4. Adversarially challenged.** `CHALLENGE.md` exists. Each finding is either absorbed (fixed in SPEC/DECISIONS) or declared-acceptable with reasoning. No unresolved findings.

**5. Resources provisioned.** If the idea warranted provisioning, `resources/` contains what downstream needs. If not, note the absence explicitly in `SPEC.md` so downstream doesn't hunt for missing files.

**6. Skills honest.** `output-skills/` contains only `SKILL.md` files that meet the four criteria. Empty is fine — note why in `SPEC.md`.

**7. Execution prompt bounds, not describes.** `EXECUTION-PROMPT.md` is written to constrain scope. Scope-pressure test: could a fresh session reading this legitimately expand the work beyond intended bounds? If yes, rewrite.

## Writing the execution prompt

The execution prompt is the bundle's load-bearing artifact. Weight its construction accordingly. It does not re-explain the idea — `SPEC.md` does that. It frames *how the downstream session should hold itself*.

Structure:

```
# Execution prompt: <idea name>

## What you're doing
[One paragraph. The outcome, not the process.]

## What you have
[Bundle contents listed with one-line descriptions.]

## What's out of scope
[Substantive. If during execution you identify an opportunity to do something listed here, stop and return to the user — do not expand.]

## Conditions for this work
[Optional. Include for non-architectural core bundles or any bundle whose validity depends on external state. State the assumed conditions explicitly. If the conditions change, the downstream returns to the user rather than continuing.]

## How to know when you're done
[Specific. Checkable. Behavior-driven. Testable by user alone.]

## Open questions for the user
[Items recorded in DECISIONS.md as live unknowns, surfaced here so downstream resolves them with the user rather than guessing.]
```

The "Conditions for this work" section is optional — include only when the bundle has real external dependencies. Padding it onto bundles that don't need it dilutes the section's meaning when it does.

## Promotion act

All seven pass:

1. Create `outbox/<idea-slug>/`
2. Copy `SPEC.md`, `DECISIONS.md`, `resources/`, `output-skills/` (renamed `skills/`)
3. Write `EXECUTION-PROMPT.md` fresh — not copied; engineered for handoff
4. Write `MANIFEST.md` — one paragraph listing contents for human orientation
5. Update `staging/<idea-slug>/STATE.md`: phase promoted, timestamp, outbox path

Staging remains after promotion for auditability. Archive only on explicit user direction.

## Refusing promotion

When any check fails:
- Name which checks failed
- State what evidence was missing or insufficient
- Give the specific next move to close each gap (which phase to return to, what to produce)

Do not promote partial bundles. Do not offer to promote with caveats. A refused promotion is the workspace working.

## Common failure modes

- **Passing checks generously.** At this point, instinct wants to declare done. Distrust it.
- **Execution prompt as summary.** It's a constraint engine. Summaries license expansion; constraints bound it.
- **Skipping `MANIFEST.md`.** Small artifact, outsized re-orientation value weeks later.
- **Treating promotion as ceremonial.** The check sequence *is* the move, not its wrapper.
- **Padding "Conditions for this work" onto bundles that don't need it.** Dilutes the section when it matters.
