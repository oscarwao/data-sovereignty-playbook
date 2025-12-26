# ADR-0003: Fedora Workstation Baseline and Backup Strategy

## Status
Accepted

## Date
2025-12-24

---

## Context
As part of a broader exploration of data sovereignty, I rebuilt a personal workstation using Fedora Workstation on Framework hardware.

The goal was not novelty, but control:
- understanding where data lives,
- ensuring recoverability,
- and preserving agency over tools.

Early attempts combined multiple advanced controls at once (encryption, Secure Boot, SELinux), which surfaced avoidable complexity during first boot and recovery. Given the low cost of restarting early, I chose to reinstall cleanly rather than salvage an ambiguous system state.

---

## Decision
I established a clean Fedora baseline with:
- Full-disk encryption enabled
- Secure Boot left on (default)
- Fedora’s default Btrfs layout
- Minimal post-install changes
- Backups implemented before automation or cloud sync

Backups were treated as a first-class sovereignty control, not an afterthought.

---

## Rationale
Encryption protects data at rest but does not address:
- device loss,
- hardware failure,
- user error,
- or misconfiguration.

A sovereignty-aligned system must support calm recovery.

Manual, local-first backups were prioritized to build confidence and understanding before introducing automation or additional destinations.

---

## Backup Design Choices
- Tool: restic (encrypted by default, simple restore model)
- Storage: Dedicated external SSD
- Execution: Manual
- Scope: Critical personal data only

A restore test was performed before trusting the backup.

---

## Tradeoffs Accepted
- Single backup destination
- No off-site copy initially
- No scheduled automation

These constraints were intentional to reduce cognitive load and ensure clarity during early learning.

---

## Outcome
The resulting system is:
- stable,
- encrypted,
- recoverable,
- and understandable.

This baseline now serves as a known-good foundation for further experimentation.

---

## Reflection
Restarting early was the correct decision.

When system state becomes ambiguous and learning cost is low, rebuilding preserves confidence and prevents cargo-cult security.

Data sovereignty is not achieved through maximal controls, but through intentional systems with clear recovery paths.
