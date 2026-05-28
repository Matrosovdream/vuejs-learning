# Part 12 — Product detail + create/edit (CRUD)

## Goal
View a single product and create / edit / delete products through a form.

## Concepts
- **Route params**: `/products/:id` → read with `useRoute().params.id`; `:id` of
  `new` (or a separate `/products/new` route) for create mode.
- **One form, two modes**: same component handles create (empty) and edit (prefilled).
- **Form state**: local reactive copy of the product so editing doesn't mutate the
  list until saved.
- **Validation**: required fields, price/stock numeric; show field errors (incl.
  `422` errors from the backend).
- **POST vs PUT vs DELETE**: create, update, remove; navigate back to the list after.

## What we'll build
- `views/ProductFormView.vue` (create + edit).
- `views/ProductDetailView.vue` (read-only view) or fold detail into the form.
- Delete button with a confirm step.

## Endpoints
- `GET /products/:id`, `POST /products`, `PUT /products/:id`, `DELETE /products/:id`.

## Checklist
- [ ] Create adds a product and returns to the list.
- [ ] Edit prefills and saves changes.
- [ ] Validation blocks bad input and shows backend `422` errors.
- [ ] Delete asks for confirmation.

## Resources
- Dynamic route matching: https://router.vuejs.org/guide/essentials/dynamic-matching.html
- Forms: https://vuejs.org/guide/essentials/forms.html
