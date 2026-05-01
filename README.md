# Seedbed: an idea-optimization workspace for Claude Code

## What it is

Seedbed is a structured workspace where ideas enter as seeds, move through six gated phases — Intake, Interrogate, Shape, Provision, Challenge, Promote — and emerge as bundles ready for execution in a fresh Claude Code session. The quality bar is whether a clean session, given only the bundle, can execute without asking the user clarifying questions.

## Why it exists

Idea-optimization conversations in Claude Code have a recurring failure mode: the output looks complete in the conversation that produced it, but doesn't hold against downstream scope pressure. A fresh execution session reads the artifact, finds it suggestive rather than constraining, and the work expands. Seedbed addresses the upstream side — producing handoffs whose structure and substance are designed to bound the downstream move, not invite reinterpretation.

## How it works

Six phases, each a gate (not a waterfall step). Transitions require explicit user confirmation. State for each idea lives in `staging/<idea-slug>/STATE.md`, the authoritative record across sessions.

- **Intake** — calibrate the seed: greenfield, iteration, or synthesis? What's the exposure, and what does "done" mean?
- **Interrogate** — interview the idea, one question at a time, digging into what's actually hard.
- **Shape** — decide and bound: declare what's in, what's out, what's this-iteration-vs-later.
- **Provision** — build reference resources, frameworks, and candidate output skills *when the idea warrants them*.
- **Challenge** — adversarial pass: try to break the bundle before it leaves.
- **Promote** — run the seven-point promotion gate; produce an outbox bundle, or refuse with reasons.

The corresponding slash commands:

- `/seed <name>` — initiate a new idea; enter Intake
- `/resume <name>` — reconstruct working state from `STATE.md`; continue from recorded phase
- `/interrogate` — interview move on the current idea
- `/shape` — declare decisions, bound scope
- `/challenge` — adversarial pass before promotion
- `/promote` — run promotion gate; produce outbox bundle or refuse

## Getting started

1. Clone this repository.
2. Open the directory in Claude Code.
3. Run `/seed <name>` on a first idea.

The first run is also the best test of the scaffold. If the structure feels overbuilt for a small idea, that's information about leaf-node calibration. If it feels under-built for a large one, the same.

## Structure

```
.
├── CLAUDE.md          # operating principles loaded each session
├── .claude/
│   ├── commands/      # six slash commands
│   └── skills/        # six on-demand skills, loaded per phase
├── staging/           # per-idea working directories
├── outbox/            # promoted bundles
└── archive/           # parked ideas
```

## Design grounding

Seedbed is an artifact of [Cognitive Architecture](https://cognitive-architecture.ca). Its design follows from explicit commitments about what AI partnership should be: tools that extend rather than replace human capacity, structures with explicit lifespans, named responsibility for what is produced, and honest accounting of limits. The scaffold is not value-neutral. It is shaped throughout by these commitments, and naming that grounding here is more useful than disguising it.

The philosophical lineage runs through two authors. From **Václav Havel** — particularly *The Power of the Powerless* and *Summer Meditations* — comes a political grounding around responsibility, human scale, and *living in truth*: the discipline of refusing the small accommodations that produce systemic dishonesty. From **Ivan Illich** — particularly *Tools for Conviviality* and *Deschooling Society* — comes a design ethics around conviviality, the *two watersheds* (the point past which a tool's growth ceases to serve its users), and the idea that freedom is enabled by appropriate limits, not abolished by them.

These commitments show up in concrete structural choices:

- **The promotion gate refuses to ship partial bundles.** This is the workspace's expression of *living in truth*: the seven-point check is designed so that "looks ready" does not pass for "is ready," and a refused promotion is the workspace working, not failing. *Output theatre* — artifacts that look complete rather than being complete — is named explicitly as a failure mode and structurally guarded against.
- **The discretion clause in interview-craft balances honest recording with appropriate scoping.** Substantive design-shaping content goes into `INTERVIEW.md`; political reads and working-relationship considerations inform interrogation but aren't recorded verbatim. Honesty is preserved; appropriate boundaries are too.
- **The explicit out-of-scope sections honor named responsibility for what the bundle does and doesn't claim.** Scope is treated as load-bearing — the out-of-scope section is as substantive as the in-scope section. The bundle commits to what it commits to, and visibly does not commit to anything else. Downstream sessions inherit those bounds, not vague invitations.

A research question for Cognitive Architecture animates this work: *does values-grounded design produce materially different collaborative artifacts than value-neutral design?* Seedbed is one data point. The answer is not assumed; it is being investigated through the artifacts themselves.

Adoption of the scaffold does not require adoption of the framework. The structural choices stand on their own: the phase gates, the promotion check, the out-of-scope sections, and the staging-as-state convention all work without philosophical commitment. The grounding is named here for readers who want to understand why the design has the shape it does.

## Sources

### Claude Code practices

- Anthropic, *Best practices for Claude Code*
- Erik Schluntz, "Vibe Coding in Prod (Responsibly)" — Code with Claude 2025
- Cat Wu and Boris Cherny, "How to use Claude Code like the people who built it" — *Every* podcast

### Philosophical grounding

- Václav Havel, *The Power of the Powerless* (1978); *Summer Meditations* (1992)
- Ivan Illich, *Tools for Conviviality* (1973); *Deschooling Society* (1971)

### Cognitive Architecture

[https://cognitive-architecture.ca](https://cognitive-architecture.ca)

## License

MIT. See [LICENSE](LICENSE).

## Status

Working scaffold; expected to evolve. Issues and pull requests are welcome. The maintainer's local fork may diverge from the public release based on personal use and ongoing research into governance-grounded design.
