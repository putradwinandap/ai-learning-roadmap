# 02 (Python): Operators and expressions

Core lesson: [02: Operators and expressions](../../../lessons/02-operators-and-expressions.md)

## Arithmetic

```python
7 / 2     # 3.5   (always a float)
7 // 2    # 3     (floor division)
7 % 2     # 1     (remainder)
2 ** 10   # 1024  (power)
```

## Comparison and logic

```python
age >= 18 and has_ticket
day == "Sat" or day == "Sun"
not is_closed
```

Python allows chained comparisons:

```python
0 <= score <= 100      # same as 0 <= score and score <= 100
```

Membership with `in`:

```python
day in ("Sat", "Sun")
```

## Assignment shortcuts

```python
total += price
count -= 1
```

There is no `++` in Python.

## Strings

```python
"ab" + "cd"    # "abcd"
"-" * 10       # "----------"
"Pages: " + 5  # TypeError! Python doesn't auto-convert
f"Pages: {5}"  # ✅
```

## Exercise hints

- Seconds → `1h 2m 5s`: use `//` and `%` together, or `divmod(seconds, 3600)`.
- Leap year as one expression: combine `%`, `and`, `or`, and use parentheses.
