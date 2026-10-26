# 03 (Python): Conditionals

Core lesson: [03: Conditionals](../../../lessons/03-conditionals.md)

## if / elif / else

Blocks are defined by **indentation** (4 spaces) and a colon:

```python
temperature = float(input("°C: "))

if temperature <= 0:
    print("freezing")
elif temperature < 15:
    print("cold")
elif temperature < 25:
    print("mild")
else:
    print("hot")
```

## Truthiness

Falsy values: `False`, `None`, `0`, `0.0`, `""`, `[]`, `{}`. Everything else is truthy.

```python
name = input("Name: ").strip()
if not name:
    print("Name can't be empty")
```

Be explicit when `0` is a meaningful value: `if count is None:` vs `if not count:`.

## Conditional expression

```python
label = "adult" if age >= 18 else "minor"
```

## match (Python 3.10+)

```python
match choice:
    case "1":
        print("Start")
    case "2" | "s":
        print("Settings")
    case "q":
        print("Bye")
    case _:
        print(f"Unknown option: {choice}")
```

## Guard clauses in a function

```python
def describe_pages(text: str) -> str:
    if not text:
        return "Please type something"
    if not text.isdigit():
        return "Whole numbers only"
    pages = int(text)
    if pages == 0:
        return "Nothing read today?"
    return f"Great, {pages} pages!"
```
