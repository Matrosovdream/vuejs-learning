# Part 07 — Route guards (protect the dashboard)

## Goal
Stop unauthenticated users from reaching dashboard routes, and restore the session
on a fresh page load.

## Concepts
- **Navigation guard**: `router.beforeEach((to, from) => ...)` runs before each
  navigation; return `true`, a route location to redirect, or `false`.
- **Route meta**: mark protected routes with `meta: { requiresAuth: true }`.
- **Session restore**: on app start, if a token exists but `user` doesn't, call
  `fetchMe()` before deciding.
- **Redirect-back pattern**: when blocking, push `/login?redirect=<intended path>`.

## What we'll build
- `meta: { requiresAuth: true }` on dashboard routes.
- A global `beforeEach` guard in `src/router/index.js` using the auth store.
- Bounce logged-in users away from `/login`.

## Endpoints
- `GET /auth/me` (session restore).

## Checklist
- [ ] Visiting `/dashboard` while logged out redirects to `/login`.
- [ ] After login I'm sent to the page I originally wanted.
- [ ] Refreshing the page while logged in keeps me in.

## Resources
- Navigation guards: https://router.vuejs.org/guide/advanced/navigation-guards.html
- Route meta: https://router.vuejs.org/guide/advanced/meta.html
