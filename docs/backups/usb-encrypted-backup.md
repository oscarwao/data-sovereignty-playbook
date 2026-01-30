# Encrypted USB Backup – Laptop Baseline

## Purpose
This backup strategy provides an offline, encrypted, user-controlled backup
aligned with data sovereignty principles. It avoids vendor lock-in and allows
full restores using standard Linux tools.

## Storage Medium
- 256 GB USB thumb drive
- Encrypted using LUKS
- Filesystem: ext4

## Backup Scope
- Home directory (`/home/$USER`)
- User configuration (`~/.config`)
- Excludes caches, node_modules, trash

## Backup Method
- rsync with hard-linked snapshots
- Incremental backups
- Human-readable structure
- No proprietary tooling

## Directory Structure
/mnt/backup
├── snapshots/
│ ├── 2026-01-30/
│ │ ├── home/
│ │ └── config/
├── current -> snapshots/2026-01-30


## Security
- LUKS full-disk encryption
- Passphrase stored in password manager
- Offline by default

## Restore
See: Restore Checklist (included in this document)

## Status
Active – manual or scheduled runs
