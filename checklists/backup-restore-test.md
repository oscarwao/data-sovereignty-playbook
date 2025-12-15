# Backup & Restore Test Checklist

Goal: backups are only real if restores work.

## Define scope
- [ ] Identify your Tier 1 data (must not be lost)
- [ ] Identify Tier 2 data (important, but replaceable)
- [ ] Identify what is intentionally excluded

## Execute backup
- [ ] Run a backup (manual or automated)
- [ ] Ensure backup is encrypted (where applicable)
- [ ] Store at least one copy offsite

## Validate
- [ ] Confirm backup completed without errors
- [ ] Verify file counts / sample file integrity

## Restore test
- [ ] Restore a single file
- [ ] Restore a folder (multiple files)
- [ ] Confirm permissions and readability

## Document
- [ ] Record results in /progress (date, tool, issues, next steps)
