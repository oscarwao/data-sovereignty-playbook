---
Status: Draft
Last updated: 2025-12-14
NIST CSF: PR.IP, PR.DS
---

# Fedora Workstation Baseline

Fedora Workstation is treated as a **managed endpoint**, not a tinkering platform.

## Baseline posture
- Full-disk encryption (LUKS)
- Secure Boot enabled
- Automatic security updates
- Firewall enabled
- SELinux enforcing
- Flatpak-first application model
- Rootless containers (Podman)

This baseline provides a stable foundation for all higher-level decisions.
