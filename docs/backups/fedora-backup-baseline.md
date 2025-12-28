# Fedora Backup Baseline (Local-First)

This document defines the **practical backup baseline** for a Fedora Workstation
used in the Data Sovereignty Playbook.

The goal is not maximal redundancy or complexity, but **provable recoverability**
with minimal moving parts.

---

## Objectives

This baseline ensures:

- Data is recoverable after loss, theft, or system failure
- Backups are understandable under stress
- Restore procedures are documented and tested
- Automation does not obscure failure modes

This is a *human-operable* system first, automated second.

---

## Scope

### In Scope
- User data under `/home`
- Notes, documents, and knowledge artifacts
- Configuration files with high recovery value

### Out of Scope (for now)
- Full system image restores
- Cloud-based backup services
- Continuous background syncing

---

## Tooling Choice

### Backup Tool
- **Restic**
  - Encrypted by default
  - Content-addressed
  - Simple CLI
  - Well-documented restore semantics

### Backup Target
- **Locally attached external drive**
- Encrypted repository
- Human-controlled attachment (not always connected)

This aligns with a *local-first, offline-capable* posture.

---

## Backup Model

### Data Tiers

| Tier | Description | Examples |
|----|-----------|---------|
| Tier 1 | Irreplaceable | Notes, documents, personal data |
| Tier 2 | Reproducible | Downloads, caches |
| Tier 3 | Disposable | Temp files |

**Only Tier 1 and selected Tier 2 data are backed up.**

---

## What Gets Backed Up

Example paths (adjust as needed):

```text
/home/<user>/Documents
/home/<user>/Notes
/home/<user>/.config (selectively)


---------
## Encryption & Secrets

## Repository encryption handled by Restic

## Passphrase stored in:

## Password manager (authoritative)

## Local file with restrictive permissions for automation

## At no point should the passphrase be hard-coded into scripts or repositories.

## Automation Strategy

## Backups triggered via systemd user timer

## Weekly cadence

## Backup only runs when the external drive is present

## Clean failure when drive is absent (no silent success)

## Automation exists to reduce forgetting, not to hide state.

## Verification Requirement

## Backups are not considered valid until:

## restic snapshots succeeds

## A file restore has been performed

## A directory restore has been performed

See:

docs/backups/restore-checklist.md
