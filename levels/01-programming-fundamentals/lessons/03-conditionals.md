# 03: Conditionals

> Syntax: [Python](../tracks/python/lessons/03-conditionals.md) · [JavaScript](../tracks/javascript/lessons/03-conditionals.md)

## Why this matters

Real programs make **decisions**: is this password correct? Is the cart empty? Is the amount valid? Conditionals let your program take different paths depending on data.

## Key ideas

### if / else if / else

```text
if amount < 0:
    print "Amount can't be negative"
else if amount == 0:
    print "Nothing to add"
else:
    add the expense
```

- Conditions are checked **top to bottom**. The **first** true branch runs, and the rest are skipped.
- `else` is optional and catches everything else.
- The body of each branch is a **block**, marked by indentation (Python) or braces `{ }` (most other languages).

### Order matters

```text
# ❌ The second branch can never run
if score >= 50: grade ← "pass"
else if score >= 90: grade ← "excellent"

# ✅ Most specific first
if score >= 90: grade ← "excellent"
else if score >= 50: grade ← "pass"
else: grade ← "fail"
```

### Truthiness

Many languages treat some values as "false-like" in conditions: `0`, empty string `""`, empty list, `null`/`None`. This is handy (`if name:` means "if name isn't empty") but can surprise you: is `0` a valid amount, or "nothing"? Be explicit when it matters.

### Guard clauses

Instead of deeply nested ifs, handle the "bad" cases first and exit early:

```text
# ❌ Nested
if input is not empty:
    if input is a number:
        if number > 0:
            ...do the work...

# ✅ Guard clauses
if input is empty: return "Please type something"
if input is not a number: return "Not a number"
if number <= 0: return "Must be positive"
...do the work...
```

The happy path stays flat and readable.

### Matching many values

When you compare one value against many options (menu choices!), use your language's `match`/`switch` statement, or a lookup table (lesson 06) instead of a long chain of `else if`.

## Exercise

1. Ask for a temperature in °C and print "freezing" (≤ 0), "cold" (< 15), "mild" (< 25) or "hot".
2. Write a menu: ask the user to type `1`, `2` or `3` and print a different message for each. Print a helpful error for anything else.
3. Rewrite a nested-if validation (empty? number? positive?) using guard clauses.

## Check your understanding

1. If two branches of an `if / else if` chain are both true, which runs?
2. What's a guard clause and why is it useful?
3. Your language treats `0` as false. Why might `if amount:` be a bug when checking user input?
