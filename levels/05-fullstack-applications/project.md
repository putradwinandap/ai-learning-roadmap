# Level 05 project: Gather Web

Turn your Level 04 API into a **complete, deployed product**: a web frontend where people discover events, sign up, RSVP and manage their own events.

**Location:** `learner/level-05/project/`, or a separate repo linked in `progress.md` (`project_location`). You may extend your Level 04 API in place.

## Requirements

### Must

| ID | Requirement |
|---|---|
| L05-M1 | Frontend built with a component framework and **TypeScript** (strict mode). |
| L05-M2 | Pages: event list with search/filter and pagination, event detail, sign up, log in, "my RSVPs", "my events", create/edit event. |
| L05-M3 | **Auth flow** works end to end. Protected routes redirect to login. Logout works. Tokens are not stored in `localStorage` (use secure cookies, or document an equally safe choice). |
| L05-M4 | **Server state** handled with caching and invalidation (after RSVP, lists update without a full reload). |
| L05-M5 | **Forms** with client-side validation that mirrors server validation, and server errors shown next to the right fields. |
| L05-M6 | Loading, empty and error states on every data view. |
| L05-M7 | Responsive and accessible (keyboard, labels, focus management on route changes, Lighthouse a11y ≥ 90). |
| L05-M8 | **Deployed**: frontend, backend and database all live on public URLs with HTTPS. CORS configured for the real origin only. |
| L05-M9 | **Tests**: component tests for key components, and at least **3 end-to-end tests** (sign up → create event → RSVP). |
| L05-M10 | README: architecture overview (diagram welcome), local setup for both apps, environment variables, deployment notes and live URLs. |

### Should

| ID | Requirement |
|---|---|
| L05-S1 | **Optimistic UI** for RSVP/cancel, with rollback on error. |
| L05-S2 | Shared validation schema or generated API types between backend and frontend (or an OpenAPI-generated client). |
| L05-S3 | Code splitting per route. Lighthouse performance ≥ 80. |
| L05-S4 | Separate environments (local, production) with documented config. |

### Stretch

| ID | Requirement |
|---|---|
| L05-X1 | Server-side rendering or static generation for public event pages (SEO). |
| L05-X2 | Image upload for event covers (object storage). |
| L05-X3 | Real-time attendee count (WebSocket or SSE). |
| L05-X4 | Internationalisation (two UI languages). |

## Acceptance scenarios

1. Visit the live URL on a phone → sign up, create an event, log out, log in as another user, RSVP.
2. Refresh on a protected page → still logged in (or cleanly redirected).
3. Submit an invalid form → field errors, from the client and from the server.
4. Kill the network while RSVPing → a clear error, and the UI state is consistent afterwards.
5. The E2E test suite passes locally with the README command.
