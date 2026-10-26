# Level 03 rubric

Scale: 0 missing · 1 attempted but broken · 2 partial · **3 meets** · 4 exceeds. See [ai/review-protocol.md](../../ai/review-protocol.md).

| ID | Criterion | 3 = meets | 4 = exceeds | Typical 1–2 signs |
|---|---|---|---|---|
| L03-R1 | **Functionality** | All Must features work on the deployed site. All acceptance scenarios pass. | Most Should items done. Smooth, polished interactions. | Broken search, missing detail view, deployed site differs from the code. |
| L03-R2 | **HTTP & async handling** | Correct async/await use. HTTP status checked (`response.ok`). Loading, empty and error states. No unhandled promise rejections. | Debouncing, request cancellation (`AbortController`) or caching. Race conditions between requests handled. | Assumes every request succeeds, spinner never stops, errors only in the console. |
| L03-R3 | **HTML semantics & accessibility** | Landmarks, headings, labels, keyboard support, visible focus, alt text. Lighthouse a11y ≥ 90. | Tested with a screen reader. Focus managed in the modal. `aria-live` announcements for results. | `div` buttons, missing labels, keyboard traps, no focus style. |
| L03-R4 | **CSS & responsive design** | Clean layout with Flexbox/Grid, mobile-first, consistent spacing and typography, works 360 px → desktop. | CSS custom properties for a design system. Thoughtful visual hierarchy. Respects reduced-motion. | Fixed widths, overflow on mobile, specificity wars, `!important` everywhere. |
| L03-R5 | **JavaScript structure** | Separation of API, state and rendering. Event delegation where sensible. No global mess. | ES modules. A single source of truth for state. Render functions are pure-ish. | One huge script, state scattered in the DOM, duplicated rendering code. |
| L03-R6 | **Security** | No user or API data inserted via `innerHTML`. No secrets committed. | Content Security Policy considered. API key handling explained if one is used. | XSS possible, API keys in the repo. |
| L03-R7 | **Documentation & deployment** | README complete. Public URL works. Incremental commits. | Screenshots, Lighthouse scores and design notes in the README. | No URL, or a broken deployment. Missing run instructions. |
