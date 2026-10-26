# 01 (Python): Values, variables and types

Core lesson: [01: Values, variables and types](../../../lessons/01-values-variables-and-types.md)

## Types

```python
count = 42            # int
price = 12.5          # float
title = "Dune"        # str ('single' or "double" quotes both work)
in_stock = True       # bool (capital T/F)
discount = None       # NoneType: "no value"

print(type(price))    # <class 'float'>
```

## Naming

`snake_case` for variables and functions, `UPPER_CASE` for constants:

```python
MAX_ITEMS = 50
book_title = "Dune"
is_available = True
```

Python has no enforced constants. `UPPER_CASE` is a promise not to reassign.

## Conversion

```python
int("42")        # 42
float("12.5")    # 12.5
str(42)          # "42"
int("12.5")      # ValueError! use float() first
float("abc")     # ValueError
bool("")         # False, bool("anything") is True
```

```python
raw = input("Pages read today: ")   # always a str
pages = int(raw)
print(pages + 10)
```

## Type hints (optional at this level)

You can annotate types. Python doesn't enforce them at runtime, but editors and tools use them:

```python
pages: int = 10
title: str = "Dune"
```

## Floats and rounding

```python
print(0.1 + 0.2)              # 0.30000000000000004
print(round(0.1 + 0.2, 2))    # 0.3
print(f"{0.1 + 0.2:.2f}")     # "0.30": format with 2 decimals for display
```

For exact money math, the standard library has `decimal.Decimal`:

```python
from decimal import Decimal
print(Decimal("0.1") + Decimal("0.2"))   # 0.3
```

Either store cents as `int`, use `Decimal`, or keep floats and **always format to 2 decimals** when displaying. Any of these is acceptable at Level 01 if you're consistent.
