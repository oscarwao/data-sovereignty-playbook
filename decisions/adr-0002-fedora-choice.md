# ADR-0002: Fedora Workstation as the Baseline Distribution

## Status
Accepted

## Context
The playbook requires a Linux baseline that:
- is modern and well-supported on contemporary laptop hardware,
- aligns with enterprise security posture and defaults,
- supports current development workflows (containers, modern packages),
- minimizes “distro friction” while remaining transparent.

## Decision
Use **Fedora Workstation** as the baseline Linux distribution.

## Alternatives considered
- **Ubuntu LTS** — strong stability and ecosystem, but slower-moving packages and some ecosystem preferences.
- **Pop!_OS** — good defaults, strong UX, but smaller ecosystem and dependency on Ubuntu base decisions.
- **Debian Stable** — excellent stability, but can lag on newer laptop hardware enablement.
- **Arch** — highly flexible, but increases maintenance burden and variance.

## Consequences
### Positive
- Modern security defaults and rapid patching cadence.
- Strong laptop compatibility and upstream alignment.
- Good fit for container-first workflows.

### Tradeoffs
- Faster release cadence than LTS distributions.
- Requires periodic upgrades (planned maintenance).

## Revisit criteria
Revisit this decision if:
- Hardware support changes materially, or
- A future baseline better meets the goals of security + sustainability with lower operational effort.
