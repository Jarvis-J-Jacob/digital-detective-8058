# Mission 8 - Final Review and Submission

## 1. Task / objective
Review all completed missions, confirm the repository meets the assignment's
submission requirements, verify no personal information is published, and prepare
the final repository URL for submission.

## 2. Work completed
- Reviewed every mission folder and its README against the assignment's requirements.
- Verified that each mission was documented, committed and pushed separately.
- Confirmed the privacy of the repository (no usernames, device names, personal IPs,
  Wi-Fi names or tokens are included).
- Confirmed the branch and Pull Request workflow for Mission 6 is visible on GitHub.
- Confirmed the repository URL is ready for submission through the instructor's form.

## 3. Commands / tools used

| Command / tool | Purpose |
|---|---|
| `git status` | Confirm the working tree is clean before submission |
| `git log --oneline` | List every mission's commit to verify separate commits |
| `git log --reverse --oneline` | Find the first (Mission 0 setup) commit |
| `ls -d mission-*` | Confirm every required mission folder exists |
| `ls evidence evidence/mission-*` | Confirm evidence folders exist for each mission that produced files |
| GitHub web UI | Verify the merged Pull Request #1 and file tree on the remote |

## 4. My understanding

### Completion summary

| Mission | Focus | Completed in commit |
|---|---|---|
| 0 | Repository and workspace setup | `42ff39b` |
| 1 | Computer fundamentals and IPOS | `eaea9ce` |
| 2 | Terminal and file management | `9bff99f` |
| 3 | Operating system, processes and permissions | `26fc9e8` (standardised in `376cad6`) |
| 4 | How programs run | `cdca095` |
| 5 | Number systems, Python and text encoding | `2737773` |
| 6 | Git, GitHub, branches and Pull Requests | `2bc4640` (PR #1 merged in `5781764`) |
| 7 | Computer networks | `69dd06a` |
| 8 | Final review and submission | This commit |

Each mission was documented, committed and pushed **separately** before the next
mission began.

### Submission checklist

| Requirement | Status |
|---|---|
| One public GitHub repository | ✅ `https://github.com/Jarvis-J-Jacob/digital-detective-8058` |
| A separate folder for every mission | ✅ `mission-00` through `mission-08` |
| A root `README.md` | ✅ Present |
| A `README.md` inside every mission folder | ✅ All present |
| Notes, tables, safe screenshots/outputs | ✅ In each README and in `evidence/` |
| A working Python number converter | ✅ `mission-05-numbers-data/number_converter.py` |
| A visible commit and push for every mission | ✅ 9 separate mission commits (+ 1 cleanup) |
| Repository URL submitted through the form | ⏳ To be submitted by the student |

### Privacy audit

| Item | Status |
|---|---|
| Username published anywhere | ❌ No - replaced with `[redacted]` |
| Device name published anywhere | ❌ No - `uname -a` avoided, `uname -srm` used instead |
| Personal IP address or Wi-Fi name published | ❌ No - only public IPs (Cloudflare edge, Google DNS) appear in evidence |
| Email, access tokens, passwords | ❌ No |
| Full `ps aux` command lines with session IDs | ❌ No - trimmed to `...` in evidence files |
| `.obsidian/` workspace config | ❌ Ignored via `.gitignore` |

### Repository structure

    digital-detective-8058/
    ├── README.md
    ├── .gitignore
    ├── mission-00-setup/
    ├── mission-01-computer-basics/
    ├── mission-02-terminal/
    ├── mission-03-operating-system/
    ├── mission-04-programs/
    ├── mission-05-numbers-data/
    ├── mission-06-git-github/
    ├── mission-07-networking/
    ├── mission-08-final-report/
    └── evidence/
        ├── mission-03/
        ├── mission-04/
        ├── mission-05/
        └── mission-07/

### Repository URL for submission

    https://github.com/Jarvis-J-Jacob/digital-detective-8058

## 5. Difficulties faced
No major difficulties.

## 6. How I resolved them
Not applicable.

## 7. Evidence / files

| File | What it contains |
|---|---|
| `mission-08-final-report/README.md` | This final review and submission report |
| `git log` on `main` | The complete commit history, one commit per mission |
| GitHub PR #1 | The visible branch-and-PR evidence for Mission 6 |

## 8. Commit details

| Field | Value |
|---|---|
| Commit message | `Complete final review and submission checklist` |
| Files in commit | `mission-08-final-report/README.md` |
