# OverTheWire — Bandit Write-ups

> Bandit is a wargame designed for beginners to learn Linux
> command-line basics through progressive security challenges.
> Link : https://overthewire.org/wargames/bandit/

---

## Level 0 → 1
**Concept :** Connecting via SSH + reading a file  
**Commands :** `ssh`, `cat`, `ls`  
**What I learned :** Basic SSH connection syntax,
listing files and reading content in a terminal.

---

## Level 1 → 2
**Concept :** Files with special names (dash `-`)  
**Commands :** `cat ./-`  
**What I learned :** A filename starting with `-` is interpreted
as a flag by most commands. Prefixing with `./` forces it
to be read as a path.

---

## Level 2 → 3
**Concept :** Filenames with spaces  
**Commands :** `cat "spaces in this filename"`, Tab completion  
**What I learned :** Wrap filenames with spaces in quotes,
or use Tab to auto-complete and let the shell handle escaping.

---

## Level 3 → 4
**Concept :** Hidden files  
**Commands :** `ls -a`, `cat`  
**What I learned :** Files starting with `.` are hidden from
standard `ls`. Use `ls -a` to reveal them.

---

## Level 4 → 5
**Concept :** Identifying file types  
**Commands :** `file ./*`  
**What I learned :** `file` inspects actual file content
(not just extension) and returns its type.
Used a wildcard `*` to check all files at once.

---

## Level 5 → 6
**Concept :** Searching files by properties  
**Commands :** `find . -type f -size 1033c -not -executable`  
**What I learned :** `find` can filter by size, type,
and permissions recursively across directories.

---

## Level 6 → 7
**Concept :** Searching across the entire filesystem  
**Commands :** `find / -user bandit7 -group bandit6 -size 33c 2>/dev/null`  
**What I learned :** Searching from `/` covers the whole system.
`2>/dev/null` suppresses permission errors — redirecting
stderr (2) to the null device keeps output clean.

---

## Level 7 → 8
**Concept :** Searching inside a file  
**Commands :** `grep millionth data.txt`  
**What I learned :** `grep` searches for a string inside
a file and returns only matching lines — far more efficient
than reading thousands of lines manually.

---

## Level 8 → 9
**Concept :** Finding unique lines  
**Commands :** `sort data.txt | uniq -u`  
**What I learned :** Piping (`|`) chains commands together.
`sort` prepares data for `uniq`, which then filters
out all duplicate lines.

---

## Level 9 → 10
**Concept :** Extracting text from binary files  
**Commands :** `strings data.txt | grep =`  
**What I learned :** `strings` extracts human-readable text
from binary files. Combined with `grep`, it narrows
results to relevant lines instantly.

---

## Level 10 → 11
**Concept :** Base64 decoding  
**Commands :** `base64 -d data.txt`  
**What I learned :** Base64 is an encoding scheme
(not encryption) that converts data to ASCII-safe text.
The `-d` flag reverses the process.
