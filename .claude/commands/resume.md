---
description: Reconstruct working state from staging and continue from recorded phase
argument-hint: <idea-slug>
---

Read `staging/$ARGUMENTS/STATE.md` first. `STATE.md` is authoritative — do not reconstruct state from chat history.

Report back:
- Seed framing
- Current phase
- What was last decided
- What's open
- Next move

If `STATE.md` is missing, malformed, or inconsistent with other staging files (e.g., phase says Shape but `SPEC.md` is empty), surface this explicitly. Do not confabulate. Ask the user to re-orient.

Then load the skill relevant to the current phase and await user direction. Resumption is orientation, not re-execution — do not auto-continue.
