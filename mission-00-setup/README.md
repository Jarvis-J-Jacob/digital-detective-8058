# Mission 0 - Repository and Workspace Setup

## 1. Task / objective
Create a correctly named public GitHub repository with the required folder structure
for every mission, and prepare a root README that indexes the project.

## 2. Work completed
- Chose the repository name `digital-detective-8058` (assignment name + last four USN digits).
- Created the matching local project folder and opened it in Terminal and a text editor.
- Created the nine mission folders, each with an empty `README.md`.
- Created the `evidence/` folder for privacy-safe outputs.
- Wrote the root `README.md` with the project title, description, mission index and an
  explanation that each mission is committed separately.
- Published the repository to GitHub and verified the folders appeared online.

## 3. Commands / tools used

| Command / tool | Purpose |
|---|---|
| `python3 --version` | Confirm Python 3 is installed and record its version |
| `git --version` | Confirm Git is installed and record its version |
| `git init` / `git remote add origin ...` | Initialise the local repo and link it to GitHub |
| `git add` + `git commit` + `git push` | Publish the initial folder structure |

**Versions checked:** Python 3.14.7 · Git 2.55.0 · macOS 27.2 (Darwin 27.2.0, arm64).

## 4. My understanding

**What a repository is:** a folder whose history Git tracks. Every committed change is
recorded, so earlier versions can be reviewed and restored. GitHub stores a copy of that
repository online so it can be shared and submitted.

**Why the folder structure is organised by mission:** each mission is a separate unit of
work with its own objective, README and commit. Keeping one folder per mission means a
reader (or grader) can open a single folder and see exactly what that mission produced,
without sorting through unrelated files.

**Repository name:** `digital-detective-8058` — lowercase, hyphenated, no spaces, matching
the local folder name exactly.

## 5. Difficulties faced
No major difficulties.

## 6. How I resolved them
Not applicable.

## 7. Evidence / files

| File | What it contains |
|---|---|
| `README.md` (root) | Project title, description and mission index |
| `mission-00-setup/README.md` | This report |
| `mission-*/README.md` | One empty README per mission, filled in as each mission is completed |
| `evidence/` | Privacy-safe outputs, grouped by mission |

## 8. Commit details

| Field | Value |
|---|---|
| Commit message | `Set up Digital Detective mission structure` |
| Files in commit | Root `README.md`, `.gitignore`, all mission folders, `evidence/` |
