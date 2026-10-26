# 01 (JavaScript): Values, variables and types

Core lesson: [01: Values, variables and types](../../../lessons/01-values-variables-and-types.md)

## Types

```js
const count = 42;          // number (JS has one number type for ints and decimals)
const price = 12.5;        // number
const title = "Dune";      // string
const inStock = true;      // boolean
let discount = null;       // null: intentionally empty
let rating;                // undefined: not assigned yet

console.log(typeof price); // "number"
```

## const vs let

```js
const MAX_ITEMS = 50;  // can't be reassigned
let pagesRead = 0;     // will change
pagesRead = 30;
```

Default to `const`. Never use `var`, which has confusing scoping rules.

## Naming

`camelCase` for variables and functions, `UPPER_SNAKE_CASE` for true constants, `PascalCase` for classes (later).

## Conversion

```js
Number("42");        // 42
Number("12.5");      // 12.5
Number("");          // 0   ⚠️ surprising
Number("abc");       // NaN ("Not a Number")
Number.parseFloat("12.5kg"); // 12.5 ⚠️ silently ignores the rest
String(42);          // "42"
```

`NaN` is a number value that means "invalid number". Check it with `Number.isNaN(x)`, because `x === NaN` is always false. For validating input, `Number(text)` plus a check for empty strings is stricter than `parseFloat`.

## Implicit conversion: be careful

```js
"5" + 1;   // "51" (string concatenation!)
"5" - 1;   // 4    (numeric subtraction)
```

Convert explicitly. Don't rely on JavaScript guessing.

## Floats and rounding

```js
0.1 + 0.2;                    // 0.30000000000000004
(0.1 + 0.2).toFixed(2);       // "0.30" (a string, for display)
Math.round(12.345 * 100);     // 1235: store money as integer cents
```

Either store cents as integers, or keep numbers and always use `.toFixed(2)` when displaying. Be consistent.
