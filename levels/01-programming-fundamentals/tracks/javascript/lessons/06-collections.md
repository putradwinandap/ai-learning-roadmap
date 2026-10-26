# 06 (JavaScript): Collections

Core lesson: [06: Collections](../../../lessons/06-collections.md)

## Arrays

```js
const titles = ["Dune", "Emma"];
titles.push("Ulysses");
titles[0];               // "Dune"
titles.at(-1);           // "Ulysses"
titles.length;           // 3
titles.splice(1, 1);     // removes "Emma" (mutates)
titles.includes("Dune"); // true
titles[10];              // undefined, no error!
```

`const` arrays can still be **changed**. `const` only prevents reassigning the variable.

## Objects (key → value)

```js
const book = { title: "Dune", author: "Herbert", year: 1965 };
book.title;               // "Dune"
book["author"];           // "Herbert"
book.isbn;                // undefined
book.isbn ?? "n/a";       // "n/a"
book.rating = 5;          // add or update
for (const [key, value] of Object.entries(book)) {
  console.log(key, value);
}
```

For dynamic keys with lots of adds and removes, there's also `Map`. Plain objects are fine at this level.

## An array of records

```js
const books = [
  { id: 1, title: "Dune", author: "Herbert", year: 1965 },
  { id: 2, title: "Neuromancer", author: "Gibson", year: 1984 },
];
```

## filter, map, find, reduce

```js
const recent = books.filter((b) => b.year > 1980);
const titlesUpper = books.map((b) => b.title.toUpperCase());
const dune = books.find((b) => b.id === 1);              // undefined if none
const withoutDune = books.filter((b) => b.id !== 1);     // "delete" without mutating
```

## Grouping

```js
const perAuthor = {};
for (const b of books) {
  perAuthor[b.author] = (perAuthor[b.author] ?? 0) + 1;
}
```

## Sorting

```js
const byYear = [...books].sort((a, b) => a.year - b.year); // copy first: sort() mutates!
```

## Aliasing and copying

```js
const a = [1, 2];
const b = a;        // same array!
const c = [...a];   // shallow copy
const copy = structuredClone(books); // deep copy
```

## Sets

```js
const categories = new Set(["food", "fun", "food"]); // {"food", "fun"}
categories.has("fun"); // true
```
