# 08: Files and persistence

> Syntax: [Python](../tracks/python/lessons/08-files-and-persistence.md) · [JavaScript](../tracks/javascript/lessons/08-files-and-persistence.md)

## Why this matters

Everything in your variables disappears when the program exits. To **persist** data (keep it between runs), you save it somewhere. The simplest place is a file. Later you'll use databases (Level 04), but the ideas start here.

## Key ideas

### Reading and writing text files

```text
write "hello" to file "notes.txt"        # creates or overwrites
append "more" to file "notes.txt"        # adds to the end
content ← read file "notes.txt"
```

Use your language's safe pattern that **always closes the file**, even if something fails (`with` in Python, the `fs` helpers in Node.js).

### Paths and the working directory

A relative path like `data.json` is resolved from the **working directory**, which is where you ran the program from, not necessarily where the code file is. This is a classic beginner bug. Either:
- document "run from the project folder", or
- build the path relative to the program file (your track shows how).

### Serializing data

Files store **text** (or bytes). To save a list of records, convert it to a text format: that's **serialization**. Loading is **deserialization**.

| Format | Looks like | Good for |
|---|---|---|
| **JSON** | `[{"id": 1, "amount": 12.5}]` | Nested data, records, APIs. Easy to load back into lists and dictionaries. |
| **CSV** | `id,amount\n1,12.5` | Tables, spreadsheets. Everything comes back as strings. |

For the project, **JSON is recommended**.

### The load → change → save cycle

```text
expenses ← load_expenses("expenses.json")    # at start
... user adds/deletes ...
save_expenses("expenses.json", expenses)     # after every change
```

Saving after every change means a crash loses at most one action.

### First run and bad files

- **File doesn't exist** (first run): start with an empty list, don't crash.
- **File is corrupt** (someone edited it badly): tell the user clearly, and don't silently overwrite their data. Rename it to a backup or stop with a helpful message.

### IDs

Records need stable identifiers to delete or edit them. Don't use the list position as the ID, because it changes when you delete items. A simple approach: `next_id ← max existing id + 1`.

## Exercise

1. Write a program that keeps a list of notes: each run, it loads `notes.json`, asks for a new note, appends it, saves, and prints all notes.
2. Delete `notes.json` and run it: does it work the first time?
3. Put invalid text into `notes.json` and run it: what happens? Make it fail gracefully.
4. Run the program from a different folder. Where did the file go?

## Check your understanding

1. What does "serialize" mean?
2. Why is JSON a better fit than CSV for a list of records with mixed types?
3. Why shouldn't list positions be used as IDs?
4. What should happen on the very first run when the data file doesn't exist yet?
