# 📝 Linux Command Cheat Sheet

## 🧭 Navigation
| Command | What It Does |
|---|---|
| `cd /path` | Move to a folder |
| `ls -lah` | List all files with details |
| `pwd` | Show where you are |
| `find / -name "file" 2>/dev/null` | Find a file anywhere |

## 📂 File Operations
| Command | What It Does |
|---|---|
| `touch file.txt` | Create empty file |
| `mkdir -p path` | Create folders |
| `cp source dest` | Copy |
| `mv old new` | Move / Rename |
| `rm file` | Delete |

## 👁️ Viewing Files
| Command | What It Does |
|---|---|
| `cat file` | Show all content |
| `head -n 20 file` | Show first 20 lines |
| `tail -n 5 file` | Show last 5 lines |
| `less file` | Read page by page |

## 🔍 Search & Filter
| Command | What It Does |
|---|---|
| `grep "word" file` | Find lines containing "word" |
| `sort file` | Sort lines alphabetically |
| `uniq` | Remove duplicates |
| `sort file | uniq -c` | Count occurrences |
| `strings file` | Extract readable text from binary |

## 🔄 Encoding & Transforming
| Command | What It Does |
|---|---|
| `base64 -d file` | Decode Base64 |
| `tr 'A-Za-z' 'N-ZA-Mn-za-m'` | ROT13 decode |
| `xxd -r file.hex > file` | Hex dump → binary |

## 📦 Decompression
| Command | What It Does |
|---|---|
| `gzip -d file.gz` | Decompress gzip |
| `bzip2 -d file.bz2` | Decompress bzip2 |
| `tar -xf file.tar` | Extract tar archive |
| `file filename` | ✅ Check REAL type — ALWAYS use this first! |

## 🔑 SSH
| Command | What It Does |
|---|---|
| `ssh user@host -p PORT` | Connect to remote server |
| `chmod 644 file` | Set file permissions |
| `chmod 700 folder` | Secure a private folder |
