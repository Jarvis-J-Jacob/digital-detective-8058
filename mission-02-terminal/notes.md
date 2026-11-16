# Mission 2 Notes

## Task 2.1 - Basic Terminal operations

| Operation | Command | What it does | What I observed |
|---|---|---|---|
| Current-directory display | pwd | Prints the full path of the folder I am in | /Users/[redacted]/Downloads/SNAI/digital-detective-8058 |
| Directory listing | ls | Lists files and folders here | The mission folders, evidence and README.md |
| Detailed listing | ls -l | Lists files with permissions, owner, size and date | Each line starts with permissions like drwxr-xr-x |
| Change directory | cd terminal-practice | Moves into another folder | The prompt changed to show terminal-practice |
| Create directory | mkdir terminal-practice | Makes a new folder | A new terminal-practice folder appeared |
| Create file | echo "First line" > notes.txt | Creates a file and writes a line into it | notes.txt was created (touch would create an empty one) |
| Copy file | cp notes.txt backup.txt | Makes a copy with a new name | Both notes.txt and backup.txt existed |
| Move / rename file | mv backup.txt notes-backup.txt | Renames or moves a file | backup.txt became notes-backup.txt |
| Display file contents | cat notes.txt | Prints what is inside a file | First line and Second line |

## Task 2.2 - Practising file changes safely

Inside terminal-practice I wrote a line with >, added a second line with >>, displayed the file with cat, then copied it and renamed the copy.

Output of cat notes.txt:

    First line
    Second line

Final contents of the folder: notes.txt and notes-backup.txt

- Replacing vs adding: > replaces everything in the file with the new text. >> adds the new text to the end and keeps what was already there.
- Copying vs moving: copying leaves the original and makes a second file. Moving takes the file away from its old name or place, so only one file remains.
- What pwd shows: the full path from the top of the disk to the folder I am in, so I know exactly where I am.
- Why ls is useful: it shows what is in a folder before I create, copy or delete anything, so I don't make mistakes.

## Task 2.3 - Flags and pipes

- ls showed only names.
- ls -l added permissions, owner, size and date.
- ls -lah also showed hidden files that start with a dot, such as .git and .DS_Store, and sizes in readable units like 1.5K instead of bytes.

Flags like -l, -a and -h change how a command behaves without changing the command itself.

Pipe: ls -l | head -3 showed only the first 3 lines of the listing. The left side (ls -l) produces the output and the pipe sends it to the right side (head -3), which keeps only the first few lines.

## Task 2.4 - Package managers

Homebrew is installed. brew --version showed Homebrew 7.0.12 and brew list shows the packages it manages. I did not install or remove anything.

A package manager installs, updates and removes software with one command, so I don't have to download installers from websites by hand. It also keeps track of what is installed and what each program needs to run.
