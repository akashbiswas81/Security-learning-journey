# Bandit Level 1 → Level 2

## Goal
Read the file named `-`.

---

## What I did
1. Checked the directory with `ls`
2. Read the file using `cat ./-`

---

## Why it works
The file name is `-`, which many commands treat as an option if used directly.
By adding `./`, I forced the shell to interpret it as a path instead of a flag.

---

## Notes
- A filename starting with `-` is valid, but it can break commands if not handled correctly.
- `cat -- -` is another safe way to read such files.
- Using `./` is a quick trick for filenames that look like options.

---

## Takeaway
This challenge is a good reminder that special filenames can change standard command behavior. Always verify how the shell parses the input before running a command.

---

## Password

```text
[REDACTED]
```