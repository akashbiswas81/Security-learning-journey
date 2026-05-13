# Bandit Level 6 → Level 7

## Goal
Find the file owned by `bandit7:bandit6` that is exactly 33 bytes.

---

## What I did
1. Ran `find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null`.
2. Used `cat` on the found path to read the file.

---

## Why it worked
The command searched the whole filesystem for regular files with the right owner, group, and byte size.
Redirecting errors to `/dev/null` hid permission denied messages from directories I couldn’t access.

---

## Notes
- Searching from `/` is useful when the file location is unknown.
- `-user` and `-group` filter by ownership.
- `-size 33c` matches exact byte size.
- `2>/dev/null` keeps the output clean.

---

## Takeaway
When a challenge gives ownership and size constraints, combine `find` filters and suppress noisy permission errors to focus on valid files.

---

## Password

```text
[REDACTED]
```