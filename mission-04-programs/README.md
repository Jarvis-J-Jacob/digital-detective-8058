# Mission 4 - How Programs Run

## 1. Task / objective
Create a small Python program, run it with Python 3 from Terminal, and compare how
compilers and interpreters translate or execute programs.

## 2. Work completed
- Created `hello.py` inside `mission-04-programs/` that prints `Hello from Python`.
- Checked the installed Python version.
- Ran the file with the Python 3 interpreter and confirmed the message appeared.
- Saved the program's run output as evidence.
- Compared compilers and interpreters across four points and wrote a short explanation.

## 3. Commands / tools used

| Command / tool | Purpose |
|---|---|
| `python3 --version` | Check which Python 3 version is installed |
| `python3 mission-04-programs/hello.py` | Run the Python file with the Python 3 interpreter |
| Text editor (VS Code) | Write and save `hello.py` and this README |

## 4. My understanding

### Task 4.1 - Running Python
`hello.py` contains one line: `print("Hello from Python")`. Running it with `python3`
executes that line and writes `Hello from Python` to the terminal. The installed
version is Python 3.14.7.

### Task 4.2 - Compiler vs interpreter

| Point | Compiler | Interpreter |
|---|---|---|
| When translation / execution happens | Translates the whole source file before the program runs | Reads and executes the source at runtime |
| Typical output | A separate binary or object file | No new file; the program's own results |
| One example | `gcc hello.c -o hello` produces an executable | `python3 hello.py` runs the file directly |
| One advantage | Fast execution because the CPU runs machine code | Easy to test and change, no separate build step |

**Difference in my own words:**
A compiler translates the whole source file into machine code or another lower-level
form before the program runs, producing a separate output file. An interpreter instead
reads the source at runtime and executes each line as it goes, without producing a
separate executable. Compiled programs usually run faster; interpreted programs are
quicker to write and test. Python is a hybrid: it compiles to bytecode first and then
interprets that bytecode.

## 5. Difficulties faced
No major difficulties.

## 6. How I resolved them
Not applicable.

## 7. Evidence / files

| File | What it contains |
|---|---|
| `mission-04-programs/hello.py` | The Python program |
| `mission-04-programs/README.md` | This report |
| `evidence/mission-04/hello-output.txt` | The captured output of `python3 hello.py` |

## 8. Commit details

| Field | Value |
|---|---|
| Commit message | `Compare compilers and interpreters` |
| Files in commit | `mission-04-programs/hello.py`, `mission-04-programs/README.md`, `evidence/mission-04/hello-output.txt` |
