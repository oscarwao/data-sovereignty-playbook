# Repo Management Playbook

## Purpose
This playbook defines how this repository is maintained so it remains readable,
disciplined, and valuable to others over time.

---

## Operating model
- Stable guidance lives in `/docs`
- Decisions live in `/decisions` (ADRs)
- Runnable steps live in `/checklists`
- Lived experience and iteration live in `/progress`

---

## Branching discipline
- No direct commits to `main`
- All work happens in a feature branch
- All changes flow through a Pull Request

### Branch naming
- `docs/<topic>`
- `feature/<topic>`
- `experiment/<topic>`
- `ops/<topic>`
- `fix/<topic>`

---

## Pull request standard
Each PR should clearly state:
- What changed
- Why it changed
- Where it belongs (docs, ADR, checklist, progress)

Merge strategy: **Create a merge commit**

---

## Commit hygiene
- Write commits that read like a narrative
- Keep commits small and intentional
- Avoid vague messages

Examples:
- `Docs: add transition matrix`
- `Governance: ADR for email provider choice`
- `Ops: add restore verification steps`

---

## ADR policy
Write an ADR when:
- Selecting or changing a baseline tool
- Reversing a previous decision
- Adding a new domain or lifecycle rule

ADR minimum:
- Context
- Decision
- Alternatives
- Consequences
- Revisit criteria

---

## Monthly workflow
1. Pull latest `main`
2. Create a feature branch
3. Decide where changes belong
4. Update `/progress/YYYY/YYYY-MM.md`
5. Commit in logical chunks
6. Push branch
7. Open PR
8. Merge with merge commit
9. Delete branch

---

## Documentation quality bar
- Plain language first
- Tradeoffs stated explicitly
- Reproducible steps where applicable
- Status header on all docs

---

## Definition of done
A section is “done enough” when it has:
- Clear target state
- Tradeoffs
- Checklist or runnable steps
- ADR if it represents a decision
- Evidence of testing or stated assumptions
