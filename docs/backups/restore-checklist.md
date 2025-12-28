# Restore Checklist — Fedora Workstation

This checklist verifies that backups are real, usable, and understandable
under stress. A backup that has not been restored is unproven.

## Preconditions
- Fedora Workstation installed and bootable
- Restic installed
- Backup repository accessible (external drive mounted)
- Backup passphrase available

---

## Step 1: Mount Backup Drive

Confirm the backup drive is mounted.

###  Expected: BACKUP_PRIMARY (or equivalent label) is present.

```bash
ls /media/$USER/
----

## Step 2: Set Environment Variables

```bash

export RESTIC_REPOSITORY=/media/$USER/BACKUP_PRIMARY/restic
export RESTIC_PASSWORD=<retrieve from password manager>

## Do not proceed if the password is unknown.

## Step 3: Verify Repository Access

``bash

restic snapshots

### Expected: At least one snapshot is listed; No authentication or repository errors

## Step 4: Inspect Snapshot Contents

``` bash

restic ls latest

## Expected: Files and directories appear as expected | Tier 1 paths are present

## Step 5: Restore a Single File (Smoke Test)

```bash

mkdir -p /tmp/restore-test

restic restore latest \
  --target /tmp/restore-test \
  --include /home/<user>/Documents/<known-file>

## Expected: Command completes without error : File exists at: /tmp/restore-test/home/<user>/Documents/<known-file>


## Step 6: Restore a Directory (Partial Restore).

```bash

restic restore latest \
  --target /tmp/restore-test \
  --include /home/<user>/Documents

## Expected: Directory structure preserved | Files readable and intact.

## Step 7: Clean Up

```bash

rm -rf /tmp/restore-test

## Exit Criteria

## All of the following must be true:

## Repository accessible

## Snapshots readable

## File restore successful

## Directory restore successful

##If any step fails, backups are considered non-functional.

