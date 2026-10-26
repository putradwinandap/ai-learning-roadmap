# 09: Errors and debugging

> Syntax: [Python](../tracks/python/lessons/09-errors-and-debugging.md) · [JavaScript](../tracks/javascript/lessons/09-errors-and-debugging.md)

## Why this matters

Bugs are normal. What separates beginners from professionals is how quickly they **find** them, and whether their programs **fail gracefully** instead of crashing on bad input.

## Key ideas

### Three kinds of errors

| Kind | When | Example |
|---|---|---|
| **Syntax error** | Before running | Missing bracket or quote |
| **Runtime error / exception** | While running | Dividing by zero, converting `"abc"` to a number, a missing file |
| **Logic error** | Never reported | Program runs but gives the wrong answer (`>` instead of `>=`) |

Logic errors are the hardest because nothing tells you about them. Tests and careful checking find them.

### Reading a stack trace

When an exception isn't handled, you get a **stack trace**: the chain of function calls that led to the error. Read it **bottom-up** (Python) or **top-down** (JavaScript): find the error type and message, then the **first line that's in your code**.

### Handling exceptions

```text
try:
    amount ← to_number(text)
catch conversion error:
    print "Please enter a number like 12.50"
```

Rules:
- Catch **specific** errors you expect, not "everything". Catching everything hides real bugs.
- Keep the `try` block **small**: just the line that can fail.
- Tell the user **what went wrong and what to do**.

### Validate first, or try and recover?

Both are valid:
- **Validate**: check before acting (`if text is empty: ...`). Clear for simple rules.
- **Try/catch**: attempt and handle failure. Better when checking in advance is hard (parsing, files).

### Raising your own errors

Functions deep in your program shouldn't print. They should **signal** a problem and let the caller decide:

```text
function parse_amount(text):
    value ← to_number(text)          # may raise
    if value <= 0: raise error "Amount must be positive"
    return value
```

### A debugging process

1. **Reproduce** it reliably. Which exact input causes it?
2. **Read** the error and stack trace fully.
3. **Inspect**: print variables at key points, or use your editor's **debugger** (breakpoints, step over, watch values).
4. **Form a hypothesis**: "I think `total` is a string, not a number".
5. **Test it** with the smallest change. Confirm or reject.
6. **Fix it, then re-run** the original scenario *and* nearby ones.

Explaining the code out loud, line by line, to someone (or a rubber duck) finds a surprising number of bugs.

## Exercise

1. Write `ask_positive_number(prompt)` that keeps asking until the user types a valid positive number. Test it with `abc`, `-5`, an empty line and `12.5`.
2. Set a breakpoint in a loop in one of your earlier programs and step through it in your editor's debugger, watching a variable change.
3. Here's a logic bug: "average of `[2, 4, 6]` prints `2.0`". Write down three hypotheses for what's wrong.

## Check your understanding

1. Name the three kinds of errors and how you'd notice each one.
2. Why is catching *all* exceptions a bad idea?
3. Why should a function like `parse_amount` raise an error instead of printing?
4. What's the first thing you do with a stack trace?
