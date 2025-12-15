# ADR-0001: Repository Scope & Structure

## Status
Accepted

## Context
This repository is intended to be usable by others and sustainable over time. The core risk is that it becomes either:
- overly personal (hard for others to apply), or
- overly abstract (not runnable).

We also want a clear separation between stable guidance and evolving experimentation.

## Decision
We will separate content into four primary areas:
- `docs/` — canonical playbook sections (publication-quality)
- `decisions/` — Architecture Decision Records (the “why” behind major choices)
- `checklists/` — runnable operational steps
- `progress/` — implementation journal / field notes

## Consequences
### Positive
- Readers can consume stable guidance without noise.
- Decisions are transparent and reviewable.
- Experiments can evolve without rewriting doctrine.

### Tradeoffs
- Requires discipline: changes that alter direction should include an ADR.
- Some duplication is acceptable (docs summarize; progress narrates).

## Revisit criteria
Revisit this structure if:
- The repo grows to include substantial code/configuration, or
- Community contributions increase and require stronger governance.
