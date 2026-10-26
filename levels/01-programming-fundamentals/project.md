# Level 01 project: Pocket Ledger

Build a **command-line expense tracker** that remembers your expenses between runs.

**Location:** `learner/level-01/project/`

## The user's view

```text
$ <run command from your README>
Pocket Ledger, 3 expenses loaded.

1) Add expense
2) List expenses
3) Summary
4) Delete expense
q) Quit
> 1
Amount: 12.5
Category: Food
Description: lunch with team
Date (YYYY-MM-DD, empty = today):
✔ Added #4

> 2
ID  Date        Category    Amount  Description
 1  2026-10-01  transport    40.00  train pass
 2  2026-10-02  food          8.20  groceries
 3  2026-10-05  fun          15.00  cinema
 4  2026-10-26  food         12.50  lunch with team

> 3
Total: 75.70
  food         20.70
  fun          15.00
  transport    40.00
```

The exact wording and layout are up to you. This only shows the idea.

## Requirements

### Must (all required to pass)

| ID | Requirement |
|---|---|
| L01-M1 | **Add** an expense with amount, category, description and date (empty date = today). Each expense gets a unique, stable **ID**. |
| L01-M2 | **List** all expenses in a readable, aligned table, with amounts shown with exactly 2 decimals. |
| L01-M3 | **Summary**: grand total, and total per category. |
| L01-M4 | **Delete** an expense by ID. An unknown ID shows a clear message. |
| L01-M5 | **Persistence**: data is saved to a file (JSON recommended) after every change and loaded on start. The first run, with no data file yet, works. |
| L01-M6 | **Input validation**: non-numeric, zero or negative amounts, empty category and invalid dates are rejected with a helpful message. The program **never crashes** on user input. |
| L01-M7 | **Structure**: logic is split into functions with single responsibilities. Logic functions (totals, ID generation, ...) don't print or read input. There's a clear `main` entry point. |
| L01-M8 | **README** in the project folder: what it does, required language version, how to run it, where data is stored, and the data file format. |

### Should (expected for a good score)

| ID | Requirement |
|---|---|
| L01-S1 | **Filter** the list by category or by month. |
| L01-S2 | Categories are **normalised** (`" Food "` and `food` are the same category). |
| L01-S3 | A **corrupt data file** is handled gracefully: a clear message, and user data is never silently overwritten. |
| L01-S4 | At least **5 incremental commits** showing the program growing feature by feature. |
| L01-S5 | Your track's **formatter and linter** pass with no errors. |

### Stretch (optional)

| ID | Requirement |
|---|---|
| L01-X1 | **Edit** an existing expense. |
| L01-X2 | **Monthly budget**: set a limit per category and warn when a new expense exceeds it. |
| L01-X3 | **Argument mode**: `... add 12.5 food "lunch"` and `... summary` work without the interactive menu. |
| L01-X4 | **Export** to CSV. |

## Acceptance scenarios

The reviewer will try at least these:

1. Delete the data file, start the program → it starts with 0 expenses, no crash.
2. Add 3 expenses in 2 categories, quit, restart → all 3 are listed with correct IDs.
3. Summary totals are correct, to the cent (try amounts like `0.10` and `0.20`).
4. Enter `abc`, `-5`, `0` and an empty line as amount → each is rejected, and the program keeps running.
5. Enter `2026-13-45` as date → rejected.
6. Delete an expense, add a new one → IDs are never reused or duplicated.
7. Delete ID `999` → clear "not found" message.
8. Replace the data file's content with `not json` → handled gracefully (S3).

## Rules

- Use only your language's **standard library**. No third-party packages for the program itself. Dev tools like formatters and linters are fine.
- Write the code yourself. Your mentor can explain concepts and give hints ([hint policy](../../ai/hint-policy.md)), and you'll be asked to explain your code in the review.

When you're done, run `/review-project`.
