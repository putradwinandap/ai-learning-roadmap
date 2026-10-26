# Level 03 quiz bank

See [ai/quiz-protocol.md](../../ai/quiz-protocol.md).

## 1. How the web works
- Describe what happens after you type a URL and press Enter.
- What does DNS do?

## 2. HTTP
- GET vs POST. Name one other method and its purpose.
- Meaning of 200, 201, 301, 400, 401, 403, 404, 500.
- *Predict:* what `fetch` does on a 404. (Hint: it does **not** reject.)

## 3. HTML & accessibility
- Why use `<button>` instead of a clickable `<div>`?
- What are landmarks? Name three.
- How does a screen reader user know what an input is for?

## 4. CSS
- Explain the box model. What does `box-sizing: border-box` change?
- Flexbox vs Grid: when to use each.
- How does specificity decide which rule wins?
- What is mobile-first?

## 5. DOM & events
- What is event delegation and why is it useful?
- `textContent` vs `innerHTML`: why does it matter for security?

## 6. Async JavaScript
- What is a promise? What does `await` do?
- *Spot the bug:* a `fetch` call without checking `response.ok` or catching errors.
- *Predict:* the order of console logs with `setTimeout(0)`, a resolved promise, and synchronous code.
- What is debouncing?

## 7. Browser security & storage
- What is the same-origin policy? What is CORS for?
- What is XSS? How do you prevent it?
- What should never be stored in `localStorage`?
