# Part 08 — Dashboard layout (sidebar + nested routes)

## Goal
Build the shell that wraps all dashboard pages: a sidebar menu, a header, and a
content area that swaps per sub-route.

## Concepts
- **Nested routes**: a parent route renders a layout containing its own
  `<RouterView />`; `children` routes render inside it.
- **Layout component**: `layouts/DashboardLayout.vue` with sidebar + header + outlet.
- **Active link styling**: `<RouterLink>` auto-adds `router-link-active` /
  `router-link-exact-active` classes you can style.
- **Slots** (optional): a layout can expose slots for header actions.
- **Components**: extract `components/SidebarNav.vue`, `components/AppHeader.vue`.

## What we'll build
- `layouts/DashboardLayout.vue` (sidebar nav links to Products/Orders/Overview,
  header with user name + logout, `<RouterView />` for children).
- Restructure routes: a parent `/` (or `/app`) with children
  `overview`, `products`, `orders`.

## Endpoints
- None directly (uses auth store for the user name + logout).

## Checklist
- [ ] Sidebar links switch the content area without reloading the layout.
- [ ] Active link is visually highlighted.
- [ ] Logout button clears session and returns to `/login`.

## Resources
- Nested routes: https://router.vuejs.org/guide/essentials/nested-routes.html
