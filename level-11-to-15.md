# Levels 11–15 — Transform & Unpack

## Level 11 → 12
ROT13 decode:
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
Lesson: ROT13 is its own inverse — same command encodes AND decodes.

## Level 12 → 13
Hex dump → binary → decompress layers:
xxd -r data.txt > data
file data
Then repeat: rename → decompress → check → repeat
gzip → bzip2 → tar → bzip2 → tar → gzip → password
BIGGEST LESSON: Filenames lie. file tells the truth.

## Level 13 → 14
SSH key authentication instead of password:
chmod 600 sshkey.private
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
Lesson: Private keys must have restricted permissions or SSH rejects them.

## Level 14 → 15
Connect to a port and get the password:
nc bandit14 30000

Key skills: tr, xxd, file, gzip/bzip2/tar, SSH keys, nc
