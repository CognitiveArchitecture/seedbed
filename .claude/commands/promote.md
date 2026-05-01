---
description: Run promotion gate; produce outbox bundle or refuse with reasons
---

Load `.claude/skills/handoff-packaging/SKILL.md`.

Run the seven-point gate specified in the skill. For each check, report pass/fail with specific evidence.

Any failure → refuse promotion. Name each failure and the next move required to close it. Do not promote partial bundles.

All passes:
- Create `outbox/<idea-slug>/`
- Write `EXECUTION-PROMPT.md` fresh — engineered to bound downstream scope, not describe the idea
- Copy `SPEC.md`, `DECISIONS.md`, `resources/`, and `output-skills/` (renamed `skills/`) into the bundle
- Write `MANIFEST.md` listing contents
- Update `staging/<idea-slug>/STATE.md`: phase promoted, timestamp, outbox path

Staging remains for auditability. Archive or delete only on explicit user direction.
