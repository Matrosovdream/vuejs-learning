# Part 09 — Products list

## Goal
Fetch and display the products in a table, with proper loading and error states.

## Concepts
- **Fetching on mount**: call the store/API in `onMounted` (or watch the route).
- **Async state pattern**: track `loading`, `error`, and `items` together.
- **Rendering a list**: `v-for` over rows with `:key="product.id"`.
- **Derived display**: format price/date; map `status` to a `.badge` class.
- **Reusable components**: extract a `components/DataTable.vue` and/or
  `components/StatusBadge.vue`.
- **Products store**: a Pinia store that caches the last fetched page.

## What we'll build
- `stores/products.js` with a `fetchProducts(params)` action.
- `views/ProductsView.vue` rendering a table with loading/error/empty states.
- `components/StatusBadge.vue` (prop-driven badge).

## Endpoints
- `GET /products`, `GET /categories`.

## Checklist
- [ ] Table shows products after load; spinner/skeleton while loading.
- [ ] Network error shows a friendly message, not a blank page.
- [ ] Empty result shows an "empty state".

## Resources
- Lifecycle (`onMounted`): https://vuejs.org/api/composition-api-lifecycle.html
- List rendering: https://vuejs.org/guide/essentials/list.html
