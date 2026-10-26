# 07 (JavaScript): Strings and input/output

Core lesson: [07: Strings and input/output](../../../lessons/07-strings-and-input-output.md)

## Common methods

```js
const s = "  Ada Lovelace  ";
s.trim();                     // "Ada Lovelace"
s.trim().toLowerCase();       // "ada lovelace"
"a,b,c".split(",");           // ["a", "b", "c"]
["x", "y"].join(" ");         // "x y"
"report.pdf".endsWith(".pdf");
"lunch with team".includes("team");
"2026-10-26".slice(0, 7);     // "2026-10"
```

Title case has no built-in, so combine:

```js
const titleCase = (text) =>
  text.split(" ").map((w) => w.charAt(0).toUpperCase() + w.slice(1)).join(" ");
```

## Parsing a line

```js
const line = "3 x coffee @ 4.50";
const parts = line.split(/\s+/);      // split on any whitespace
if (parts.length !== 5) {
  console.log("Expected: <qty> x <item> @ <price>");
} else {
  const [qty, , item, , price] = parts;  // destructuring, skipping "x" and "@"
  console.log(`${item}: ${(Number(qty) * Number(price)).toFixed(2)}`);
}
```

## Padding and alignment

```js
"tea".padEnd(10);          // "tea       "
"42".padStart(6);          // "    42"
(7).toFixed(2).padStart(8) // "    7.00"
```

A small table:

```js
const rows = [["Dune", 1965, 9.99], ["Emma", 1815, 4.5]];
console.log("Title".padEnd(12) + "Year".padStart(6) + "Price".padStart(8));
for (const [title, year, price] of rows) {
  console.log(title.padEnd(12) + String(year).padStart(6) + price.toFixed(2).padStart(8));
}
```

`console.table(rows)` is handy for debugging, but build your own table for the project.

## Command-line arguments

```js
import { argv } from "node:process";

console.log(argv.slice(2)); // node src/main.js add 12.5 → ["add", "12.5"]
```

`npm start -- add 12.5` passes arguments through npm. For options and help text, Node has a built-in `util.parseArgs`.
