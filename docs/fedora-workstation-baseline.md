# Fedora Workstation Baseline (Data Sovereignty-Oriented)

## Purpose
This document describes a minimal, reliable baseline for running Fedora Workstation in a way that prioritizes data sovereignty, recoverability, and operational clarity.

The goal is not maximal hardening, but a system that is:
- understandable,
- recoverable,
- and resilient under stress.

---

## System Profile
- Operating system: Fedora Workstation
- Hardware: Framework Laptop (or equivalent)
- Usage model: Daily driver for thinking, writing, and experimentation
- Threat posture: Device loss, user error, misconfiguration

---

## Installation Best Practices

### Disk & Filesystem
- Use entire disk
- Enable full-disk encryption (LUKS)
- Accept Fedora’s default Btrfs layout

Rationale: Fedora’s defaults balance security, recoverability, and maintainability without manual partitioning risk.

---

### Encryption
- Use a long, word-based passphrase
- Favor length and reliability over cleverness
- Avoid symbols or layout-sensitive characters

Disk encryption passphrases are typed rarely and should optimize for correctness under stress.

---

### Secure Boot
- Enabled by default

Secure Boot protects the boot chain and strengthens encryption guarantees. Fedora supports this path cleanly.

---

### User Setup
- Primary user is an administrator (wheel)
- Login password optimized for daily usability, not cryptographic strength

Disk passphrases and login passwords serve different purposes and should remain distinct.

---

## Post-Install Baseline

### System Updates
```bash
sudo dnf upgrade --refresh -y
