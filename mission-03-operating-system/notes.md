# Mission 3 Notes

## Task 3.1 - Exploring my operating system

| Information | Command | What it tells you | My observation |
|---|---|---|---|
| Operating system details | sw_vers and uname -sm | The OS name, version and type of processor | macOS 27.2, Darwin kernel, arm64 processor |
| Current account | whoami | Which user account is logged in | [redacted] |
| Storage | df -h / | Total, used and free space on the main disk | 926 GB total, 627 GB free, about 3 percent used |
| System activity | top -l 1 | A snapshot of running processes, CPU and memory use | About 920 processes, mostly sleeping, CPU around 87 percent idle |

## Task 3.2 - Processes

I opened my browser and listed processes with ps -ax.

- What is a process: a program that is running right now. Each open app is one or more processes, and many others run in the background.
- What PID means: the process ID, a unique number the OS gives each running process so it can track and control it.
- Two examples from my computer:
  - launchd, PID 1, the first process macOS starts, which starts the others
  - Brave Browser, the web browser I had open

## Task 3.3 - Paths and permissions

When I moved with cd from digital-detective-8058 into mission-02-terminal, pwd showed the extra folder at the end of the path.

- Absolute path: starts from the top of the disk and works from anywhere. Example: /Users/[redacted]/Downloads/SNAI/digital-detective-8058/mission-02-terminal
- Relative path: starts from the folder I am in now. Example: mission-02-terminal/terminal-practice from the project folder

Permissions of notes.txt from ls -l: -rw-r--r--

- The first dash means it is a file, not a folder.
- The owner has rw-, so the owner can read and write it but cannot execute it.
- The group and others have r--, so they can only read it.

| Permission | Meaning | Example |
|---|---|---|
| r - Read | Allows a file's contents to be read | Opening a text file |
| w - Write | Allows a file to be changed | Editing a text file |
| x - Execute | Allows a file to be run, or a folder to be entered | Running a script |

## Task 3.4 - Operating system responsibilities

| Responsibility | My explanation | Example |
|---|---|---|
| Process management | Starts and stops programs and shares CPU time between them | Running a browser and VS Code at the same time |
| Memory management | Gives each program its own part of RAM and frees it when the program closes | Closing an app frees its memory |
| Device management | Talks to hardware through drivers | Using the keyboard, trackpad and speakers |
| File management | Organises files in folders and keeps track of where they are stored | Creating and moving files in Finder or Terminal |
| User interface / shell | Gives me a way to use the computer, either with windows or typed commands | The desktop and the Terminal |
| Security and permissions | Controls who can log in and who can read or change files | File permissions and the login password |
