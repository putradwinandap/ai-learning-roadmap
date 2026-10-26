# 05: Functions

> Syntax: [Python](../tracks/python/lessons/05-functions.md) · [JavaScript](../tracks/javascript/lessons/05-functions.md)

## Why this matters

Without functions, programs become one long wall of code that's impossible to read, test or change. A **function** packages a piece of logic under a name so you can reuse it and reason about it on its own.

## Key ideas

### Defining and calling

```text
function area(width, height):
    return width * height

room ← area(4, 5)       # 20
```

- **Parameters** (`width`, `height`) are the inputs the function expects.
- **Arguments** (`4`, `5`) are the actual values you pass in.
- **`return`** sends a value back to the caller and ends the function.

### Return vs. print

A function that **returns** a value is far more useful than one that **prints** it: the caller decides what to do with the result (print it, save it, compute more with it).

```text
# ❌ Can only be shown on screen
function show_total(expenses): print sum of amounts

# ✅ Reusable everywhere
function total(expenses): return sum of amounts
print format_money(total(expenses))
```

Rule of thumb: **compute in one function, display in another.**

### Scope

Variables created inside a function are **local**: they exist only while the function runs and aren't visible outside. That's a feature: functions can't accidentally break each other.

Avoid relying on **global** variables changed from inside functions. Pass data in as parameters, and get results out with `return`.

### Single responsibility

Each function should do **one thing**, describable in a short sentence without "and". If you can't name it well, it probably does too much.

| ❌ | ✅ |
|---|---|
| `handle_stuff()` | `parse_amount(text)` |
| `process(data)` that validates, saves and prints | `validate_expense(...)`, `save_expenses(...)`, `print_expense_table(...)` |

Good size for now: **under ~25 lines**.

### Default and named arguments

Many languages let parameters have defaults (`date = today`) and let callers name arguments (`add_expense(amount=5, category="food")`). Defaults reduce repetition; names make calls readable.

### Pure functions

A **pure** function's output depends only on its inputs, and it has no side effects (no printing, no file writing, no changing globals). Pure functions are the easiest to test and reuse. Keep **side effects at the edges** of your program (input/output), and logic in the middle pure.

## Exercise

1. Write `celsius_to_fahrenheit(c)` and `fahrenheit_to_celsius(f)`. Check that converting back and forth gives the original number.
2. Write `is_valid_amount(text)` that returns true/false. Write `format_money(amount)` that returns a string like `"12.50"`.
3. Take your multiplication-table or menu program from lesson 04 and split it into at least three functions.

## Check your understanding

1. Parameter vs. argument?
2. Why is returning a value usually better than printing it inside the function?
3. What is a local variable?
4. What makes a function "pure", and why is that useful?
