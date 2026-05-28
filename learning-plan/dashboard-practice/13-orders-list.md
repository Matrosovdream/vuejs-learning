# Part 13 — Orders list

## Goal
Build the orders table, reusing the list/filter/pagination patterns from products,
with status and date-range filters.

## Concepts
- **Reuse**: the `DataTable`, `FilterBar`, `PaginationControls`, `StatusBadge`
  components should largely carry over — proof that componentizing paid off.
- **Date-range filter**: two date inputs → `dateFrom` / `dateTo` query params.
- **Status mapping**: the 5 order statuses → distinct badge colors.
- **Orders store**: mirror the products store shape.

## What we'll build
- `stores/orders.js` with `fetchOrders(params)`.
- `views/OrdersView.vue` with search + status select + date range + pagination.

## Endpoints
- `GET /orders?search=&status=&dateFrom=&dateTo=&sort=&page=&pageSize=`.

## Checklist
- [ ] Orders table loads with the shared components.
- [ ] Status + date-range filters work and combine.
- [ ] Pagination works as on products.

## Resources
- (Reuses concepts from parts 09–11.)
