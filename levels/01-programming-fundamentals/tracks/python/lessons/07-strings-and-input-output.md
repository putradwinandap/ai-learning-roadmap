# 07 (Python): Strings and input/output

Core lesson: [07: Strings and input/output](../../../lessons/07-strings-and-input-output.md)

## Common methods

```python
s = "  Ada Lovelace  "
s.strip()                 # "Ada Lovelace"
s.strip().lower()         # "ada lovelace"
"ada lovelace".title()    # "Ada Lovelace"
"a,b,c".split(",")        # ["a", "b", "c"]
" ".join(["x", "y"])      # "x y"
"report.pdf".endswith(".pdf")
"12".isdigit()            # True ("12.5".isdigit() is False)
```

## Slicing

```python
word = "Python"
word[0]      # "P"
word[1:4]    # "yth"
word[-3:]    # "hon"
```

## Parsing a line

```python
line = "3 x coffee @ 4.50"
parts = line.split()
if len(parts) != 5:
    print("Expected: <qty> x <item> @ <price>")
else:
    qty, _, item, _, price = parts
    print(f"{item}: {int(qty) * float(price):.2f}")
```

## Format specifiers

Inside f-strings, `:` starts a format spec:

```python
f"{3.14159:.2f}"     # "3.14"
f"{42:>6}"           # "    42" (right-align, width 6)
f"{'tea':<10}|"      # "tea       |" (left-align, width 10)
f"{7:>8.2f}"         # "    7.00"
```

A small table:

```python
rows = [("Dune", 1965, 9.99), ("Emma", 1815, 4.5)]
print(f"{'Title':<12}{'Year':>6}{'Price':>8}")
for title, year, price in rows:
    print(f"{title:<12}{year:>6}{price:>8.2f}")
```

## Command-line arguments

```python
import sys

print(sys.argv)   # python app.py add 12.5 → ['app.py', 'add', '12.5']
```

For anything bigger, the standard library's `argparse` handles options and help text.
