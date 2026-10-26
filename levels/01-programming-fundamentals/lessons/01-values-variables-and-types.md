# 01: Values, variables and types

> Syntax: [Python](../tracks/python/lessons/01-values-variables-and-types.md) · [JavaScript](../tracks/javascript/lessons/01-values-variables-and-types.md)

## Why this matters

Programs work with **data**: names, prices, dates, yes/no answers. You need a way to store data, give it a name, and know what kind of data it is, because the kind decides what you can do with it.

## Key ideas

### Values and types

A **value** is a piece of data. Every value has a **type**:

| Type (general name) | Examples | What it's for |
|---|---|---|
| Integer | `42`, `-7`, `0` | Whole numbers, counting |
| Floating-point number | `3.14`, `-0.5` | Numbers with decimals, measurements |
| String | `"hello"`, `"42"` | Text |
| Boolean | `true`, `false` | Yes/no, on/off |
| Nothing / null | `null`, `None`, `nil` | "No value here" |

`42` and `"42"` are **different**: one is a number you can do math with, the other is text that happens to contain digits.

### Variables

A **variable** is a name that refers to a value.

```text
price ← 12.50
item ← "coffee"
paid ← false
```

- You **assign** a value with `=` (in most languages). Read `price = 12.50` as "price *gets* 12.50", not "price *equals* 12.50".
- You can **reassign**: `price ← 13.00`. The old value is gone.
- Some languages let you declare **constants** that can't be reassigned. Prefer them when the value shouldn't change.

### Naming

Names are for humans. Good names make code readable without comments.

| ❌ | ✅ |
|---|---|
| `x`, `a1`, `data` | `total_price`, `userName`, `is_paid` |
| `temp2` | `previous_balance` |

Follow your language's convention (`snake_case` in Python, `camelCase` in JavaScript). Booleans read well as questions: `is_valid`, `hasItems`.

### Static vs. dynamic typing

- **Dynamically typed** languages (Python, JavaScript, Ruby, PHP) check types while the program runs. A variable can hold any type.
- **Statically typed** languages (Go, Java, C#, Rust, TypeScript) check types *before* running. Each variable has a fixed type.

Either way, **types matter**. Mixing them carelessly causes bugs.

### Converting between types

Input from the keyboard or a file usually arrives as a **string**. To do math, you must convert it:

```text
text ← "12.5"
amount ← to_number(text)     # 12.5
label ← to_string(amount)    # "12.5"
```

Conversion can **fail** (`to_number("abc")`). You'll handle that in lesson 09.

### Floating-point surprise

Computers store most decimals approximately. In almost every language:

```text
0.1 + 0.2  →  0.30000000000000004
```

For money, either round when displaying, store whole cents as integers, or use a decimal type. You'll need this in the project.

## Exercise

In your language:
1. Create variables for a product name, its price, the quantity, and whether it's in stock.
2. Print each one together with its type (your track shows how to check the type).
3. Read a number from the keyboard and add 10 to it. What happens if you forget to convert it?
4. Print `0.1 + 0.2`. Then print it rounded to 2 decimals.

## Check your understanding

1. What's the difference between `42` and `"42"`?
2. Why is `x` a bad variable name in most cases?
3. Why must you convert keyboard input before doing math?
4. Why is storing money as a float risky?

## Further reading

- [What every programmer should know about floating-point](https://floating-point-gui.de/)
