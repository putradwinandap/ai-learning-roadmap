# 08 (JavaScript): Files and persistence

Core lesson: [08: Files and persistence](../../../lessons/08-files-and-persistence.md)

## Paths relative to the code file

```js
import path from "node:path";

// Folder that contains THIS .js file (Node 20.11+), independent of where you run from
const NOTES_FILE = path.join(import.meta.dirname, "..", "notes.json");
```

## Reading and writing text

For a small CLI, the synchronous API is simplest:

```js
import { existsSync, readFileSync, writeFileSync, appendFileSync } from "node:fs";

writeFileSync("hello.txt", "hello\n", "utf8");     // create or overwrite
appendFileSync("hello.txt", "more\n", "utf8");
const content = readFileSync("hello.txt", "utf8");
existsSync("hello.txt");                            // true
```

There are also promise-based versions in `node:fs/promises` (`await readFile(...)`), which you'll use in servers (Level 04).

## JSON

```js
const notes = [{ id: 1, text: "buy milk" }];

writeFileSync(NOTES_FILE, JSON.stringify(notes, null, 2), "utf8");  // save, pretty-printed
const loaded = JSON.parse(readFileSync(NOTES_FILE, "utf8"));       // load
```

## First run and corrupt files

```js
export function loadNotes(file) {
  if (!existsSync(file)) return [];
  const text = readFileSync(file, "utf8");
  try {
    return JSON.parse(text);
  } catch (error) {
    if (error instanceof SyntaxError) {
      throw new Error(`${file} is not valid JSON. Fix or move it, then try again.`);
    }
    throw error;
  }
}
```

The function signals the problem, and the caller decides how to tell the user (lesson 09).

## Dates

```js
const today = new Date().toISOString().slice(0, 10); // "2026-10-26" (UTC!)
```

⚠️ `toISOString()` uses **UTC**, so near midnight it can be "yesterday" or "tomorrow" for you. A local version:

```js
const d = new Date();
const localToday = [
  d.getFullYear(),
  String(d.getMonth() + 1).padStart(2, "0"), // months are 0-based!
  String(d.getDate()).padStart(2, "0"),
].join("-");
```

Validating `YYYY-MM-DD` is tricky: `new Date("2026-02-30")` doesn't fail, it rolls over to March. A robust check: match the pattern with a regex, build the date, and verify it converts back to the **same** string.

## Next ID

```js
const nextId = Math.max(0, ...notes.map((n) => n.id)) + 1;
```
