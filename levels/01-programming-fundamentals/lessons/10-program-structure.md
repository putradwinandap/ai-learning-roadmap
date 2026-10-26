# 10: Program structure

> Syntax: [Python](../tracks/python/lessons/10-program-structure.md) · [JavaScript](../tracks/javascript/lessons/10-program-structure.md)

## Why this matters

You now know all the pieces. This lesson is about **putting them together** so a 200-line program stays as easy to read as a 20-line one. It's exactly what the project rubric checks.

## Key ideas

### Separate the layers

Even a small CLI has three responsibilities. Keep them apart:

| Layer | Does | Example functions |
|---|---|---|
| **Interface (I/O)** | Talks to the user: menus, prompts, printing | `show_menu()`, `ask_expense()`, `print_table(expenses)` |
| **Logic** | Pure computations on data | `total(expenses)`, `totals_by_category(expenses)`, `next_id(expenses)` |
| **Storage** | Loads and saves data | `load_expenses(path)`, `save_expenses(path, expenses)` |

Logic functions **never** print or read input. That makes them easy to test (Level 02) and reuse (a web version in Level 04 could reuse them unchanged).

### A main entry point

Put the top-level flow in one `main` function that reads like a summary:

```text
function main():
    expenses ← load_expenses(DATA_FILE)
    while true:
        choice ← show_menu()
        if choice == "q": break
        expenses ← handle(choice, expenses)
        save_expenses(DATA_FILE, expenses)

main()
```

Someone new should understand the whole program by reading `main`.

### Dispatch with a table

Instead of a long `if/else if` over menu choices, map choices to functions:

```text
actions ← {"1": add_expense, "2": list_expenses, "3": show_summary}
action ← actions[choice]
```

### Constants

Values that never change (file name, menu text, categories) go at the top as named constants (`DATA_FILE`, `CATEGORIES`). No "magic numbers" or strings scattered through the code.

### Multiple files (modules)

When a file gets long (> ~200 lines), split it by layer: `storage`, `ledger` (logic), `cli` (interface), `main`. Your track shows how to import between files. For this level's project, one well-organised file **or** a few modules are both fine.

### Comments

- Good names first. A comment should explain **why**, not repeat **what**.
- Delete commented-out code. Git remembers it.
- A short comment at the top of the file saying what the program does is welcome.

### Work in small steps

Build features one at a time, run the program after each, and **commit** each working step. For the project, a good order is:
1. Menu loop that quits.
2. Add + list (in memory).
3. Save/load.
4. Summary.
5. Delete.
6. Validation and error handling.
7. README.

## Exercise

Take your notes program from lesson 08 and restructure it into interface / logic / storage functions with a `main`. Count how many functions now contain both `print` and file access. The goal is zero.

## Check your understanding

1. Name the three layers of a CLI program and one function for each.
2. Why should logic functions never print?
3. What should someone learn by reading your `main` function?
4. Why delete commented-out code?

## Next

You're ready for the [Level 01 project](../project.md).
