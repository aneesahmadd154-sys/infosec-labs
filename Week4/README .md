# Week 4: Role-Based Access Control (RBAC) on Linux

## Goal
Give access to **roles** instead of individual people, and give each role only what it needs (least privilege).

## What I did
1. Created five role groups: faculty, registrar, hr, itsec and comms.
2. Created six users and placed each in a role. One user (an intern) had no role, to test that access is denied.
3. Built shared folders for each role with group ownership and the **setgid bit** (`2770`), so new files stay owned by the group.
4. Filled in a role-access matrix, then tested access **as each user** and compared expected and actual results.
5. Wrote a **least-privilege sudo rule** with `visudo`: the itsec role can check the SSH service and read its log, and nothing else.
6. Tested that allowed commands work and everything else is refused.
7. Walked an account through its lifecycle:
   - **Joiner:** new user gets access just by joining a role
   - **Mover:** user changes role, so old access is removed and new access added
   - **Leaver:** account is locked and expired, not deleted

## Key ideas
- Users get access through a role; when someone changes jobs, change their role, not hundreds of permissions.
- Use `usermod -aG` (with `-a`). Without it, the user's other groups are silently removed.
- Test as the user (`sudo -u name`), not as admin, because admin can read almost everything.
- Never use broad rules like `ALL=(ALL) NOPASSWD: ALL`. Avoid sudo on programs that can open a shell.
- People who administer a system should not be the only ones who can erase its logs (separation of duties).

## Tools
`groupadd`, `useradd`, `usermod`, `gpasswd`, `id`, `getent`, `visudo`, `sudo -l`, `chage`, `find`
