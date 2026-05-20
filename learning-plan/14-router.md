# 14 — Vue Router

## Goals
- Add client-side routing to a Vue app.
- Use `<router-link>` for navigation and `<router-view>` to render the matched route.
- Read route params and use programmatic navigation.

## Concepts
- **SPA routing** — URL changes without a full page reload; Vue Router swaps the matched component.
- **Define routes**:
  ```js
  import { createRouter, createWebHistory } from 'vue-router'
  const routes = [
    { path: '/', component: Home },
    { path: '/users/:id', component: UserDetail, name: 'user' }
  ]
  const router = createRouter({ history: createWebHistory(), routes })
  ```
- **`<router-link to="/about">About</router-link>`** — declarative navigation.
- **`<router-view />`** — placeholder for the matched component.
- **`useRoute()`** — read `params`, `query`, etc. **`useRouter()`** — programmatic `.push()`, `.replace()`, `.back()`.
- **Navigation guards** — `beforeEach`, route-level `beforeEnter`, for auth/redirects.
- **Lazy loading** — `component: () => import('./Page.vue')` keeps the initial bundle small.

## Exercises
1. Add Vue Router to a new project (`npm create vue@latest` and pick router this time, or `npm i vue-router`).
2. Build pages `Home`, `About`, `Users` (list), `UserDetail` (by `:id`).
3. From the user list, link to each detail page with `<router-link :to="{ name: 'user', params: { id: u.id } }">`.
4. In `UserDetail`, read the param with `useRoute().params.id` and fetch / display it.
5. Add a "Go back" button using `useRouter().back()`.

## Checklist
- [ ] I can define routes and render them with `<router-view />`.
- [ ] I can read `params` and navigate programmatically.
- [ ] I know about lazy loading and at least one navigation guard.

## Resources
- Vue Router: https://router.vuejs.org/
