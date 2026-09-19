# Levels 16–20 — Network & Scripts

## Level 16 → 17
Scan ports, get hash, decode → SSH key:
nmap -p 31000-32000 bandit16.labs.overthewire.org
Connect to open SSL port → get SHA256 hash
Decrypt → get private key → SSH in

## Level 17 → 18
Compare two files:
diff passwords.old passwords.new
Then SSH in and find password in hidden file.

## Level 18 → 19
Command replaces shell — run directly:
ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme

## Level 19 → 20
Program runs as different user — execute it:
./bandit20-do cat /etc/bandit_pass/bandit20

## Level 20 → 21
Create your own listener in one terminal, connect from another:
Terminal 1: nc -l 12345
Terminal 2: ./suconnect 12345
Lesson: Network programming basics — how client/server communicate.

Key skills: Networking, diff, SSH tricks, permissions, processes
