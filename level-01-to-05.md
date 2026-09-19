# Levels 1–5 — How I Solved Them

## Level 1 → 2
What I found: The password was in a file named just `-`
What I did: Used `cat ./-` instead of just `cat -`
Why: `-` normally means "input from keyboard", so I had to tell it "this is a file in this folder"
Lesson: When a filename looks like a command option, put `./` before it

## Level 2 → 3
What I found: The filename had spaces in it
What I did: Put quotes around the name → `cat "spaces in this filename"`
Why: Without quotes, Linux thinks each word is a separate file
Lesson: Always quote filenames that have spaces

## Level 3 → 4
What I found: The file was hidden — it started with a dot
What I did: Used `ls -lah` to see ALL files, then `cat inhere/.hidden`
Why: Files starting with `.` don't show up in normal `ls`
Lesson: Use `-a` flag to see hidden files

## Level 4 → 5
What I found: Lots of files — only one had readable text
What I did: Checked every file type → `find . -type f | xargs file | grep "ASCII text"`
Why: `file` tells you what something actually is, not what it's named
Lesson: When you don't know which one, check them all

## Level 5 → 6
What I found: Need a file that's exactly 1033 bytes and NOT executable
What I did: `find inhere/ -size 1033c ! -executable`
Why: `find` can search by size and permissions together
Lesson: Combine search rules to narrow it down
