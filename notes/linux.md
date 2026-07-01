# Linux Notes

## Navigation
| Command | Description |
|---------|-------------|
| `ls` | List files |
| `ls -a` | List all files including hidden |
| `ls -l` | List with details (permissions, size, owner) |
| `ls -b` | Show special characters in filenames |
| `cd` | Change directory |
| `pwd` | Print current directory path |
| `find` | Search files by criteria |

## Reading Files
| Command | Description |
|---------|-------------|
| `cat file` | Display file content |
| `cat ./file` | Read file with special name (dash) |
| `cat "file name"` | Read file with spaces in name |
| `cat -- -` | Read file literally named `-` |
| `less file` | Read file page by page |
| `strings file` | Extract readable text from binary |
| `base64 -d file` | Decode base64 encoded file |

## Searching
| Command | Description |
|---------|-------------|
| `grep "word" file` | Search for string inside file |
| `grep -r "word" .` | Search recursively in all files |
| `find / -user X` | Find files owned by user X |
| `find . -size 33c` | Find files of exact size (bytes) |
| `find . -not -executable` | Find non-executable files |

## File Types & Permissions
| Command | Description |
|---------|-------------|
| `file filename` | Detect real file type |
| `chmod` | Change file permissions |
| `chown` | Change file owner |
| `ls -l` | View permissions in octal-style |

## Text Processing
| Command | Description |
|---------|-------------|
| `sort file` | Sort lines alphabetically |
| `uniq -u` | Show only unique lines (no duplicates) |
| `sort file \| uniq -u` | Combine both to find unique lines |

## Key Concepts
- **Hidden files** : filenames starting with `.` — revealed with `ls -a`
- **stderr redirection** : `2>/dev/null` silences permission errors
- **Pipe `\|`** : chains commands — output of one becomes input of next
- **`./` prefix** : forces shell to treat name as path, not a flag
- **`--` separator** : tells command everything after is a filename
- **`2>/dev/null`** : redirects error output to null (discards it)
