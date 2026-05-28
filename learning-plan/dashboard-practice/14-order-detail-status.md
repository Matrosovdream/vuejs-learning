# Part 14 — Order detail + status update

## Goal
Show a single order with its line items, and let an admin advance its status.

## Concepts
- **Detail fetch**: `GET /orders/:id` returns the order plus `items[]`.
- **Computed totals**: derive line totals and a grand total with `computed`.
- **Status workflow**: a `<select>` or buttons to change status; `PATCH` it and
  reflect the new status (optimistic or refetch).
- **Shared component**: reuse `StatusBadge`; maybe a small `components/Modal.vue`
  (with a slot) for the confirm.

## What we'll build
- `views/OrderDetailView.vue`: order header, items table, totals, status control.
- A `changeStatus(newStatus)` action → `PATCH /orders/:id/status`.

## Endpoints
- `GET /orders/:id`, `PATCH /orders/:id/status`.

## Checklist
- [ ] Order detail shows items and a correct computed total.
- [ ] Changing status persists and updates the badge.
- [ ] Invalid status transitions are handled gracefully.

## Resources
- Slots (for the modal): https://vuejs.org/guide/components/slots.html
