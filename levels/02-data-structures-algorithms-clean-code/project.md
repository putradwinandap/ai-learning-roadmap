# Level 02 project: Shelf

A **library-management CLI** for a small community library: books, members and loans, with search, sorting and business rules, all covered by unit tests.

**Location:** `learner/level-02/project/`

## Requirements

### Must

| ID | Requirement |
|---|---|
| L02-M1 | Manage **books** (ISBN, title, author, year, copies) and **members** (ID, name). Add, list, remove. |
| L02-M2 | **Loans**: a member borrows a book (if a copy is available) and returns it. Rules: max 3 active loans per member, a book with no copies left can't be borrowed, a member with overdue loans can't borrow. Loans last 14 days. |
| L02-M3 | **Search** books by title or author (case-insensitive, partial match). |
| L02-M4 | **Sort** book lists by title, author or year. Implement **one sorting algorithm yourself** (merge sort or quicksort) and use it for at least one of these. |
| L02-M5 | Choose data structures deliberately: lookup of a book by ISBN and of a member by ID must be **O(1)** on average. |
| L02-M6 | **Domain logic is separated from the CLI** and modelled with classes or modules with clear responsibilities. |
| L02-M7 | **Unit tests** with your language's standard test runner: ≥ 20 tests covering loan rules, search, your sort algorithm, and edge cases (empty library, duplicate ISBN, returning a book that isn't on loan, ...). All tests pass. |
| L02-M8 | Persistence to a file (as in Level 01). |
| L02-M9 | README: how to run the app and the tests, plus a short **"Design decisions"** section explaining your data structures and the Big-O of search, borrow and your sort. |

### Should

| ID | Requirement |
|---|---|
| L02-S1 | **Time is injectable** (pass "today" in as a parameter or clock object), so overdue rules can be tested without waiting 14 days. |
| L02-S2 | Some features were written **test-first** (TDD), visible in the commit history (test commit before implementation commit). |
| L02-S3 | **Report** command: top 5 most borrowed books, members with overdue loans. |
| L02-S4 | No function longer than ~30 lines. No duplicated logic. |

### Stretch

| ID | Requirement |
|---|---|
| L02-X1 | **Reservation queue**: when a book is unavailable, members can join a FIFO waiting list. |
| L02-X2 | **Undo** the last action, using a stack. |
| L02-X3 | **Recommendations**: "members who borrowed this also borrowed ..." using a graph or co-occurrence map. |
| L02-X4 | Test coverage report ≥ 80% for domain code. |

## Acceptance scenarios

1. Run the test suite with the command in your README → all tests pass.
2. A member with 3 active loans tries to borrow a 4th → refused with a clear reason.
3. Borrow the last copy of a book, then another member tries → refused. Return it → now allowed.
4. With "today" set to 15 days after a loan, the member is marked overdue and can't borrow.
5. Search `"dun"` finds "Dune". Sorting by year with your own sort matches the language's built-in sort.
6. Add a book with an existing ISBN → handled (rejected, or copies increased, as documented).

## Rules

Standard library plus your language's standard test runner. No third-party runtime dependencies.
