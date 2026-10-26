# 02 (JavaScript): Operators and expressions

Core lesson: [02: Operators and expressions](../../../lessons/02-operators-and-expressions.md)

## Arithmetic

```js
7 / 2;              // 3.5
Math.floor(7 / 2);  // 3   (integer division)
Math.trunc(-7 / 2); // -3  (towards zero)
7 % 2;              // 1
2 ** 10;            // 1024
```

## Strict equality: always use `===`

```js
0 == "";     // true  ⚠️ loose equality converts types
0 === "";    // false ✅
"5" === 5;   // false
```

Use `===` and `!==`. ESLint's recommended config warns otherwise.

## Logic

```js
age >= 18 && hasTicket;
day === "Sat" || day === "Sun";
!isClosed;
["Sat", "Sun"].includes(day); // membership
```

## Nullish helpers

```js
const name = input || "friend";   // falls back on ANY falsy value ("", 0, null)
const count = saved ?? 0;         // falls back only on null/undefined
user?.address?.city;              // optional chaining: undefined instead of a crash
```

## Assignment shortcuts

```js
total += price;
count++;   // also count += 1
```

## Strings

```js
"ab" + "cd";        // "abcd"
"-".repeat(10);     // "----------"
`Pages: ${5}`;      // "Pages: 5"
```

## Exercise hints

- Seconds → `1h 2m 5s`: combine `Math.floor` and `%`.
- Leap year: combine `%`, `&&`, `||`, with parentheses.
