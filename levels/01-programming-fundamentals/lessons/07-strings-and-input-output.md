# 07: Strings and input/output

> Syntax: [Python](../tracks/python/lessons/07-strings-and-input-output.md) · [JavaScript](../tracks/javascript/lessons/07-strings-and-input-output.md)

## Why this matters

Command-line programs talk to people through text. Clean input handling and well-formatted output separate a frustrating tool from a pleasant one.

## Key ideas

### Strings are sequences of characters

You can get their length, index into them, slice them, and loop over them, much like lists. In most languages strings are **immutable**: operations return a *new* string.

### Everyday string operations

| Task | Typical name |
|---|---|
| Remove surrounding spaces | `strip` / `trim` |
| Change case | `lower`, `upper` |
| Split into parts | `split(",")` → list |
| Join parts | `join` |
| Check content | `startswith`, `endswith`, `contains`/`in` |
| Replace | `replace` |

### Normalising input

Users type `" Food"`, `"FOOD"`, `"food "`. Normalise before comparing or storing:

```text
category ← lower(trim(raw_input))
```

### Parsing input

Turning text into structured data is **parsing**:

```text
line ← "add 12.50 food lunch with team"
parts ← split(line, " ")        # ["add", "12.50", "food", "lunch", "with", "team"]
command ← parts[0]
amount  ← to_number(parts[1])
note    ← join(parts[3..], " ")  # "lunch with team"
```

Always expect **missing or wrong parts**, and check the length before indexing.

### Formatting output

- **Interpolation** (`f"..."`, `` `...${}` ``) beats concatenation.
- **Fixed decimals**: show money as `12.50`, not `12.5` or `12.4999999`.
- **Alignment**: pad columns so tables line up.

```text
ID  Date        Category    Amount
 1  2026-10-01  food         12.50
 2  2026-10-02  transport    40.00
```

Most languages support width and alignment in format strings. Check your track.

### Program arguments (preview)

Besides interactive input, programs can receive **command-line arguments**: `ledger add 12.5 food`. Your track shows how to read them. It's a stretch goal in the project.

## Exercise

1. Ask for a full name and print it in Title Case, plus the initials (`"ada lovelace"` → `Ada Lovelace (AL)`).
2. Parse a line like `"3 x coffee @ 4.50"` into quantity, item and price, and print the total.
3. Print a 3-column table of at least four rows, with right-aligned numbers and two decimals.

## Check your understanding

1. Why normalise input before storing or comparing it?
2. What can go wrong when you index `parts[1]` after splitting user input?
3. How do you print `7` as `7.00`?
