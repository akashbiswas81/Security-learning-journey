# Bandit Level 11 → Level 12

 The password for the next level is in `data.txt`, but all letters are rotated by 13 positions – that's ROT13 encoding. I remember ROT13 is a simple cipher where A becomes N, B becomes O, etc.

## What I Did

Logged in as bandit11. Checked the data.txt file.

```bash
cat data.txt
```

It was some gibberish text, like "Guvf vf frperg grkg..." – classic ROT13.

To decode, I used the tr command to shift the letters back.

```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

That gave me the decoded text, and from there, I extracted the password.

## Step-by-Step

1. **Reading the file**: Just cat'ed it. Saw the encoded text. Knew it was ROT13 because the hint said so.

2. **Decoding ROT13**: Used tr to translate. The command shifts each letter by 13 positions in the alphabet.

   - `cat data.txt` - read the file
   - `| tr 'A-Za-z' 'N-ZA-Mn-za-m'` - pipe to tr, which maps A-Z to N-ZA-M, and a-z to n-za-m

   This effectively rotates back by 13 positions.

   Why this mapping? Because ROT13 is its own inverse – applying it twice gets back to original. So shifting forward 13 is same as backward 13.

3. **Getting the password**: The decoded output had the password in it. I noted it down.

## Password for Level 12

[ANONYMIZED - Actual password not shown for security]

## What I Learned

- ROT13 cipher: simple substitution, shifts by 13.
- The tr command in Linux: great for character translation.
- How to decode basic ciphers.
- Pipes again, chaining commands.

This was pretty straightforward once I recalled ROT13. Didn't take long. On to level 12!