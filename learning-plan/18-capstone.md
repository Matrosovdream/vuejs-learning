# 18 — Capstone Project

## Goal
Build a small app that exercises everything from steps 01–17. Aim for ~1–2 days of focused work.

## Project options (pick one)

### A. Personal Task Tracker
- Routes: `/`, `/tasks`, `/tasks/:id`, `/about`.
- Add/edit/delete/complete tasks. Filter by `all / active / done`.
- Persist to `localStorage` via a Pinia store.
- Form validation when creating a task.
- Deployed to a live URL.

### B. GitHub Repo Explorer
- Search GitHub users via the public API.
- Routes for a user list, a user detail with their repos, and a single repo page.
- Loading + error states throughout. Abort on navigation.
- A "favorites" Pinia store persisted to `localStorage`.

### C. Pomodoro Timer with Stats
- A timer component with start/pause/reset.
- Pinia store that records each completed session.
- A stats page with a list and totals (computed).
- Notifications on session end (`Notification` API).

## Requirements (any project)
- Vue 3 + Vite + Vue Router + Pinia.
- At least one custom composable.
- At least one form with validation.
- At least one real HTTP request (use a real API or `jsonplaceholder`).
- A handful of Vitest tests.
- Deployed and a `README.md` explaining how to run it.

## Checklist
- [ ] Project picked.
- [ ] App scaffolded.
- [ ] Core features working.
- [ ] Tests passing.
- [ ] Deployed.
- [ ] Written README.

## After this
You're ready for: TypeScript with Vue, Nuxt (SSR/SSG), advanced reactivity (`effectScope`, custom refs), animation (`<Transition>` / `<TransitionGroup>`), and integrating UI libraries (Vuetify, Naive UI, PrimeVue).
