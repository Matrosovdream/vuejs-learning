# Part 03 — Router + Pinia wiring sanity check

## Goal
Understand how routing works and confirm Router + Pinia are wired, using two
placeholder pages.

## Concepts
- **SPA routing**: one HTML page; the router swaps which *component* renders based on
  the URL — no full page reload.
- **Route table**: an array of `{ path, name, component }` in `src/router/index.js`.
- **`<RouterView />`**: the outlet where the matched component is rendered.
- **`<RouterLink to="/x">`**: client-side navigation (replaces `<a href>`; no reload).
- **Lazy routes**: `component: () => import('...')` code-splits a view into its own
  chunk, loaded on demand.
- **Pinia** is registered in `main.js` with `createPinia()`; stores are defined with
  `defineStore` and used inside components/guards.

## What we'll build
- `views/LoginView.vue` and `views/DashboardView.vue` placeholders.
- Routes `/login` and `/dashboard` (plus a redirect from `/`).
- `<RouterLink>`s to navigate between them; confirm URL changes without reload.

## Checklist
- [ ] Navigating between `/login` and `/dashboard` swaps the view, no reload.
- [ ] I can explain what `<RouterView>` and `<RouterLink>` do.

## Resources
- Vue Router essentials: https://router.vuejs.org/guide/
- Pinia: https://pinia.vuejs.org/core-concepts/
