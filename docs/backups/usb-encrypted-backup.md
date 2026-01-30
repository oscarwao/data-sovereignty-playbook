# Encrypted USB Backup – Laptop Baseline

## Overview
This document describes the setup and use of an encrypted USB backup
for a Fedora Linux laptop. The goal is to maintain offline, user-owned,
vendor-neutral backups aligned with data sovereignty principles.

## Storage Medium
- 256 GB USB thumb drive
- Full-disk encryption using LUKS
- Filesystem: ext4
- Mounted at `/mnt/backup` when unlocked

## Device Mapping
- Raw device: `/dev/sda`
- Encrypted mapping: `LAPTOP-BACKUP`
- Mount point: `/mnt/backup`

## Backup Scope
- `/home/$USER`
- `~/.config`
- Excludes caches, trash, and build artifacts

## Directory Structure
/mnt/backup
├── snapshots/
│ └── initial/
│ ├── home/
│ └── config/
└── meta/
└── README.txt


## Restore (High-Level)
1. Unlock device:
   ```bash
   sudo cryptsetup open /dev/sda LAPTOP-BACKUP
2. Mount
sudo mount /dev/mapper/LAPTOP-BACKUP /mnt/backup

3. Restore files using rsync

4. Clean Shutdown (Important Habit)
   ```bash
   sync
    sudo umount /mnt/backup
    sudo cryptsetup close LAPTOP-BACKUP
