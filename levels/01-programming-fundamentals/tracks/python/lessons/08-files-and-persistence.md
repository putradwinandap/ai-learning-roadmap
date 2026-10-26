# 08 (Python): Files and persistence

Core lesson: [08: Files and persistence](../../../lessons/08-files-and-persistence.md)

## Paths with pathlib

```python
from pathlib import Path

# Folder that contains THIS .py file, independent of where you run it from
BASE_DIR = Path(__file__).parent
NOTES_FILE = BASE_DIR / "notes.json"

NOTES_FILE.exists()       # True / False
```

## Reading and writing text

```python
path = Path("hello.txt")
path.write_text("hello\n", encoding="utf-8")
content = path.read_text(encoding="utf-8")
```

Or with `open`. `with` closes the file automatically, even on errors:

```python
with open(path, "a", encoding="utf-8") as f:   # "a" = append, "w" = overwrite, "r" = read
    f.write("another line\n")
```

Always pass `encoding="utf-8"`. The default differs between operating systems.

## JSON

```python
import json

notes = [{"id": 1, "text": "buy milk"}]

# save
NOTES_FILE.write_text(json.dumps(notes, indent=2), encoding="utf-8")

# load
notes = json.loads(NOTES_FILE.read_text(encoding="utf-8"))
```

JSON ↔ Python: object ↔ `dict`, array ↔ `list`, string ↔ `str`, number ↔ `int`/`float`, `true` ↔ `True`, `null` ↔ `None`.

## First run and corrupt files

```python
def load_notes(path: Path) -> list[dict]:
    if not path.exists():
        return []
    try:
        return json.loads(path.read_text(encoding="utf-8"))
    except json.JSONDecodeError:
        raise ValueError(f"{path} is not valid JSON. Fix or move it, then try again.")
```

The function signals the problem, and the caller decides how to tell the user (lesson 09).

## Dates

```python
from datetime import date

today = date.today().isoformat()         # "2026-10-26"
date.fromisoformat("2026-10-01")         # date object
date.fromisoformat("2026-13-45")         # ValueError
```

Store dates as ISO strings (`YYYY-MM-DD`) in JSON. They sort correctly as text.

## Next ID

```python
next_id = max((n["id"] for n in notes), default=0) + 1
```
