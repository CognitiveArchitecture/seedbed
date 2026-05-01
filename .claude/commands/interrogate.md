---
description: Invoke interview move on the current idea
---

Load `.claude/skills/interview-craft/SKILL.md`.

Read the current idea's `STATE.md` and `INTERVIEW.md`. Continue interrogation from where the last session ended, or begin if `INTERVIEW.md` is empty.

Ask one question at a time. Write each Q+A to `INTERVIEW.md` as you go — the record must survive mid-session context loss. Do not ask questions the staging area already answers.

If interrogation surfaces that the real idea is adjacent to what was originally described, stop and recommend `/seed` re-calibration. Do not continue interrogating against an outdated framing.

Exit conditions:
- User declares interrogation complete
- Remaining unknowns are design-time unknowns (record in `DECISIONS.md` as live questions), not answerable questions

Update `STATE.md` on exit with next move.
