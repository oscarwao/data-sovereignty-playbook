# DS-EXP-001: Domain Ownership & Email Control Plane

## Owner
[Name]

## Status
Planned / In Progress / Completed

## Scope
Personal ☐ | Pilot ☐ | Organization ☐

## Hypothesis
If domain ownership, DNS, and mail routing are controlled independently of the email provider, email services can be changed with minimal disruption and reduced sovereignty risk.

## In Scope
- Domain registration and DNS control
- MX, SPF, DKIM, DMARC configuration
- Mail routing and provider dependency mapping

## Out of Scope
- Building a full self-hosted mail server (unless explicitly tested)
- End-user UX optimization

## Systems Involved
- Domain registrar
- DNS provider
- Email service provider(s)

## Data Classes Involved
- Communications
- Identity metadata

## Success Criteria
- Domain and DNS are fully transferable
- Email provider swap path is documented
- Administrative access and jurisdictional exposure are understood

## Risks & Mitigations
- Misconfigured DNS → staged rollout and validation
- Deliverability issues → SPF/DKIM/DMARC testing

## Expected Outputs
- Mail flow diagram
- DNS configuration summary
- Exit/migration notes

## Decision Signals
This experiment may trigger an ADR if:
- Domain ownership is deemed mandatory
- Provider lock-in risk is unacceptable

## Next Experiments
- DS-EXP-004 (Identity & Federation)
- DS-EXP-006 (Exit Simulation)
