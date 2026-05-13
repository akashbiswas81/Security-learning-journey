# Bandit Level 8 → Level 9

## Goal
Find the single unique line in `data.txt`.

---

## What I did
Used `cat data.txt | sort | uniq -u` to find the line that appears only once.

---

## Why it worked
`sort` groups duplicate lines together.
`uniq -u` then prints only the lines that are not repeated.

---

## Notes
- `sort` is necessary before `uniq` because `uniq` only checks adjacent lines.
- `uniq -u` filters out duplicate entries and leaves unique ones.
- This is a good pattern for identifying anomalies in text data.

---

## Takeaway
For finding the unique item in a list, sort first then use `uniq -u`. It’s a reliable way to isolate one-off entries.

---

## Password

```text
[REDACTED]
```