# Part 05 — Auth store (Pinia)

## Goal
Hold the logged-in session (token + user) in a Pinia store that any component or
route guard can read.

## Concepts
- **`defineStore('auth', () => { ... })`** — setup-style store: `ref`s are state,
  `computed`s are getters, functions are actions.
- **State**: `token`, `user`.
- **Getter**: `isAuthenticated` = `!!token`.
- **Actions**: `login(email, password)`, `fetchMe()`, `logout()`.
- **Persistence**: mirror the token to `localStorage` so a page refresh keeps you
  logged in; read it back on store init.

## What we'll build
- `src/stores/auth.js`:
  - `login()` → `POST /auth/login`, store `token` + `user`, persist token.
  - `fetchMe()` → `GET /auth/me` to restore `user` from a saved token.
  - `logout()` → clear token/user + localStorage.

## Endpoints
- `POST /auth/login`, `GET /auth/me`, `POST /auth/logout` (optional).

## Checklist
- [ ] `isAuthenticated` reflects login state.
- [ ] Token survives a page refresh (localStorage).
- [ ] `logout()` fully clears session.

## Resources
- Pinia setup stores: https://pinia.vuejs.org/core-concepts/#Setup-Stores
