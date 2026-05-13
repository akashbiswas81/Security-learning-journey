# Bandit Level 5 → Level 6

## Goal
Find the human-readable file that is exactly 1033 bytes and not executable.

---

## What I did
Used `find . -type f -size 1033c ! -executable` to locate the target file.

---

## Why it worked
The command searched the current directory tree for regular files of exactly 1033 bytes.
The `! -executable` filter excluded any executable files, narrowing the result to the correct file.

---

## Notes
- `find` is great for combining filename and metadata filters.
- `-size 1033c` matches file size in bytes.
- `! -executable` ensures the file is not marked executable.

---

## Takeaway
When a challenge describes a file by size and permissions, `find` is the tool to use. It helps target files precisely without manual inspection.

---

## Password

```text
[REDACTED]
```