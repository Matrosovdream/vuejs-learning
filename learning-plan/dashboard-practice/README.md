# Dashboard Practice — Integrated Project

A bigger, hands-on practice project that ties together the concepts from the main
course (components, props/events, router, Pinia, forms, HTTP) into one real app:
an **e-commerce products & orders admin dashboard** with token-based auth.

- **Code lives at:** `/dashboard-practice/` (repo root) — the Vite app.
- **Plan & progress live here:** `learning-plan/dashboard-practice/`.
- **Backend contract:** [API.md](./API.md) — endpoints, params, response shapes
  (Stan builds the backend; the frontend is built against this spec).

## How we work on it

Code-along style, same as the main lessons: Claude gives **one focused block at a
time**, Stan types it into his editor, Claude explains how it works. Progress is
tracked in [PROGRESS.md](./PROGRESS.md) (this sub-project) and summarized in the
common `learning-plan/PROGRESS.md`.

## Stack

- Vue 3 + Vite (scaffolded with `npm create vue@latest`, Router + Pinia selected)
- Vue Router — auth-guarded routes, nested dashboard layout
- Pinia — `auth`, `products`, `orders` stores
- Native `fetch` — small API client wrapper (token header, 401 handling)
- Plain hand-written CSS (`src/assets/main.css`) — no UI library

## What it exercises

| Concept | Where it shows up |
|---|---|
| Components & composition | views, layout, shared components (table, filter bar, badge) |
| Props & events | passing data down to rows/cards, emitting actions up |
| Slots | reusable layout / table / modal wrappers |
| Vue Router | route table, `<RouterLink>`, params, nested routes, guards |
| Pinia | auth/session, cached lists, shared state |
| Forms & validation | login, product create/edit |
| HTTP | fetch wrapper, loading/error states, CRUD |
| Reactivity (computed/watch) | filters, search debounce, derived totals |

## Build parts

See [PROGRESS.md](./PROGRESS.md) for the part-by-part status table. High level:

1. Scaffold (Router + Pinia) → 2. Router/Pinia wiring → 3. API client →
4. Auth store → 5. Login page → 6. Route guards → 7. Dashboard layout →
8. Products list → 9. Filters/search → 10. Pagination → 11. Product CRUD →
12. Orders list → 13. Order detail/status → 14. Dashboard stats → 15. Polish.

## Resuming

When picking this back up: read [PROGRESS.md](./PROGRESS.md) for the current part,
then continue code-along from there.
