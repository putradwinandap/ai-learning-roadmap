# 06 (Python): Your first program

Core lesson: [06: Your first program](../../../lessons/06-your-first-program.md)

## Output: `print`

```python
print("Hello, world!")
print("Two", "values")       # print separates values with a space
```

## Input: `input`

`input()` shows a prompt, waits for the user to press Enter, and returns what they typed **as text** (a string).

```python
city = input("Which city do you live in? ")
print("Nice, I've heard", city, "is lovely.")
```

## Combining text: f-strings

Put `f` before the quotes and variables inside `{}`:

```python
city = input("Which city? ")
print(f"Welcome to {city}!")
print(f"{city} has {len(city)} letters.")   # len() counts characters
```

`len(...)` is a small computation. You can put any expression inside `{}`.

## Cleaning input

Users type extra spaces. `.strip()` removes spaces from both ends:

```python
city = input("Which city? ").strip()
```

## Running your file

```bash
cd learner/level-00/scratch
python first.py
```

## Today's date and time (useful for computed details)

```python
from datetime import datetime

now = datetime.now()
print(now.strftime("%A"))   # day of the week, e.g. "Monday"
print(now.hour)             # hour as a number, 0–23
```

The `from ... import ...` line goes at the **top** of the file.

## Common first errors

| Error | Usually means |
|---|---|
| `SyntaxError: unterminated string literal` | Missing closing quote. |
| `NameError: name 'citty' is not defined` | Typo in a variable name, or used before it was created. |
| `IndentationError` | Unexpected spaces at the start of a line. In Python, indentation matters. |
| `can't open file ... No such file or directory` | You're in the wrong folder. Check with `pwd`. |

## Exercise (Python)

Do the core lesson's exercise in Python: ask for a name and a favourite food, print a sentence with both, and add one computed detail of your choice (but don't reuse it in your project).
