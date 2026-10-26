# 04: Loops

> Syntax: [Python](../tracks/python/lessons/04-loops.md) · [JavaScript](../tracks/javascript/lessons/04-loops.md)

## Why this matters

Computers are great at repetition. Loops let you process every item in a list, keep a menu running until the user quits, or retry until input is valid, without writing the same code again and again.

## Key ideas

### Two kinds of loops

| Loop | Use when | Pseudocode |
|---|---|---|
| **for-each** | you have a collection or a range to go through | `for each expense in expenses: print expense` |
| **while** | you repeat until a condition changes | `while user hasn't typed "quit": show menu` |

### for-each over a range

```text
for i in range 1 to 5:
    print i          # 1 2 3 4 5
```

Ranges are often **end-exclusive** (`range(1, 5)` gives 1–4 in Python). Off-by-one errors are the most common loop bug. Check the first and last iteration.

### while and infinite loops

```text
answer ← ""
while answer != "quit":
    answer ← ask "Command? "
    handle answer
```

If the condition never becomes false, the loop runs forever. Press **Ctrl+C** to stop it. Make sure something inside the loop moves you toward the exit.

### break and continue

- `break` leaves the loop immediately.
- `continue` skips to the next iteration.

```text
while true:
    command ← ask "Command? "
    if command == "quit": break
    if command == "": continue      # ignore empty input
    handle command
```

The `while true` + `break` pattern is the standard way to write a **menu loop**.

### Accumulators

A very common pattern: start with an initial value and update it on each iteration.

```text
total ← 0
for each expense in expenses:
    total ← total + expense.amount
```

The same shape gives you counts (`count += 1`), maximums (`if x > best: best = x`), and filtered lists.

### Nested loops

A loop inside a loop runs the inner loop fully for **each** outer iteration. 10 × 10 = 100 iterations. Useful for grids and tables, but watch the cost (Level 02 covers why).

## Exercise

1. Print the multiplication table for a number the user chooses (1–10).
2. Keep asking for numbers until the user types `done`, then print the count, sum, average and maximum.
3. Write a menu loop with options `1) say hi`, `2) show time`, `q) quit`. Empty input is ignored, unknown input shows an error.

## Check your understanding

1. When would you choose `while` over `for`?
2. What's an off-by-one error? How do you check for one?
3. Describe the accumulator pattern and give two uses.
4. What does `continue` do?
