# 06: Collections

> Syntax: [Python](../tracks/python/lessons/06-collections.md) · [JavaScript](../tracks/javascript/lessons/06-collections.md)

## Why this matters

One expense is a few variables. A hundred expenses need **collections**: structures that hold many values. Choosing the right collection makes code simple. Choosing the wrong one makes it painful.

## Key ideas

### Lists / arrays: ordered sequences

```text
amounts ← [12.5, 3.0, 40.0]
amounts[0]            # 12.5: indexes start at 0
length(amounts)       # 3
append 7.25 to amounts
remove item at index 1
```

Use a list when **order matters** or you'll go through all items. Accessing an index that doesn't exist (`amounts[10]`) is an error or `undefined`, depending on the language.

### Dictionaries / maps / objects: key → value

```text
expense ← {
    "amount": 12.5,
    "category": "food",
    "note": "lunch"
}
expense["category"]   # "food"
expense["paid"] ← true
```

Use a dictionary when you look things up **by name or key**. Keys are unique.

### Combining them: records

The most common data shape in real programs is a **list of records**:

```text
expenses ← [
    {"id": 1, "amount": 12.5, "category": "food"},
    {"id": 2, "amount": 40.0, "category": "transport"},
]
```

This maps directly to JSON (lesson 08), database rows (Level 04) and API responses (Level 03).

### Common operations

| Task | Pattern |
|---|---|
| Go through every item | for-each loop |
| Keep only some items (**filter**) | new list + `if` inside a loop, or your language's filter |
| Transform each item (**map**) | new list of changed values |
| Combine into one value (**reduce**) | accumulator (sum, count, max) |
| Group by a key | dictionary of key → total or key → list |

Grouping example, totals per category:

```text
totals ← {}
for each e in expenses:
    if e.category not in totals: totals[e.category] ← 0
    totals[e.category] ← totals[e.category] + e.amount
```

### Mutation and references

In most languages, assigning a list or dictionary to another variable does **not** copy it. Both names refer to the **same** collection:

```text
a ← [1, 2]
b ← a
append 3 to b
print a        # [1, 2, 3]!
```

Copy explicitly when you need an independent version.

### Other collections (preview)

**Sets** (unique values, fast membership checks) and **tuples** (fixed, immutable groups) exist in many languages. Level 02 goes deeper into data structures and their costs.

## Exercise

1. Build a list of at least 5 records (e.g. books with title, author, year).
2. Print all books published after 2000 (filter).
3. Print a list of just the titles, in uppercase (map).
4. Count books per author (group with a dictionary).
5. Find the oldest book without using a built-in sort.

## Check your understanding

1. When do you choose a list, and when a dictionary?
2. What's the index of the last item in a list of length `n`?
3. Explain why changing `b` also changed `a` in the example above.
4. Describe how to compute totals per category.
