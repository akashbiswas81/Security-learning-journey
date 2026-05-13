# Bandit Level 2 → Level 3

## Goal
Open the file with spaces in its name.

---

## What I did
1. Used `ls` to verify the file exists.
2. Used `cat -- "--spaces in this filename--"` to read it.

---

## Why it worked
The filename contains spaces and begins with `--`, which can confuse command parsing.
Using `--` tells `cat` to stop interpreting options and treat the next text as the filename.

---

## Notes
- `--` is a common way to end option parsing in GNU commands.
- Quoting filenames with spaces keeps them as a single argument.
- This is a useful trick for files with unusual names.

---

## Takeaway
When a filename looks like an option or includes spaces, stop option parsing first and quote the name. That keeps the command from misreading the argument.

---

## Password

```text
[REDACTED]
```