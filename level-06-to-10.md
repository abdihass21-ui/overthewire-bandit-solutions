# Levels 6–10 — How I Solved Them

## Level 6 → 7
What I found: File could be anywhere on the whole system
What I did: `find / -name "file_name" 2>/dev/null`
Why: Searches every folder; `2>/dev/null` hides error messages so I can read the result
Lesson: When you don't know where something is, search everywhere

## Level 7 → 8
What I found: One line out of thousands had the password
What I did: `grep "million" data.txt`
Why: `grep` finds only lines containing the word I wanted
Lesson: Search by a unique word you know is there

## Level 8 → 9
What I found: All lines were identical except ONE
What I did: `sort data.txt | uniq -c` → looked for count = 1
Why: `sort` groups matching lines together; `uniq -c` counts them
Lesson: Sort first, then find what only appears once

## Level 9 → 10
What I found: The file looked like garbage — no readable text at all
What I did: `strings data.txt`
Why: `strings` pulls out only the human-readable parts from binary data
Lesson: When it looks like computer noise, extract the text

## Level 10 → 11
What I found: The password was scrambled with Base64 encoding
What I did: `base64 -d data.txt`
Why: `-d` means decode — turns the scrambled text back into normal words
Lesson: Common encoding types have simple decode commands
