# Bandit Level 4 → Level 5

## Goal
Find the one human-readable file in `inhere` and read it.

---

## What I did
1. Changed into `inhere` with `cd inhere`.
2. Listed the files with `ls`.
3. Checked file types using `file ./*`.
4. Read the readable file with `cat ./-file07`.

---

## Why it worked
Most files in the directory were not plain text.
The `file` command showed which file was human-readable, so I could safely use `cat` on that file.

---

## Notes
- `file` is useful for identifying file formats before opening them.
- Use `cat` only on the file confirmed as text.
- The target file name started with `-`, so I used `./-file07` to avoid option parsing issues.

---

## Takeaway
Always verify file types before reading files in a challenge. That keeps the process efficient and avoids accidentally opening binary data.

---

## Password

```text
[REDACTED]
```