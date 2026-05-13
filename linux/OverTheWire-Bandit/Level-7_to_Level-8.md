# Bandit Level 7 → Level 8

## Goal
Find the line in `data.txt` that contains `millionth`.

---

## What I did
Used `cat data.txt | grep "millionth"` to locate the target line.

---

## Why it worked
`grep` searches text for the string `millionth`.
Piping `cat` into `grep` passes the file contents as input.

---

## Notes
- `grep` is the right tool for pattern matching in text files.
- The pipe `|` connects commands so the output from `cat` becomes the input for `grep`.
- For this task, `grep "millionth" data.txt` would also work.

---

## Takeaway
When you need a specific line from a file, use `grep` directly. It’s a simple and effective way to find text patterns.

---

## Password

```text
[REDACTED]
```