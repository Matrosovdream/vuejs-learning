# Part 16 — Polish

## Goal
Round off the app: logout flow, 404 page, consistent empty/error states, and small
UX touches.

## Concepts
- **Catch-all route**: `path: '/:pathMatch(.*)*'` → a `NotFoundView`.
- **Global logout**: button in the header → `auth.logout()` → redirect to `/login`.
- **Consistent states**: a shared pattern (or component) for loading / error / empty.
- **Auth-aware 401**: the API client's 401 handler logs the user out everywhere.
- **Nice-to-haves**: page titles per route, a toast/notification for save success,
  disabling actions during requests.

## What we'll build
- `views/NotFoundView.vue` + catch-all route.
- Polish passes over existing views (empty states, button disabling).
- Optional `components/Toast.vue` for success/error feedback.

## Endpoints
- None new.

## Checklist
- [ ] Unknown URLs show a 404 page with a link home.
- [ ] Logout works from anywhere and a 401 force-logs-out.
- [ ] Loading/empty/error states are consistent across lists.

## Resources
- Catch-all routes: https://router.vuejs.org/guide/essentials/dynamic-matching.html#Catch-all-404-Not-found-Route
