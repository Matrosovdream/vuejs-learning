# Part 11 — Pagination

## Goal
Page through large result sets using the backend's `page`/`pageSize` + `total`.

## Concepts
- **Server-side pagination**: the API returns `{ items, total, page, pageSize }`;
  the UI sends `page`/`pageSize` and renders page controls.
- **Derived page count**: `computed(() => Math.ceil(total / pageSize))`.
- **Resetting page**: when filters change, jump back to page 1.
- **Reusable component**: `components/PaginationControls.vue` with prev/next +
  page numbers, emitting `update:page`.

## What we'll build
- `PaginationControls.vue` (props: `page`, `pageSize`, `total`; emits page change).
- Wire it into `ProductsView` so changing pages refetches.
- Keep `page` in the URL query alongside the filters.

## Endpoints
- `GET /products?page=&pageSize=` (envelope with `total`).

## Checklist
- [ ] Prev/next and page numbers work and disable at the ends.
- [ ] Changing a filter resets to page 1.
- [ ] Page is reflected in the URL.

## Resources
- Computed: https://vuejs.org/guide/essentials/computed.html
