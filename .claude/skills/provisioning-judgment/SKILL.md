---
name: provisioning-judgment
description: Decide whether and what to provision for an idea. Governs reference resources, frameworks, templates, and candidate output skills. Applies the four-criteria test for output skills. Load during /shape when provisioning might be warranted.
---

# Provisioning judgment

Provisioning is a judgment call, not a default. Over-provisioning generates reference material the downstream won't use; under-provisioning hands off a tidy SPEC that immediately hits "I need a model for X."

## When provisioning is warranted

Provision when one or more of:

- The idea has domain-specific terms-of-art the downstream shouldn't re-derive (records management: classification schemas; legal drafting: jurisdiction-specific terminology)
- The idea requires a framework choice among named alternatives (project planning: agile vs. waterfall vs. critical-path) and the choice has been made — the chosen framework gets its own reference artifact
- The downstream work references structured data (categories, taxonomies, templates) better held as files than prose in `SPEC.md`
- The idea is a synthesis seed — the existing scattered material itself needs to be inventoried and provisioned so the downstream isn't hunting for it
- The idea has repeatable moves that warrant output skills (see below)

Skip when:

- The downstream session can search as fast as it could read your reference
- The material is on the open web in authoritative form — link, don't restate
- The idea is narrow enough that `SPEC.md` + execution prompt is sufficient context
- Provisioning would just restate `SPEC.md`

## Types of resources

**Reference models.** Frameworks, taxonomies, schemas the downstream will reference.

**Templates.** Skeleton files the downstream fills in (blank weekly review, empty entry log, governance artifact template). Underrated — the most efficient way to communicate structure.

**Source-of-truth documents.** For iteration seeds, the relevant current state: what the existing system looks like now, which the downstream will modify. Often the single most important provisioned resource.

**Inventories.** For synthesis seeds, a structured account of what exists in scattered form: where each piece lives, who owns it, what shape it's in, whether it's in or out of scope for consolidation.

**Candidate output skills.** See below.

## Output skills — the four criteria

Draft an output `SKILL.md` only when all four hold:

1. **Repeatable.** The downstream work has moves that happen more than once. One-off actions don't earn skills.
2. **Sometimes-relevant.** If always-relevant, it belongs in the downstream `CLAUDE.md`, not a skill. Skills are for conditional context.
3. **Terms-of-art.** The move has domain vocabulary or conventions worth encoding rather than re-deriving.
4. **Done-definable.** You can articulate what the move looks like when done well. If you can't, the skill isn't ready — probably the move itself isn't crisp enough yet.

Failing any of these → don't draft it. Note it as a future-possible skill in `DECISIONS.md` and move on.

Negative criterion: **if a skill can't be named without hedging, it doesn't exist yet.** A skill called "general-approach" or "working-with-claude-on-X" is a sign the move isn't crisp. Don't ship it.

## Packaging

Provisioned files live in `staging/<idea>/resources/` and `staging/<idea>/output-skills/`. Real names (not `reference1.md`) and brief frontmatter noting what they are and why.

## Common failure modes

- **Drafting skills to seem thorough.** The bundle should not contain skills that don't meet the four criteria, no matter how productive drafting feels.
- **Restating the web.** Well-documented elsewhere → one-page crib sheet + link, not a full re-documentation.
- **Provisioning by analogy to other bundles.** Each idea's needs are its own.
- **Missing the source-of-truth doc for iterations.** For iteration seeds, the current-state document is usually the most important provisioned resource. Don't skip it.
- **Missing the inventory for synthesis seeds.** Synthesis without inventory is consolidation against an imagined source.
