# Week 3: File and Folder Permissions and ACLs on Linux

## Goal
Turn the Week 2 classification levels into real Linux access controls.

## What I did
1. Created a working folder with 12 dummy files (a catalog, a transcript, payroll data, an incident report and others).
2. Practiced `chmod` in both forms:
   - Symbolic: `chmod u+x,g-w,o=r file`
   - Octal: `chmod 640 file`
3. Practiced `chown` and `chgrp` to change a file's owner and group.
4. Matched each classification level to a permission setting and applied it to the files.
5. Used an **ACL** (`setfacl` and `getfacl`) to give one named person access, which normal permissions cannot do.
6. Checked everything with `ls -l` and `getfacl`.

## Key ideas
- Every file has permissions for **owner, group and others**: read, write, execute.
- On a directory, "execute" means you may enter it.
- Permissions should follow the handling rule for the level, not a guess based on the file name.
- A file should be owned by the narrowest party that needs control of it.
- ACLs are for special cases the three-class model can't express, not a default replacement.

## Tools
Linux terminal: `chmod`, `chown`, `chgrp`, `ls -l`, `setfacl`, `getfacl`
