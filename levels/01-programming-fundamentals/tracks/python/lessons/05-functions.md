# 05 (Python): Functions

Core lesson: [05: Functions](../../../lessons/05-functions.md)

## def and return

```python
def area(width: float, height: float) -> float:
    return width * height

print(area(4, 5))   # 20
```

A function without `return` returns `None`. A common bug is printing inside the function and then using its "result".

## Default and keyword arguments

```python
def greet(name: str, greeting: str = "Hello") -> str:
    return f"{greeting}, {name}!"

greet("Ana")                    # "Hello, Ana!"
greet("Ana", greeting="Halo")   # keyword argument: clear at the call site
```

⚠️ Never use a mutable default like `def f(items=[])`. The same list is shared across calls. Use `None` and create it inside.

## Scope

```python
count = 10

def reset():
    count = 0        # creates a NEW local variable. The outer one is unchanged.

reset()
print(count)         # 10
```

Avoid the `global` keyword. Pass values in and return results instead.

## Docstrings

A short docstring explains what a function does (and *why*, if it's not obvious):

```python
def to_fahrenheit(celsius: float) -> float:
    """Convert a temperature from Celsius to Fahrenheit."""
    return celsius * 9 / 5 + 32
```

## Pure vs. side effects

```python
def average(numbers: list[float]) -> float:        # pure
    return sum(numbers) / len(numbers) if numbers else 0.0

def print_report(numbers: list[float]) -> None:    # side effect: output
    print(f"Average: {average(numbers):.2f}")
```
