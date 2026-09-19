# Levels 6–10 — Search & Decode

## Level 6 → 7
Find anywhere on the system:
find / -name "file_name" 2>/dev/null

## Level 7 → 8
Find line containing the word:
grep "million" data.txt

## Level 8 → 9
Find unique line:
sort data.txt | uniq -c
Look for the line showing count = 1

## Level 9 → 10
Extract readable text from binary:
strings data.txt

## Level 10 → 11
Base64 decode:
base64 -d data.txt

Key skills: find, grep, sort | uniq, strings, base64
