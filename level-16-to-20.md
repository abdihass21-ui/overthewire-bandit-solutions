# Levels 16–20 — How I Solved Them

## Level 16 → 17
What I found: Had to find which ports were open, then connect securely
What I did:
- `nmap -p 31000-32000 bandit16` scanned for open doors
- Connected to the SSL port → got a hash → decrypted it → got a new private key
- Set permissions → SSH'd in with the new key
Why: Some services run on different ports — you have to find them first
Lesson: Combine scanning + decryption + SSH for layered challenges

## Level 17 → 18
What I found: Two files looked almost identical — one had the new password
What I did: `diff passwords.old passwords.new` showed the ONE line that changed
Why: `diff` puts two files side-by-side and shows only what's different
Lesson: When things look the same, compare them directly

## Level 18 → 19
What I found: SSH kicked me out instantly — no shell to type in
What I did: Ran the command DIRECTLY: `ssh bandit18@... cat readme`
Why: You can tell SSH "run THIS thing and exit" instead of opening a chat
Lesson: When the door slams shut, send your instruction through the keyhole

## Level 19 → 20
What I found: A program ran with higher permissions than I had
What I did: `./bandit20-do cat /etc/bandit_pass/bandit20` used the program to read the file
Why: The program was "trusted" — it could do things I wasn't allowed to do alone
Lesson: Find what's already trusted to get what you need

## Level 20 → 21
What I found: Needed two terminals — one waiting, one connecting
What I did:
- Terminal 1: `nc -l 12345` waited for a connection
- Terminal 2: `./suconnect 12345` connected and sent the password
- Got the next password back over the connection
Why: One side listens, the other talks — like making a phone call to yourself
Lesson: Sometimes you have to be BOTH the server AND the client
