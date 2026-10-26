# Level 03 project: Explorer

Build an **interactive single-page web app** on top of a public API of your choice (countries, books, weather, recipes, space, ...). Use plain HTML, CSS and JavaScript, **no frameworks**.

**Location:** `learner/level-03/project/` + a public deployment URL.

## Requirements

### Must

| ID | Requirement |
|---|---|
| L03-M1 | Fetches data from a **public HTTP API** with `fetch` and async/await. |
| L03-M2 | **Search or filter** interaction that updates results without reloading the page. |
| L03-M3 | A **detail view** for one item (modal, panel or separate section). |
| L03-M4 | Visible **loading, empty and error states**. Network failures and API errors are handled gracefully. |
| L03-M5 | **Semantic HTML**: landmarks, heading hierarchy, labelled form controls, buttons for actions and links for navigation. |
| L03-M6 | **Responsive** layout using Flexbox and/or Grid that works from 360 px to desktop widths. |
| L03-M7 | **Accessible**: fully usable with the keyboard, visible focus, sufficient contrast, images with alt text. Lighthouse accessibility score ≥ 90. |
| L03-M8 | **Safe rendering**: user input and API text are inserted with `textContent` or created elements, never raw `innerHTML`. |
| L03-M9 | **Deployed** publicly (GitHub Pages, Netlify, ...). The URL is in the README. |
| L03-M10 | README: what the app does, which API, how to run it locally, the deployment URL, and known limitations. |

### Should

| ID | Requirement |
|---|---|
| L03-S1 | **Favourites** saved in `localStorage` and restored on reload. |
| L03-S2 | **Debounced** search input (no request on every keystroke). |
| L03-S3 | JavaScript split into **ES modules** (API, state, rendering). |
| L03-S4 | State reflected in the **URL** (query string or hash), so a search can be shared or bookmarked. |
| L03-S5 | Lighthouse performance ≥ 80. |

### Stretch

| ID | Requirement |
|---|---|
| L03-X1 | Dark/light theme following `prefers-color-scheme`, with a toggle. |
| L03-X2 | Pagination or infinite scroll. |
| L03-X3 | Caching API responses in memory to avoid repeated requests. |

## Acceptance scenarios

1. Open the deployed URL on a phone-sized viewport → layout works, no horizontal scroll.
2. Use the whole app with only the keyboard (Tab, Enter, Esc).
3. Search for something that returns nothing → friendly empty state.
4. Turn on offline mode in DevTools and search → friendly error, the app still works afterwards.
5. Search for `<img src=x onerror=alert(1)>` → rendered as text, no script runs.
6. Lighthouse accessibility ≥ 90.

## Rules

No UI frameworks or component libraries (React, Vue, Bootstrap, Tailwind, ...). The point is learning the platform. Small dev tools (a local server, Prettier, ESLint) are fine.
