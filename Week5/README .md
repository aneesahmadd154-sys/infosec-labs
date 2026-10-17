# Week 5: Authentication, Password Policy and MFA

## Goal
See how Linux stores passwords, force stronger ones, and add a second factor so a stolen password is not enough.

## What I did
1. **Password storage:** compared the permissions of `/etc/passwd` (readable by all) and `/etc/shadow` (restricted). Read a shadow record and identified the algorithm, the salt and the hash.
2. **Salt demo:** gave three accounts the same password and saw three different hashes. A plain SHA-256 hash, with no salt, gives the same output every time.
3. **Password policy:** set rules for minimum length, character types and repeated characters. Set password aging with `chage`. Tested weak passwords and saw each one rejected with a reason.
4. **MFA:** set up time-based one-time passwords (TOTP) for `su` using PAM and an authenticator app.
5. **Tested MFA** with a correct code, a wrong code, a reused code, an account without MFA and a root login.
6. **Recovery:** used a one-time emergency code, reset a user's enrolment and rolled back the PAM change.

## Key ideas
- Three authentication factors: something you know, have and are. MFA combines at least two.
- Linux stores a salted one-way hash, never the password itself.
- Salt makes identical passwords produce different hashes and defeats precomputed tables.
- Setting `nullok` lets accounts without MFA in, and root bypasses the check. A control is only as strong as its weakest exemption.
- Back up PAM files before editing and keep a second root shell open so you can't lock yourself out.

## Tools
`/etc/shadow`, `openssl passwd`, `sha256sum`, `pam_pwquality`, `chage`, `google-authenticator`, `oathtool`, PAM
