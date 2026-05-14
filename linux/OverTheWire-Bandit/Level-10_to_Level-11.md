# Bandit Level 10 → Level 11 

 The goal is to get the password for the next level, which is stored in `data.txt` as Base64 encoded data.

## What I Did

First, I logged in as bandit10. Then, I checked out the data.txt file.

```bash
cat data.txt
```

It showed some encoded stuff. I remembered Base64 often ends with = or ==, so I filtered for that.

```bash
cat data.txt | grep "=="
```

That gave me the encoded string. Then, I decoded it.

```bash
base64 -d <<< encoded string
```

Wait, that's not right. Let me copy the actual encoded data from the file.

Actually, in the challenge, the encoded data was something like that. Anyway, decoding it gave me the password.

## Step-by-Step

1. **Reading the file**: I just cat'ed it to see what's inside. It was a bunch of text, some encoded.

2. **Finding the Base64 part**: I knew Base64 strings usually end with padding. So, grep for "==" to find lines that look like Base64.

   - `cat data.txt` - read the file
   - `| grep "=="` - pipe to grep, search for double equals

   Why double equals? Base64 padding can be one or two equals signs. I chose "==" to be sure.

3. **Decoding**: Used base64 -d to decode. The <<< is a here-string in bash, passes the string directly.

   Got the password: decoded string

## Password for Level 11

[ANONYMIZED - Actual password not shown for security]



## What I Learned

- Base64 encoding/decoding. Handy for CTFs.
- Using grep to search for patterns in files.
- Pipes in bash - chaining commands.
- The base64 command in Linux.

I think I got stuck for a bit because I forgot the <<< syntax, but once I remembered, it was easy. Next level!