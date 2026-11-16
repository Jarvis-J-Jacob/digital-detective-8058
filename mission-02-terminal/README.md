# Mission 2 - Become Comfortable with the Terminal

## 1. Task / objective
Use the command-line interface to inspect folders, create and manage practice files,
understand flags and pipes, and explain what package managers do.

## 2. Work completed
- Practised nine basic Terminal operations and recorded what each one did.
- Created a `terminal-practice` folder and practised appending text, copying and renaming files.
- Compared a normal listing with a detailed listing that includes hidden files and
  human-readable sizes.
- Piped a detailed listing into a command that shows only the first few lines.
- Explained why package managers are useful.

## 3. Commands / tools used

| Command / tool | Purpose |
|---|---|
| `pwd` | Print the full path of the current folder |
| `ls` | List files and folders in the current location |
| `ls -l` / `ls -la` | Detailed listing, and detailed listing including hidden files |
| `cd <dir>` / `cd ..` | Move into a folder or to the parent folder |
| `mkdir <name>` | Create a new folder |
| `touch <file>` | Create an empty file |
| `echo "text" > file` / `>> file` | Write text to a file, replacing or appending |
| `cp <src> <dest>` | Copy a file |
| `mv <src> <dest>` | Move or rename a file |
| `cat <file>` | Display a file's contents |
| `ls -lah \| head` | Pipe a detailed listing into `head` to show only the first few lines |
| `brew --version` | Check whether the Homebrew package manager is installed |

## 4. My understanding

### Task 2.1 - Basic Terminal operations

| Operation / command name | What it does | What I observed |
|---|---|---|
| Current-directory display | `pwd` prints the absolute path of where I am | Printed the full path from `/` down to the repo folder |
| Directory listing | `ls` lists names in the current folder | Showed the mission folders and root README |
| Detailed listing | `ls -l` adds permissions, owner, size and date | Each line started with letters like `drwxr-xr-x` or `-rw-r--r--` |
| Change directory | `cd ..` moves to the parent folder | `pwd` afterwards showed the folder one level up |
| Create directory | `mkdir terminal-practice` | The new folder appeared in `ls` |
| Create empty file | `touch practice.txt` | The file appeared with size 0 |
| Copy file | `cp practice.txt practice-backup.txt` | Two separate files existed afterwards |
| Move / rename file | `mv practice-backup.txt renamed-backup.txt` | The original name disappeared, the new name appeared |
| Display file contents | `cat practice.txt` | Printed the text I had written into the file |

### Task 2.2 - File changes and the four questions

- **Replacing a file's contents vs adding to the end:** `>` overwrites the file from the
  beginning, so anything already there is lost. `>>` appends to the end and keeps what
  was there before. I used `>` for the first line and `>>` for the second, then `cat`
  showed both lines present.
- **Copying vs moving a file:** `cp` creates a second file with the same contents and
  leaves the original in place. `mv` relocates or renames the file so only one copy
  exists, at the new name or location.
- **What the current-directory display provides:** the absolute path of the folder my
  commands will act on, which matters because relative paths are interpreted from there.
- **Why a directory listing is useful:** it shows what exists in a location before I act
  on it, so I avoid creating duplicate files or deleting the wrong thing.

### Task 2.3 - Flags and pipes

- **Normal listing (`ls`):** just the names, in columns.
- **Detailed listing (`ls -la`):** adds permission letters, owner, group, size and date,
  and `-a` also includes hidden files beginning with a dot.
- **Human-readable sizes (`-h`):** expresses sizes as `K`, `M` or `G` instead of raw byte
  counts, which makes large files far easier to read.

A **pipe** (`|`) sends the standard output of the command on its left into the standard
input of the command on its right. In `ls -lah | head`, the left side produces a long
listing and `head` prints only the first ten lines of it — useful when a folder has more
files than fit on screen. The left side contributes data; the right side filters it.

### Task 2.4 - Package managers

A package manager installs, updates and removes software from a single trusted source,
resolving dependencies automatically so the user does not have to download and configure
each library by hand. It also keeps a record of installed versions, which makes updates
and removals predictable. On macOS, Homebrew is the common example; this mission only
checks whether it is present, and nothing was installed or removed.

## 5. Difficulties faced
I created the `terminal-practice` folder in the main project folder instead of the
Mission 2 folder.

## 6. How I resolved them
I moved the `terminal-practice` folder into `mission-02-terminal` so the work stays
with its mission.

## 7. Evidence / files

| File | What it contains |
|---|---|
| `mission-02-terminal/README.md` | This report with the command table and answers |
| `mission-02-terminal/terminal-practice/` | The practice folder where files were created, copied and renamed |

## 8. Commit details

| Field | Value |
|---|---|
| Commit message | `Complete Terminal and file management mission` |
| Files in commit | `mission-02-terminal/` |
