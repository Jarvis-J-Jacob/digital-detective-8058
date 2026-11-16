# Mission 3 - Understand the Operating System

## 1. Task / objective
Explore the operating system environment, running processes, storage, absolute and
relative paths, and file permissions using Terminal, and explain the main
responsibilities of an operating system.

## 2. Work completed
- Identified the OS, kernel version and CPU architecture.
- Identified the current user account and observed available/used storage.
- Captured a one-shot snapshot of system activity and the running process list.
- Navigated between the repository root and this mission folder using absolute and
  relative paths, and observed how `pwd` changed.
- Created `practice.txt` and inspected its permission letters.
- Wrote explanations for six OS responsibilities with an example for each.
- Redacted all personal identifiers (username, device name, home path) before
  saving any output into the repository.

## 3. Commands / tools used

| Command / tool | Purpose |
|---|---|
| `sw_vers` | Show macOS product name, version and build |
| `uname -srm` | Show kernel name, release and machine architecture (used instead of `uname -a` to avoid printing the device name) |
| `whoami` | Show the account the Terminal session runs as |
| `df -h` | Show disk space used/available in human-readable units |
| `top -l 1 -n 10 \| head -25` | Take one snapshot of processes and system load |
| `ps aux \| head -20` | List processes with user, PID, CPU, memory and command |
| `ps -eo pid,comm \| head -20` | List process IDs with command names only |
| `pwd` | Print the current working directory |
| `cd <dir>` / `cd ..` | Change directory using absolute or relative paths |
| `echo "..." > practice.txt` | Create a file with one line of content |
| `ls -l` / `ls -la` | Detailed listing, with and without hidden files |

## 4. My understanding

### Task 3.1 - Operating system, account, storage, activity

| Information explored | What it tells you | My observation (privacy-safe) |
|---|---|---|
| Operating system / system details | The OS family, version and CPU architecture, which decide what software runs | macOS 27.2, build 26B123; `uname -srm` reports Darwin 27.2.0 arm64, so this is macOS on a 64-bit ARM (Apple Silicon) CPU |
| Current account identity | Which account my commands run as, and therefore which permissions apply | `[redacted]` - a normal user, not `root`, so system files stay protected |
| Available and used storage | Total, used and free space before creating large files | The main APFS container is 926 GiB with 626 GiB free; `/` is only 3% used because user data lives on `/System/Volumes/Data`, which shows 261 GiB used (30%) |
| System activity snapshot | CPU load, memory use and process counts at one moment | 847 processes (3 running, 844 sleeping), load average 1.47 / 2.05 / 2.54, CPU 91.15% idle, ~19 GB of memory used and ~4.4 GB unused |

### Task 3.2 - Processes

- **What is a process?** A program loaded into memory and currently being run, including
  its memory, CPU time, open files and owning user.
- **What does the PID column represent?** A unique number the OS gives each process so
  it can be tracked, scheduled and signalled. PID 1 is `/sbin/launchd`.
- **Two examples of running processes:**

| PID | Process | What it is |
|---|---|---|
| 1 | `/sbin/launchd` | The first system process, which starts all the others |
| 54127 | `Brave Browser` | The browser, which has several helper renderer/GPU processes |

Not every process belongs to my account - some run as `root` or as system users such
as `_windowserver`, which limits what any single program can affect.

### Task 3.3 - Paths and permissions

| Location | Path shown |
|---|---|
| Repository root (absolute) | `/Users/[redacted]/Downloads/SNAI/digital-detective-8058` |
| Inside Mission 3 folder (absolute) | `/Users/[redacted]/Downloads/SNAI/digital-detective-8058/mission-03-operating-system` |
| After `cd ..` (relative) | back to `/Users/[redacted]/Downloads/SNAI/digital-detective-8058` |
| After `cd mission-03-operating-system` (relative) | back inside the Mission 3 folder |

- **Absolute path** - starts at `/` and means the same thing from anywhere.
  Example: `/Users/[redacted]/Downloads/SNAI/digital-detective-8058/mission-03-operating-system`
- **Relative path** - interpreted from the current directory using `.`, `..` or a name.
  Example: `../mission-02-terminal` from inside `mission-03-operating-system`.

Detailed listing of `practice.txt`:

    -rw-r--r--  1 [redacted]  staff  20 17 Nov 00:43 practice.txt

| Permission | Meaning | Example |
|---|---|---|
| `r` - Read | Allows a file's contents to be read | Opening `practice.txt` |
| `w` - Write | Allows a file to be changed | Adding a line with `>>` |
| `x` - Execute | Allows a file to run; on a directory, allows traversal | Running a `.py` script |

The owner permissions are `rw-`: the owner can read and write but not execute, which
is correct for a text file. The leading `-` means a regular file (`d` would mean a
directory), and `@` means macOS extended attributes. I only observed permissions -
none were changed.

### Task 3.4 - Operating-system responsibilities

| OS responsibility | My explanation | Example |
|---|---|---|
| Process management | Starts processes, shares CPU time between them and stops them when done | 847 processes with only 3 running at once |
| Memory management | Allocates RAM to processes, reclaims it on exit and compresses when full | 19 GB used with 4954 MB compressed |
| Device management | Drivers and services let programs use hardware without talking to it directly | `WindowServer` draws the screen |
| File management | Organises data into files and directories and records metadata and permissions | `ls -l` showed size, owner and permission bits |
| User interface / shell | Gives humans a way to send instructions, either graphically or by typed commands | The zsh prompt where I typed `pwd` |
| Security and permissions | Decides which users and processes may access which resources | `practice.txt` is `rw-r--r--`, so only the owner can modify it |

## 5. Difficulties faced
No major difficulties.

## 6. How I resolved them
Not applicable.

## 7. Evidence / files

| File | What it contains |
|---|---|
| `mission-03-operating-system/README.md` | This report |
| `mission-03-operating-system/notes.md` | Working notes for Tasks 3.1-3.4 (raw, with `[redacted]`) |
| `mission-03-operating-system/practice.txt` | The file created in Task 3.3 for permission practice |
| `evidence/mission-03/system-info.txt` | Captured `sw_vers`, `uname -srm`, `whoami` and `df -h` output (redacted) |
| `evidence/mission-03/processes.txt` | Captured `ps aux` and `ps -eo pid,comm` output (redacted) |
| `evidence/mission-03/paths-permissions.txt` | Captured `pwd`, `ls -l` and `ls -la` trace |

## 8. Commit details

| Field | Value |
|---|---|
| Commit message | `Document operating system and file management` |
| Files in commit | `.gitignore`, `mission-03-operating-system/README.md`, `mission-03-operating-system/notes.md`, `mission-03-operating-system/practice.txt`, `evidence/mission-03/*` |
