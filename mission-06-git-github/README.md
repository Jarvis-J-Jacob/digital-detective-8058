# Mission 6 - Git and GitHub

## 1. Task / objective
Understand Git version control, practise the basic workflow (status, stage, commit, log),
create a branch, open a Pull Request, and build a personal glossary of Git commands.

## 2. Work completed
- Inspected repository status and commit history.
- Created the `update-about` branch and added a "My Learning" section to the root README.
- Committed and pushed the branch to GitHub.
- Opened Pull Request #1 (`update-about` into `main`) with a description of the change.
- Merged the PR on GitHub and pulled the merged `main` back to the local machine.
- Wrote a one-line explanation for each required Git operation.

## 3. Commands / tools used

| Command / tool | Purpose |
|---|---|
| `git status` | Check the state of the working directory and staging area |
| `git add <file>` | Stage a file for the next commit |
| `git commit -m "message"` | Save staged changes as a commit with a message |
| `git log --oneline` | Show commit history in compact form |
| `git checkout -b <branch>` | Create and switch to a new branch |
| `git push -u origin <branch>` | Publish the branch to GitHub |
| `git checkout main` + `git pull origin main` | Switch to main and download remote changes |
| GitHub web UI | Open and merge the Pull Request |

## 4. My understanding

### Task 6.1 - Basic Git workflow

| Git operation | What it does in my own words |
|---|---|
| Check repository status | Shows which files are modified, staged or untracked |
| Stage selected changes | Moves chosen changes into the staging area ready for commit |
| Create a commit | Records the staged changes as a permanent snapshot with a message |
| View commit history | Lists past commits in order, each with its SHA and message |

**Difference between staging and committing:** staging only *prepares* changes, while
committing *records* them permanently in the repository's history.

### Task 6.2 - Branch

A branch is a separate line of development. I created `update-about`, added a new
section to `README.md`, committed it, and pushed it to GitHub without touching `main`.

### Task 6.3 - Pull Request

A Pull Request is a formal request to merge one branch into another. I opened PR #1
from `update-about` into `main`, reviewed the changed file, and merged it on GitHub.
After merging, I switched back to `main` locally and pulled the merged changes.

**Why branches and PRs are useful:** they let people work on the same project without
interfering with each other. A PR adds a review step before changes reach the main
branch, which reduces the risk of introducing broken code.

### Task 6.4 - Git command glossary

| Operation | One-line explanation |
|---|---|
| Initialise a repository | `git init` creates a new Git repository in the current directory |
| Check status | `git status` shows the state of the working tree and staging area |
| Stage changes | `git add <file>` marks a file's changes for the next commit |
| Commit changes | `git commit -m "msg"` saves the staged changes as a permanent snapshot |
| View history | `git log` lists past commits with SHA, author and message |
| Create or list branches | `git branch <name>` creates a branch; `git branch` alone lists branches |
| Switch branches | `git checkout <branch>` (or `git switch <branch>`) changes the working branch |
| Publish changes | `git push origin <branch>` uploads local commits to the remote |
| Retrieve remote changes | `git pull origin <branch>` downloads and integrates remote commits |

## 5. Difficulties faced
No major difficulties.

## 6. How I resolved them
Not applicable.

## 7. Evidence / files

| File | What it contains |
|---|---|
| `mission-06-git-github/README.md` | This report |
| `README.md` (root) | The "My Learning" section added on the `update-about` branch |
| GitHub PR #1 | The merged Pull Request from `update-about` into `main` |

## 8. Commit details

| Field | Value |
|---|---|
| Commit message | `Complete Git and GitHub collaboration mission` |
| Files in commit | `mission-06-git-github/README.md` |
