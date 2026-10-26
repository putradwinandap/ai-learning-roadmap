# 02: Operators and expressions

> Syntax: [Python](../tracks/python/lessons/02-operators-and-expressions.md) · [JavaScript](../tracks/javascript/lessons/02-operators-and-expressions.md)

## Why this matters

Storing data is only half the story. You also need to **compute** with it: add prices, compare dates, check conditions. Operators are the verbs of programming.

## Key ideas

### Expressions

An **expression** is anything that produces a value: `3`, `price`, `price * quantity`, `age >= 18`. A **statement** does something: assign, print, loop.

### Arithmetic

| Operator | Meaning | Example → result |
|---|---|---|
| `+ - * /` | add, subtract, multiply, divide | `7 / 2 → 3.5` (in most languages) |
| `%` | remainder (modulo) | `7 % 2 → 1` |
| `**` or a power function | exponent | `2 ** 3 → 8` |
| integer division | divide and drop the fraction | `7 // 2 → 3` (Python), `Math.floor(7 / 2)` (JS) |

`%` is more useful than it looks: `n % 2 == 0` checks for even numbers, and `minutes % 60` gives leftover minutes.

### Precedence

As in math: parentheses, then `*` `/` `%`, then `+` `-`. **When in doubt, add parentheses.** They cost nothing and make intent clear.

```text
total ← price * quantity + shipping        # ok
total ← (price + tax) * quantity           # parentheses required
```

### Comparison

`==` (equal), `!=` (not equal), `<`, `<=`, `>`, `>=`. They produce booleans.

> Don't confuse `=` (assign) with `==` (compare). Some languages (JavaScript) also have `===` for strict comparison. Check your track.

### Logical operators

| Operator | True when |
|---|---|
| `and` / `&&` | both sides are true |
| `or` / `\|\|` | at least one side is true |
| `not` / `!` | the value is false |

```text
can_rent_car ← age >= 21 and has_license
is_weekend ← day == "Sat" or day == "Sun"
```

**Short-circuiting**: `a and b` doesn't evaluate `b` if `a` is false. That's useful: `items_count > 0 and total / items_count > 10` never divides by zero.

### Assignment shortcuts

`total += price` means `total = total + price`. Also `-=`, `*=`, `/=`.

### String operators

Most languages use `+` to join strings, and many let you repeat them (`"-" * 20` in Python, `"-".repeat(20)` in JS). Joining a number and a string may fail (Python) or silently convert (JavaScript). Know which one your language does.

## Exercise

1. Given a total number of seconds (e.g. `3725`), compute hours, minutes and remaining seconds, and print `1h 2m 5s`.
2. Given a year, compute whether it's a leap year (divisible by 4, except centuries, unless divisible by 400) as a single boolean expression.
3. Predict, then run: `10 - 2 * 3`, `(10 - 2) * 3`, `17 % 5`, `not (3 > 2 and 2 > 3)`.

## Check your understanding

1. What does `%` compute? Give a practical use.
2. What's the difference between `=` and `==`?
3. Why does `count > 0 and total / count > 5` never crash with division by zero?
