# ADR-0004: Repository Scope Includes Data Sovereignty Playbooks and Experiments

## Status
Accepted

## Date
[YYYY-MM-DD]

## Context

This repository originated as a platform-focused baseline (e.g., Fedora workstation configuration, backups, operational hardening). As the work evolved, it became clear that **platform baselines alone are insufficient** to support modern data governance and data sovereignty goals.

Data sovereignty is not achieved solely through technical configuration. It emerges from:
- Explicit governance intent
- Clear authority and accountability over data
- Identity and access control decisions
- Exit readiness and portability
- Ethical considerations around use, benefit, and stewardship

To address this gap, structured **data sovereignty experiments** and **playbooks** were developed to safely test, document, and refine governance and architectural decisions before they are embedded into platform baselines or organizational policy.

This ADR establishes the repository as the authoritative home for those artifacts.

## Decision

This repository SHALL include:
- **Data sovereignty playbooks** describing how experiments are designed and executed
- **Experiment artifacts** that generate evidence, tradeoffs, and learning
- **Architecture Decision Records (ADRs)** capturing durable outcomes from experiments
- **Platform baselines** (e.g., Fedora) as implementations of those decisions

The repository scope is explicitly expanded from *platform configuration* to **sovereign ecosystem design**, where governance, identity, data placement, and exit readiness are treated as first-class architectural concerns.

## Rationale

This decision is grounded in the following principles:

1. **Data sovereignty precedes tooling**  
   Governance intent and authority must be defined before selecting or configuring platforms.

2. **Experiments reduce irreversible risk**  
   Sovereignty decisions often involve tradeoffs (cost, usability, operational overhead). Experiments allow these tradeoffs to be understood before institutionalizing them.

3. **Identity and data governance are architectural concerns**  
   These decisions materially affect security, compliance, resilience, and trust and therefore belong alongside system baselines and ADRs.

4. **Platform baselines are implementations, not strategy**  
   Fedora and other platform configurations represent one expression of broader governance and sovereignty decisions captured elsewhere in the repository.

## Consequences

### Positive
- Clear separation between **learning**, **decision-making**, and **implementation**
- Reusable sovereignty patterns that can scale from personal to organizational contexts
- Stronger auditability and narrative coherence for why certain technical choices exist
- Reduced risk of ad-hoc or vendor-driven architecture

### Tradeoffs
- Broader repository scope requires clearer structure and documentation discipline
- Some artifacts are conceptual rather than immediately executable
- Requires contributors to understand governance context, not just tooling

These tradeoffs are accepted as necessary to support long-term ecosystem control.

## Repository Structure Implications

This ADR affirms the following structure
/docs
/playbooks # How experiments are designed and run
/experiments # Evidence-producing sovereignty experiments
/reference-architectures
/decisions
/adrs # Durable architectural decisions
/fedora # Platform-specific baseline implementation


## Guiding References

This decision and the associated playbooks are informed by:

- **The CARE Principles for Indigenous Data Governance**  
  Emphasizing Collective Benefit, Authority to Control, Responsibility, and Ethics in data stewardship. :contentReference[oaicite:0]{index=0}

- **Indigenous Data Sovereignty – Study Guide**  
  Framing data as a governance asset and asserting the right of communities to control collection, use, and interpretation. :contentReference[oaicite:1]{index=1}

- **Governing Data and Data for Governance (Diane E. Smith)**  
  Establishing that effective governance depends on access to trusted, relevant data and the ability to govern that data intentionally. :contentReference[oaicite:2]{index=2}

These sources collectively reinforce the position that **data governance and sovereignty are operational practices**, not abstract policy statements, and must be exercised through intentional design and experimentation.

## Related Artifacts
- Data Sovereignty Experiments Playbook (v1.0)
- `/docs/experiments/*`
- Future ADRs derived from DS-EXP-### experiments

## Notes
This ADR does not mandate self-hosting or rejection of cloud or SaaS platforms. It mandates **intentional control, documented tradeoffs, and exit readiness** as non-negotiable design criteria.


