# 10 (Python): Program structure

Core lesson: [10: Program structure](../../../lessons/10-program-structure.md)

## The main guard

```python
def main() -> None:
    ...

if __name__ == "__main__":
    main()
```

`main()` runs when you execute the file directly (`python notes.py`), but **not** when another file imports it. That lets you import and test functions later (Level 02).

## Constants at the top

```python
from pathlib import Path

DATA_FILE = Path(__file__).parent / "notes.json"
MENU = """
1) Add note
2) List notes
q) Quit
"""
```

## Dispatch table

```python
def add_note(notes: list[dict]) -> list[dict]: ...
def list_notes(notes: list[dict]) -> list[dict]: ...

ACTIONS = {
    "1": add_note,
    "2": list_notes,
}

def main() -> None:
    notes = load_notes(DATA_FILE)
    while True:
        choice = input(MENU + "> ").strip().lower()
        if choice == "q":
            break
        action = ACTIONS.get(choice)
        if action is None:
            print("Unknown option")
            continue
        notes = action(notes)
        save_notes(DATA_FILE, notes)
```

## Splitting into modules

```text
project/
├── main.py       # from cli import run; run()
├── cli.py        # input/print only
├── logic.py      # pure functions
└── storage.py    # load/save
```

```python
# cli.py
from logic import total_pages
from storage import load_notes, save_notes
```

Run with `python main.py` from inside `project/`. Imports like `from logic import ...` work because Python adds the script's folder to its search path.

## Before submitting

```bash
ruff format .
ruff check .
```

Both should finish with no changes or errors.
