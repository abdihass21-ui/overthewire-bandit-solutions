# Levels 1–5 — The Basics

## Level 1 → 2
Password in a file named `-` (special filename). Read with:
cat ./-
Lesson: `-` means "stdin" so you must give the path explicitly.

## Level 2 → 3
Filename has spaces. Quote it or use escapes:
cat "spaces in this filename"

## Level 3 → 4
Hidden directory:
ls -lah
cat inhere/.hidden
Lesson: Names starting with `.` are hidden — use `-a` to see them.

## Level 4 → 5
Find the only human-readable file among many:
find . -type f | xargs file | grep "ASCII text"

## Level 5 → 6
Find file matching size criteria:
find inhere/ -size 1033c ! -executable

Key skills: Navigation, special filenames, hidden files, find
