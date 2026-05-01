---
name: adversarial-attacks
description: Library of attack patterns for stress-testing a bundle before promotion. Selects attacks based on the bundle's exposure profile and seed type. Tries to break the bundle, not validate it. Load when /challenge is invoked.
---

# Adversarial attacks

The challenge phase exists to find reasons the bundle should not ship. Approach it that way. The energy is *trying to break this*, not *confirming it's sound*. A challenge that finds nothing is suspicious before it's reassuring.

Select attacks based on the bundle's exposure profile and seed type. Not every attack applies to every bundle; running attacks that don't fit produces noise. The skill's job is matching attacks to bundles.

## Attack patterns

### 1. Scope-pressure attack (apply to every bundle)

The primary attack. Read the bundle as a fresh session that wants to do good work. Where does it license expansion?

- For each in-scope item, can the downstream session find a plausible adjacent move that the bundle doesn't explicitly forbid?
- For each out-of-scope item, is the exclusion specific enough that a downstream session reading in good faith would respect it?
- Does the execution prompt frame the work as bounded, or as something to expand on?

If a fresh session could legitimately expand the work and claim it was within scope, the perimeter has a hole. Record the specific hole and the move that should close it.

### 2. Symptom-vs-structure attack (apply to iteration seeds)

Iteration seeds risk fixing the symptom rather than the structural cause. Re-read the bundle and ask:

- What was the user's reported failure mode?
- What does the bundle change?
- Does the change address the *structure* that produces the failure mode, or just the symptom?

A bundle that addresses the symptom will sometimes work and sometimes fail to. A bundle that addresses the structure should durably resolve the failure mode. If the bundle is symptom-level, name what structural change would actually address the cause.

### 3. Framing-collapse attack (apply to non-architectural core seeds)

Bundles whose framing depends on political, relational, or organizational state must survive shifts in that state. Attack the framing:

- If [stakeholder] reorganizes / leaves / shifts position, what survives in this bundle?
- If the assumed organizational state shifts, does the bundle still produce something valuable, or does its value collapse with the framing?
- Are the conditions on which the bundle depends made explicit, or are they buried?

A bundle that collapses entirely with a state shift is contingent. Contingency isn't disqualifying — but it must be *visible* in the bundle. Record where the bundle hides its contingencies, and surface them.

### 4. Technical-contingency attack (apply to bundles depending on external technical state)

If the bundle depends on a library, model, API, or service behaving consistently:

- What happens if the dependency changes shape?
- Is the dependency's expected shape documented in the bundle?
- Are there fallback or detection mechanisms, or does the bundle silently break?

Same logic as framing-collapse: contingencies must be visible. Hidden ones are time bombs.

### 5. Ownership-leak attack (apply to synthesis seeds)

Synthesis seeds risk consolidating content that belongs to others. Attack:

- For each piece of consolidated material, who actually owns it?
- Does the bundle treat anyone else's content as the user's to consolidate?
- Does the execution prompt accidentally license the downstream to copy or modify content owned elsewhere?

Record any case where the bundle's authority over a piece of source material is unclear.

### 6. Definition-of-done attack (apply to every bundle)

Re-read the definition of done. Apply both bars from intake-calibration:

- **Testable by user alone.** Can the user verify done-ness without another person's response?
- **Artifact or behavior, not quality.** Is "done" something checkable, or is it a hope?

If the definition-of-done failed either bar at intake but slipped through, this is the catch.

### 7. Provisioning-fit attack (apply to bundles with provisioned resources)

For each provisioned resource:

- Will the downstream actually use it, or is it noise?
- Are any obvious resources *missing* — things the downstream will need that aren't there?

Over-provisioning and under-provisioning are both real failures. Both surface here.

## Selection heuristic

Run scope-pressure and definition-of-done on every bundle. Select others based on the calibration:

| Seed type | Add these attacks |
|---|---|
| Iteration | Symptom-vs-structure |
| Synthesis | Ownership-leak |
| Greenfield | (no specific add) |

| Exposure | Add these attacks |
|---|---|
| Architectural core | Technical-contingency |
| Non-architectural core | Framing-collapse |
| Mixed | Both |

| Provisioning state | Add these attacks |
|---|---|
| Resources provisioned | Provisioning-fit |
| No resources | (skip) |

## Recording findings

Write `CHALLENGE.md`. For each finding:

- **Attack type** (which pattern surfaced it)
- **Specific evidence** (what in the bundle invites the failure)
- **Disposition**: absorb (return to Shape/Provision and fix) or declare-acceptable (note reasoning)

A finding declared acceptable must have reasoning. "It's fine" doesn't pass — name *why* this contingency or hole is acceptable for this bundle.

## Common failure modes

- **Generous reading.** The challenger's instinct should be to find problems. Suppress the urge to read favorably.
- **Running every attack.** Attacks that don't fit produce noise; the selection heuristic exists to keep challenge focused.
- **Declaring acceptable too quickly.** Real reasoning, not waving away.
- **Treating clean challenge as good.** A bundle that survives challenge with no findings is rare. Suspect the challenge before celebrating the bundle.
