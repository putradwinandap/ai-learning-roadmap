# 04 (JavaScript): Loops

Core lesson: [04: Loops](../../../lessons/04-loops.md)

## for...of over a collection

```js
const titles = ["Dune", "Emma", "Ulysses"];
for (const title of titles) {
  console.log(title);
}
```

Need the index? Use `entries()`:

```js
for (const [index, title] of titles.entries()) {
  console.log(`${index + 1}. ${title}`);
}
```

⚠️ `for...in` iterates over **keys**, not values. Don't use it for arrays.

## Classic for (counting)

```js
for (let i = 1; i <= 5; i++) {
  console.log(i); // 1..5
}
```

## while

```js
let pagesLeft = 120;
while (pagesLeft > 0) {
  pagesLeft -= 30;
  console.log(`${pagesLeft} pages left`);
}
```

## Menu loop with break / continue

```js
import { createInterface } from "node:readline/promises";
import { stdin as input, stdout as output } from "node:process";

const rl = createInterface({ input, output });

while (true) {
  const choice = (await rl.question("1) hi  2) time  q) quit > ")).trim().toLowerCase();
  if (choice === "q") break;
  if (!choice) continue;
  if (choice === "1") {
    console.log("Hi!");
  } else if (choice === "2") {
    console.log(new Date().toLocaleTimeString());
  } else {
    console.log("Unknown option");
  }
}
rl.close();
```

## Accumulators

```js
const numbers = [4, 8, 15, 16, 23, 42];

let total = 0;
let largest = numbers[0];
for (const n of numbers) {
  total += n;
  if (n > largest) largest = n;
}

// Built-ins. Know both ways:
numbers.reduce((sum, n) => sum + n, 0);
Math.max(...numbers);
```
