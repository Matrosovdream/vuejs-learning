# Dashboard Practice — Progress

> Part-by-part tracker for the dashboard project. Code-along style.
> The common `learning-plan/PROGRESS.md` links here.

## Current part

**Queued** — this side project starts *after* the main 18-step course is finished.
First part to do when we begin: **01 — Scaffold** (`npm create vue@latest dashboard-practice`, Router + Pinia).

## Status by part

| #  | Part                                             | Status      | Notes |
|----|--------------------------------------------------|-------------|-------|
| 01 | [Scaffold via create-vue (Router + Pinia)](./01-scaffold.md) | not started | Stan runs the commands himself (queued) |
| 02 | [Strip demo content + add simple CSS](./02-cleanup-and-css.md) | not started | remove HelloWorld/demo, drop in main.css |
| 03 | [Router + Pinia wiring sanity check](./03-router-pinia-wiring.md) | not started | routes, `<RouterView>`, `<RouterLink>` |
| 04 | [API client (`fetch` wrapper, token, 401)](./04-api-client.md) | not started | |
| 05 | [Auth store (Pinia: login, token, user)](./05-auth-store.md) | not started | |
| 06 | [Login page (form, calls store, redirect)](./06-login-page.md) | not started | |
| 07 | [Route guards (protect dashboard, restore)](./07-route-guards.md) | not started | |
| 08 | [Dashboard layout (sidebar + nested routes)](./08-dashboard-layout.md) | not started | nested routes |
| 09 | [Products list (fetch, table, states)](./09-products-list.md) | not started | |
| 10 | [Filters + search (query params, debounce)](./10-filters-search.md) | not started | |
| 11 | [Pagination](./11-pagination.md)                 | not started | |
| 12 | [Product detail + create/edit (CRUD)](./12-product-crud.md) | not started | route params, POST/PUT/DELETE |
| 13 | [Orders list (status filter, date range)](./13-orders-list.md) | not started | |
| 14 | [Order detail + status update](./14-order-detail-status.md) | not started | PATCH |
| 15 | [Dashboard landing (stats cards)](./15-dashboard-stats.md) | not started | GET /stats |
| 16 | [Polish (logout, 404, empty states)](./16-polish.md) | not started | |

**Status legend:** `not started` · `in progress` · `done`

## Log

- 2026-05-28 — project kicked off: decided on e-commerce products & orders admin, new `dashboard-practice/` folder at repo root, real token auth. Wrote API spec ([API.md](./API.md)) and this plan. Stan is scaffolding the Vite app from scratch with `npm create vue@latest` (Router + Pinia). Next: strip demo content, add CSS, start wiring.
