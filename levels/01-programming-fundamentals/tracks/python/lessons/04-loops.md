# 04 (Python): Loops

Core lesson: [04: Loops](../../../lessons/04-loops.md)

## for over a range or collection

```python
for i in range(1, 6):      # 1, 2, 3, 4, 5 (end is exclusive!)
    print(i)

for title in ["Dune", "Emma", "Ulysses"]:
    print(title)
```

Need the position too? Use `enumerate`, not `range(len(...))`:

```python
for position, title in enumerate(titles, start=1):
    print(f"{position}. {title}")
```

## while

```python
pages_left = 120
while pages_left > 0:
    pages_left -= 30
    print(f"{pages_left} pages left")
```

## Menu loop with break / continue

```python
while True:
    choice = input("1) hi  2) time  q) quit > ").strip().lower()
    if choice == "q":
        break
    if not choice:
        continue
    if choice == "1":
        print("Hi!")
    elif choice == "2":
        from datetime import datetime
        print(datetime.now().strftime("%H:%M"))
    else:
        print("Unknown option")
```

(Normally imports go at the top of the file. It's inside here only to keep the snippet short.)

## Accumulators

```python
numbers = [4, 8, 15, 16, 23, 42]

total = 0
largest = numbers[0]
for n in numbers:
    total += n
    if n > largest:
        largest = n

# Python built-ins do the same. Know both ways:
sum(numbers), max(numbers), len(numbers)
```
