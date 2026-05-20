# Vue.js Learning Plan

A step-by-step path to learn Vue.js 3 from zero. Each step is a self-contained lesson with goals, concepts, exercises, and resources. Claude is your tutor — ask questions as you go.

## How to use this plan

1. Work through steps in order (01 → 18).
2. For each step:
   - Read the lesson file (`NN-title.md`).
   - Try the exercises in `/practice/NN-title/` (you'll create these as you go).
   - Ask Claude to explain anything unclear or review your code.
3. When you finish a step, update [PROGRESS.md](PROGRESS.md) — that's where we track where you are.

## Stack we're targeting

- **Vue 3** (Composition API as primary, Options API mentioned where useful)
- **Vite** as the build tool / dev server
- **Pinia** for state management
- **Vue Router** for routing
- Plain JavaScript first; TypeScript introduced later (optional)

## Steps

### Part 1 — Foundations
- [01 — Introduction to Vue.js](01-introduction.md) — what Vue is, why use it, the ecosystem
- [02 — Environment Setup](02-environment-setup.md) — Node, npm, Vite, project scaffold
- [03 — First Vue App & Template Syntax](03-first-app.md) — mounting, interpolation, attributes

### Part 2 — Core Reactivity & Directives
- [04 — Reactivity Fundamentals](04-reactivity.md) — `ref`, `reactive`, how reactivity works
- [05 — Directives](05-directives.md) — `v-bind`, `v-if`, `v-for`, `v-on`, `v-model`
- [06 — Computed Properties & Watchers](06-computed-watchers.md)
- [07 — Methods & Event Handling](07-events.md)
- [08 — Class & Style Bindings](08-class-style.md)

### Part 3 — Components
- [09 — Components Basics](09-components-basics.md) — defining, registering, using
- [10 — Props & Events](10-props-events.md) — parent ↔ child communication
- [11 — Slots](11-slots.md) — default, named, scoped
- [12 — Lifecycle Hooks](12-lifecycle.md)

### Part 4 — Going Bigger
- [13 — Composition API Deep Dive](13-composition-api.md) — `setup`, composables, reusing logic
- [14 — Vue Router](14-router.md) — multi-page apps
- [15 — State Management with Pinia](15-pinia.md)
- [16 — Forms, Validation & HTTP](16-forms-http.md) — talking to a real backend

### Part 5 — Finishing Up
- [17 — Build, Deploy & Testing Basics](17-build-deploy.md)
- [18 — Capstone Project](18-capstone.md) — a small app that uses everything above

## Progress

See [PROGRESS.md](PROGRESS.md) for the current step and notes from past lessons.
