# Bandit Level 3 → Level 4

## Goal
Find the hidden file in `inhere` and read it.

---

## What I did
1. Ran `ls` to see the current directory.
2. Changed into `inhere` with `cd inhere`.
3. Used `ls -a` to reveal hidden entries.
4. Read the file with `cat ...Hiding-From-You`.

---

## Why it worked
The hidden file begins with `.` and won't show up with a normal `ls`.
Using `ls -a` shows hidden files, then `cat` displays the content.

---

## Notes
- Hidden files are still regular files; they just start with a dot.
- `cd` moves into the target directory before searching.
- `ls -a` is the key step for finding files that are intentionally hidden.

---

## Takeaway
Hidden files are easy to miss with basic `ls`. Always use `ls -a` when the challenge mentions hidden content.

---

## Password

```text
[REDACTED]
```