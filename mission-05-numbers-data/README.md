# Mission 5 - Numbers and Data

## 1. Task / objective
Convert numbers between decimal, binary and hexadecimal, verify the results with
Python, build a small Python number converter, and explain how text is stored using
character encoding.

## 2. Work completed
- Converted seven values by hand between decimal, binary and hexadecimal.
- Verified each conversion using Python's `bin()`, `int(..., base)` and `hex()`
  built-in functions in a non-interactive script.
- Wrote `number_converter.py`, which asks the user for a decimal number and prints
  its binary and hexadecimal forms.
- Tested the converter with three positive numbers (5, 10 and 42).
- Found the ASCII decimal codes for `A` and `a`, explained why an encoding standard
  is needed, and identified a non-ASCII character.

## 3. Commands / tools used

| Command / tool | Purpose |
|---|---|
| `python3 -c "..."` | Run one-line Python expressions to verify the manual conversions |
| `python3 mission-05-numbers-data/number_converter.py` | Run the number converter program |
| `echo 5 \| python3 ...` | Feed test input to the program without typing it manually |
| Text editor (VS Code) | Write `number_converter.py` and this README |

## 4. My understanding

### Task 5.1 - Manual conversions

Decimal uses base 10, binary uses base 2 and hexadecimal uses base 16
(A=10, B=11, C=12, D=13, E=14, F=15).

| Question | Working and answer |
|---|---|
| Convert decimal 13 to binary | 13 = 8 + 4 + 1 → bits 8, 4, 2, 1 → `1 1 0 1` → **1101** |
| Convert decimal 25 to binary | 25 = 16 + 8 + 1 → bits 16, 8, 4, 2, 1 → `1 1 0 0 1` → **11001** |
| Convert binary 1010 to decimal | 1×8 + 0×4 + 1×2 + 0×1 = 8 + 2 → **10** |
| Convert binary 1101 to decimal | 1×8 + 1×4 + 0×2 + 1×1 = 8 + 4 + 1 → **13** |
| Convert hexadecimal A to decimal | A = 10 → **10** |
| Convert hexadecimal 1F to decimal | 1×16 + 15×1 = 16 + 15 → **31** |
| Convert binary 1111 to hexadecimal | 1111 in binary = 15 in decimal = **F** |

### Task 5.2 - Verification with Python

| Expression tested | Python result | Matches manual answer? |
|---|---|---|
| `bin(13)` | `0b1101` | Yes |
| `bin(25)` | `0b11001` | Yes |
| `int('1010', 2)` | `10` | Yes |
| `int('1101', 2)` | `13` | Yes |
| `int('A', 16)` | `10` | Yes |
| `int('1F', 16)` | `31` | Yes |
| `hex(15)` | `0xf` | Yes |

Every manual answer matches Python's result. `bin()` returns the binary form with the
`0b` prefix, `hex()` returns the hexadecimal form with `0x`, and `int(x, base)` reads
a string in the given base and returns a decimal integer.

### Task 5.3 - The number converter

`number_converter.py`:

    num = int(input("Enter a decimal number: "))
    print(f"Binary: {bin(num)}")
    print(f"Hexadecimal: {hex(num)}")

**What the conversion functions do:**
`bin(num)` turns the integer into a string starting with `0b` followed by its base-2
digits. `hex(num)` turns the integer into a string starting with `0x` followed by its
base-16 digits. `int(input(...))` reads the typed text and converts it from a decimal
string to an integer so the two conversion functions can use it.

**Test results:**

| Test number | Binary output | Hexadecimal output |
|---|---|---|
| 5 | `0b101` | `0x5` |
| 10 | `0b1010` | `0xa` |
| 42 | `0b101010` | `0x2a` |

### Task 5.4 - How text is stored

- **ASCII decimal codes:** uppercase `A` = **65**; lowercase `a` = **97**.
- **Why an encoding standard is needed:** a computer can only store bits (0s and 1s),
  so every character must be given a fixed number that both the writer and the reader
  agree on. Without an agreed mapping, the same bytes could mean different letters on
  different machines.
- **A character that is not in basic ASCII:** `é` (for example in the word "café"),
  or the Devanagari character `अ`. Basic ASCII only covers 128 codes, so text in most
  of the world's scripts needs an encoding such as UTF-8, which extends ASCII and can
  represent any Unicode character.

## 5. Difficulties faced
The pasted multi-line block in the interactive `python3` shell did not execute — the
`...` prompt appeared and nothing ran.

## 6. How I resolved them
I ran each verification as a one-line command instead, using
`python3 -c "print(..., bin(13))"`. This produced clean, one-shot output that could be
copied straight into `evidence/mission-05/python-verification.txt` without the shell
interpretation problem.

## 7. Evidence / files

| File | What it contains |
|---|---|
| `mission-05-numbers-data/README.md` | This report |
| `mission-05-numbers-data/number_converter.py` | The working converter |
| `evidence/mission-05/python-verification.txt` | Output of the seven `python3 -c` verification commands |
| `evidence/mission-05/converter-tests.txt` | Output of running the converter with 5, 10 and 42 |

## 8. Commit details

| Field | Value |
|---|---|
| Commit message | `Build number converter and practise data representation` |
| Files in commit | `mission-05-numbers-data/README.md`, `mission-05-numbers-data/number_converter.py`, `evidence/mission-05/*` |
