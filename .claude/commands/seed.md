---
description: Initiate a new idea and enter Intake phase
argument-hint: <idea-slug>
---

Load `.claude/skills/intake-calibration/SKILL.md`.

Create `staging/$ARGUMENTS/` with:
- `STATE.md` — populated per the template in `CLAUDE.md`, phase: intake
- `SPEC.md` — empty
- `INTERVIEW.md` — empty
- `DECISIONS.md` — empty

Perform intake calibration per the loaded skill. Do not proceed past calibration without explicit user confirmation. Calibration outputs are recorded in `STATE.md` and shape subsequent phases.

If `staging/$ARGUMENTS/` already exists, stop. Report the conflict. Offer `/resume $ARGUMENTS` instead.
