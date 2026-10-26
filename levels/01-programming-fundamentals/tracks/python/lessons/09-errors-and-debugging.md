# 09 (Python): Errors and debugging

Core lesson: [09: Errors and debugging](../../../lessons/09-errors-and-debugging.md)

## Reading a traceback

Read Python tracebacks **from the bottom up**:

```text
Traceback (most recent call last):
  File "/home/ana/app.py", line 12, in <module>
    main()
  File "/home/ana/app.py", line 8, in main
    pages = int(raw)
            ^^^^^^^^
ValueError: invalid literal for int() with base 10: 'ten'
```

1. Last line: the **type** (`ValueError`) and **message**.
2. Just above: the **exact line** (`app.py`, line 8).
3. Further up: how you got there.

## Common exceptions

| Exception | Typical cause |
|---|---|
| `ValueError` | Right type, bad value: `int("ten")`, `date.fromisoformat("2026-13-45")` |
| `TypeError` | Wrong type: `"a" + 1` |
| `KeyError` | Missing dict key: `book["isbn"]` |
| `IndexError` | List index out of range |
| `FileNotFoundError` | File doesn't exist |
| `json.JSONDecodeError` | Invalid JSON (a subclass of `ValueError`) |

## try / except / else

```python
raw = input("Pages: ")
try:
    pages = int(raw)
except ValueError:
    print(f"'{raw}' isn't a whole number.")
else:
    print(f"Logged {pages} pages.")
```

Catch **specific** exceptions. A bare `except:` or `except Exception:` around everything hides bugs.

## Raising

```python
def parse_rating(text: str) -> int:
    rating = int(text)                    # may raise ValueError
    if not 1 <= rating <= 5:
        raise ValueError("Rating must be between 1 and 5")
    return rating
```

Caller:

```python
try:
    rating = parse_rating(input("Rating: "))
except ValueError as error:
    print(f"Invalid rating: {error}")
```

## Re-prompt until valid

```python
def ask_int(prompt: str) -> int:
    while True:
        raw = input(prompt).strip()
        try:
            return int(raw)
        except ValueError:
            print("Please enter a whole number.")
```

## Debugging tools

- `print(f"{variable=}")` prints the name *and* value: `variable=42`.
- `breakpoint()` pauses the program and opens the `pdb` debugger. Commands: `n` (next), `s` (step into), `p name` (print), `c` (continue), `q` (quit).
- VS Code: click left of a line number to set a breakpoint, then press **F5** → "Python File".
