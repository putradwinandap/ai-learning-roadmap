# 06 (Python): Collections

Core lesson: [06: Collections](../../../lessons/06-collections.md)

## Lists

```python
titles = ["Dune", "Emma"]
titles.append("Ulysses")
titles[0]          # "Dune"
titles[-1]         # "Ulysses" (negative index counts from the end)
len(titles)        # 3
titles.pop(1)      # removes and returns "Emma"
"Dune" in titles   # True
```

## Dictionaries

```python
book = {"title": "Dune", "author": "Herbert", "year": 1965}
book["title"]               # "Dune"
book.get("isbn")            # None (no KeyError)
book.get("isbn", "n/a")     # "n/a"
book["rating"] = 5          # add or update
for key, value in book.items():
    print(key, value)
```

## A list of records

```python
books = [
    {"id": 1, "title": "Dune", "author": "Herbert", "year": 1965},
    {"id": 2, "title": "Neuromancer", "author": "Gibson", "year": 1984},
]
```

## Comprehensions: map and filter in one line

```python
recent = [b for b in books if b["year"] > 1980]          # filter
titles = [b["title"].upper() for b in books]             # map
```

Use them when they stay readable. Otherwise, a normal loop is fine.

## Grouping

```python
per_author: dict[str, int] = {}
for b in books:
    per_author[b["author"]] = per_author.get(b["author"], 0) + 1
```

## Sorting

```python
by_year = sorted(books, key=lambda b: b["year"])   # returns a new list
```

## Aliasing and copying

```python
a = [1, 2]
b = a          # same list!
c = a.copy()   # independent (shallow) copy
```

## Other built-ins

- `set`: unique values, `{"food", "fun"}`
- `tuple`: immutable group, `(lat, lon)`
