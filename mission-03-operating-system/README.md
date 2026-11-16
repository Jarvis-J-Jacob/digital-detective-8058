# Mission 3 — Understand the Operating System

## Task completed
Explored the OS environment, running processes, storage, paths and file permissions using Terminal. All identifying details are replaced with `[redacted]`.

## Commands used

| Command | Purpose |
|---|---|
| `sw_vers` | Show macOS product name, version and build |
| `uname -srm` | Show kernel name, release and architecture |
| `whoami` | Show the account the session runs as |
| `df -h` | Show disk space in human-readable units |
| `top -l 1 -n 10 \| head -25` | Take one snapshot of processes and system load |
| `ps aux \| head -20` | List processes with user, PID, CPU and memory |
| `ps -eo pid,comm \| head -20` | List process IDs with command names only |
| `pwd` | Print the current working directory |
| `cd <dir>` / `cd ..` | Change directory using absolute or relative paths |
| `echo "..." > practice.txt` | Create a file with one line of content |
| `ls -l` / `ls -la` | Detailed listing, with and without hidden files |

---

## Task 3.1 — Explore your operating system

| Information explored | What it tells you | Your observation (privacy-safe) |
|---|---|---|
| Operating system / system details | The OS family, version and CPU architecture, which decide what software runs | macOS 27.2, build 26B123; Darwin 27.2.0 arm64 (Apple Silicon) |
| Current account identity | Which account my commands run as, and therefore which permissions apply | `[redacted]` — a normal user, not `root`, so system files stay protected |
| Available and used storage | Total, used and free space before creating large files | 926 GiB container with 626 GiB free; `/` at 3%, `/System/Volumes/Data` at 261 GiB (30%) |
| System activity snapshot | CPU load, memory use and running/sleeping process counts at one moment | 847 processes (3 running, 844 sleeping); load 1.47/2.05/2.54; 91.15% idle; ~19 GB used |

---

## Task 3.2 — Understand processes

**What is a process?**
A program loaded into memory and currently being run, including its memory, CPU time, open files and owning user.

**What does the PID column represent?**
A unique number the OS gives each process so it can be tracked, scheduled and signalled. PID 1 is `/sbin/launchd`.

**Two examples of processes that were running on my computer:**

| PID | Process | What it is |
|---|---|---|
| 1 | `/sbin/launchd` | The first system process that launches all others |
| 54127 | `Brave Browser` | The browser, with several helper renderer/GPU processes |

Some processes run as `root` or as system users like `_windowserver`, which limits how much any one program can affect.

---

## Task 3.3 — Understand paths and permissions

| Location | Path shown |
|---|---|
| Repository root (absolute) | `/Users/[redacted]/Downloads/SNAI/digital-detective-8058` |
| Inside Mission 3 folder (absolute) | `/Users/[redacted]/Downloads/SNAI/digital-detective-8058/mission-03-operating-system` |
| After `cd ..` (relative) | back to `/Users/[redacted]/Downloads/SNAI/digital-detective-8058` |
| After `cd mission-03-operating-system` (relative) | back inside the Mission 3 folder |

**Absolute path** — starts at `/` and means the same thing from anywhere.
Example: `/Users/[redacted]/Downloads/SNAI/digital-detective-8058/mission-03-operating-system`

**Relative path** — interpreted from the current directory using `.`, `..` or a name.
Example: `../mission-02-terminal` from inside `mission-03-operating-system`

### Permission letters for my practice file

    -rw-r--r--  1 [redacted]  staff  20 17 Nov 00:43 practice.txt

| Permission | Meaning | Example |
|---|---|---|
| `r` — Read | Allows a file's contents to be read | Opening `practice.txt` |
| `w` — Write | Allows a file to be changed | Adding a line with `>>` |
| `x` — Execute | Allows a file to run; on a directory, allows traversal | Running a `.py` script |

Owner permissions are `rw-`: the owner can read and write but not execute, which is correct for a text file.
The leading `-` means a regular file, `d` would mean a directory, and `@` means macOS extended attributes.

---

## Task 3.4 — Explain operating-system responsibilities

| OS responsibility | Your explanation | Example |
|---|---|---|
| Process management | Starts processes, shares CPU time between them and stops them when done. | 847 processes with only 3 running at once |
| Memory management | Allocates RAM to processes, reclaims it on exit and compresses or swaps when full. | 19 GB used with 4954 MB compressed |
| Device management | Drivers and services let programs use hardware without talking to it directly. | `WindowServer` draws the screen |
| File management | Organises data into files and directories and records metadata and permissions. | `ls -l` showed size, owner and permission bits |
| User interface / shell | Gives humans a way to send instructions, either graphically or by typed commands. | The zsh prompt where I typed `pwd` |
| Security and permissions | Decides which users and processes may access which resources. | `practice.txt` is `rw-r--r--`, so only the owner can modify it |

---

## What I understood

- The OS sits between hardware and programs: it schedules CPU time, manages memory, drives devices, organises files and enforces permissions.
- `top -l 1` takes one snapshot then exits; load averages at or below core count mean the machine is not overloaded.
- macOS keeps system files on a read-only volume, so `/` and `/System/Volumes/Data` show different usage within the same container.
- Absolute paths work from anywhere; relative paths only work from the right current directory.
- In `-rw-r--r--`, the first character is the file type and the next nine are owner, group and others triplets.

## Difficulty faced
No major difficulties.