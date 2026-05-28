# Progress

> Update this file as you finish each step. Claude will read it to know where to pick up.

## Current step

**→ 07 — Methods & Event Handling** (in progress — exercises 1 & 2 done: task-list form with `@submit.prevent="addTask"`, per-row `@click="removeTask(task.id)"` passing args. Next: accessing `$event` while passing args, `@keyup.enter` (ex 3), `@click.stop` nested (ex 4))

## Status by step

| #  | Step                             | Status      | Notes |
|----|----------------------------------|-------------|-------|
| 01 | Introduction to Vue.js           | done        |       |
| 02 | Environment Setup                | done        | scaffolded as `vue-project/` at repo root (minimal preset, no ESLint/Prettier) |
| 03 | First Vue App & Template Syntax  | done        |       |
| 04 | Reactivity Fundamentals          | done        | ref vs reactive, .value rule, Proxy mental model, destructuring footgun + toRefs |
| 05 | Directives                       | done        | v-if/v-show, v-for + :key, v-model, modifiers (.trim/.number/.prevent) |
| 06 | Computed Properties & Watchers   | done        | computed (cached/derived), watch (lazy, oldVal, debounce), watchEffect (eager, auto-deps) |
| 07 | Methods & Event Handling         | in progress |       |
| 08 | Class & Style Bindings           | not started |       |
| 09 | Components Basics                | not started |       |
| 10 | Props & Events                   | not started |       |
| 11 | Slots                            | not started |       |
| 12 | Lifecycle Hooks                  | not started |       |
| 13 | Composition API Deep Dive        | not started |       |
| 14 | Vue Router                       | not started |       |
| 15 | State Management with Pinia      | not started |       |
| 16 | Forms, Validation & HTTP         | not started |       |
| 17 | Build, Deploy & Testing Basics   | not started |       |
| 18 | Capstone Project                 | not started |       |

**Status legend:** `not started` · `in progress` · `done`

## Side project — Dashboard Practice

A bigger integrated build (e-commerce products & orders admin dashboard with token
auth) that ties together components, router, Pinia, forms, and HTTP. Runs alongside
the numbered steps.

- **Plan:** [dashboard-practice/README.md](./dashboard-practice/README.md)
- **Progress:** [dashboard-practice/PROGRESS.md](./dashboard-practice/PROGRESS.md)
- **Backend spec:** [dashboard-practice/API.md](./dashboard-practice/API.md)
- **Code:** `/dashboard-practice/` (repo root)
- **Status:** queued — starts after the 18-step course is finished (plan + API spec ready).

## Log

<!-- Append a short line each session, newest at the bottom. Example:
- 2026-05-20 — finished step 01, took notes on Vue vs React mental model
-->

- 2026-05-20 — learning plan created, starting with step 01
- 2026-05-20 — finished step 01 (concepts: what Vue is, progressive framework, Options vs Composition API, SFCs, ecosystem), starting step 02
- 2026-05-20 — finished step 02: scaffolded `vue-project/` via `npm create vue@latest` at repo root, minimal preset, dev server runs
- 2026-05-21 — finished step 03: rebuilt `App.vue` with `<script setup>` + `<template>`, learned mustaches, `:href` binding, expressions in `{{ }}`, and `v-html` + XSS risk
- 2026-05-21 — step 04 started: built counter with `ref` (learned `.value` rule + template auto-unwrap), rewrote with `reactive` (object-only, no `.value`); stopped before `user` object + destructuring/`toRefs` exercise
- 2026-05-26 — finished step 04: `user` reactive object with name/age + birthday button; saw destructuring break reactivity, fixed with `toRefs`; learned Proxy mental model behind it. Step 05 (Directives) next.
- 2026-05-26 — step 05 started: framed directives (`v-` prefix, `:` and `@` as shorthands); exercise 1 done — toggle paragraph with `v-if` then `v-show`, observed DOM diff in DevTools, learned when to pick each. Next: exercise 2 (`v-for` with `:key`).
- 2026-05-28 — finished step 05: built todo list with `v-for`/`:key` (stable id vs index footgun), live text mirror with `v-model` (= `:value` + `@input`), and modifiers `.trim`/`.number`/`.prevent`. Also covered why `ref` state uses `const` (mutate `.value`, never reassign). Step 06 (Computed & Watchers) next.
- 2026-05-28 — finished step 06: `fullName`/`parity` computeds (cached, lazy, auto-deps); `watch(count, ...)` (doesn't run on load, gives old/new) vs `watchEffect` (eager, auto-tracks only refs it reads); debounced search box with `clearTimeout`/`setTimeout` + `let` timer. Clarified computed must run on load if displayed. Step 07 (Methods & Event Handling) next.
- 2026-05-28 — step 07 started: built task-list app (App.vue) — method handlers `addTask`/`removeTask` in `<script setup>`, `@submit.prevent` form (Enter & button both submit), `v-for` rows with `@click="removeTask(task.id)"` passing args (reference vs call distinction). Next: `$event` access, `@keyup.enter`, `@click.stop` (ex 4).
- 2026-05-28 — kicked off Dashboard Practice side project (see dashboard-practice/ plan). Decided: e-commerce products & orders admin, new `/dashboard-practice/` app at repo root, real token auth. Wrote plan/progress/API spec under `learning-plan/dashboard-practice/`. Stan is scaffolding the Vite app himself via `npm create vue@latest` (Router + Pinia).
