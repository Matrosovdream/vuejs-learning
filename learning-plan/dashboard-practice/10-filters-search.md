# Part 10 — Filters + search

## Goal
Filter the products list by search text, category, and status — driven through the
backend query params and reflected in the URL.

## Concepts
- **Controlled filters**: `v-model` on a search box + `<select>`s for category/status.
- **Debounce**: wait ~300ms after typing stops before fetching (from step 06 of the
  main course).
- **Watchers**: `watch` the filter state and refetch when it changes.
- **URL as state**: push filters into the route query (`router.push({ query })`) so
  the view is shareable/back-button friendly; read them back on load.
- **Component**: extract `components/FilterBar.vue` that emits filter changes (or
  uses `v-model` with `defineModel`).

## What we'll build
- A `FilterBar` with search + category + status controls.
- Watch filters → debounce → call `fetchProducts(params)`.
- Sync filters to the URL query.

## Endpoints
- `GET /products?search=&categoryId=&status=&sort=`, `GET /categories`.

## Checklist
- [ ] Typing filters the list after a short debounce, not every keystroke.
- [ ] Category/status selects filter immediately.
- [ ] Filters appear in the URL and survive a refresh.

## Resources
- Watchers: https://vuejs.org/guide/essentials/watchers.html
- Component events / `defineModel`: https://vuejs.org/guide/components/v-model.html
