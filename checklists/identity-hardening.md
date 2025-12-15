# Identity Hardening Checklist

Goal: reduce account takeover risk and minimize identity coupling.

## Passwords
- [ ] Choose a password manager as system of record
- [ ] Migrate critical logins into the manager
- [ ] Enable vault lock + strong master password
- [ ] Store recovery codes securely

## MFA
- [ ] Enable MFA on primary email
- [ ] Enable MFA on GitHub
- [ ] Enable MFA on your password manager account (if applicable)

## Reduce coupling
- [ ] Avoid “Sign in with Google/Apple” where possible
- [ ] Review and remove unused OAuth app integrations

## Recovery
- [ ] Verify account recovery methods (email/phone/keys)
- [ ] Test recovery path for at least one low-risk account
