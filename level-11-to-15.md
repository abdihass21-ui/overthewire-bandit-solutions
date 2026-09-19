# Levels 11–15 — How I Solved Them

## Level 11 → 12
What I found: Every letter was shifted 13 places in the alphabet
What I did: `cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'`
Why: ROT13 is its own inverse — the same command both encodes AND decodes
Lesson: Simple letter patterns can be reversed with `tr`

## Level 12 → 13
What I found: Started as hex code → turned into binary → wrapped in layers over and over
What I did: 
- `xxd -r data.txt > data` turned hex into a real file
- Then `file data` told me the REAL type EVERY time
- Rename → decompress → check → REPEAT
Why: The FILENAMES LIED! One said `.bz2` but it was actually a tar archive!
Lesson: NEVER trust the name — ALWAYS run `file` first

## Level 13 → 14
What I found: Couldn't use a password — had to use a private key file instead
What I did: 
- `chmod 600 sshkey.private` locked the file down
- `ssh -i sshkey.private bandit14@...` used the key to log in
Why: SSH rejects keys if anyone else can read them — permissions MUST be tight
Lesson: Private keys need `600` permission to work

## Level 14 → 15
What I found: Password wasn't in a file — it was waiting on a network port
What I did: `nc bandit14 30000` connected directly and got it
Why: `nc` (netcat) talks to servers — like a chat window to another machine
Lesson: Sometimes you connect instead of reading a file
