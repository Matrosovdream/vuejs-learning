# Part 06 — Login page

## Goal
Build the login form that authenticates against the backend and redirects into the
dashboard.

## Concepts
- **Form handling**: `v-model` on email/password, `@submit.prevent` on the form.
- **Calling a store action** from a component; awaiting it.
- **Loading + error UI**: disable the button while submitting; show an error message
  on failure.
- **Programmatic navigation**: `useRouter()` → `router.push('/dashboard')` after
  success.
- **Redirect query**: if the user was bounced here by a guard, send them back to the
  page they wanted (`route.query.redirect`).

## What we'll build
- `views/LoginView.vue`: form bound to local refs, calls `auth.login()`, handles
  loading/error, redirects on success.

## Endpoints
- `POST /auth/login`.

## Checklist
- [ ] Valid credentials log in and land on the dashboard.
- [ ] Wrong credentials show an error, no redirect.
- [ ] Button is disabled while the request is in flight.

## Resources
- Programmatic navigation: https://router.vuejs.org/guide/essentials/navigation.html
