# Part 15 — Dashboard landing (stats cards)

## Goal
Build the overview page shown after login: summary cards (products, orders, revenue,
pending) fed by the stats endpoint.

## Concepts
- **Presentational component**: `components/StatCard.vue` (props: label, value, maybe
  an icon/trend) — pure props in, no logic.
- **Number/currency formatting**: `Intl.NumberFormat` in a computed or helper.
- **Grid layout**: the `.grid` / `.grid-4` classes from our CSS.
- **Loading skeletons** for the cards.

## What we'll build
- `views/OverviewView.vue` fetching `GET /stats`.
- `StatCard.vue` reused 4×.

## Endpoints
- `GET /stats`.

## Checklist
- [ ] Four cards render with formatted values.
- [ ] Loading + error states handled.
- [ ] `StatCard` is purely prop-driven (no fetching inside).

## Resources
- Props: https://vuejs.org/guide/components/props.html
- Intl.NumberFormat: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat
