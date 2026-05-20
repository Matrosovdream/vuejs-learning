# 12 — Lifecycle Hooks

## Goals
- Know the main lifecycle hooks and when they fire.
- Use `onMounted` for setup work (fetching, subscribing) and `onUnmounted` for cleanup.

## Concepts
- The major hooks in Composition API:
  - `onBeforeMount` — right before the DOM is created.
  - **`onMounted`** — DOM is in place; safe to query refs, start fetches, attach listeners.
  - `onBeforeUpdate` / `onUpdated` — around DOM updates triggered by reactive changes.
  - **`onUnmounted`** — clean up timers, subscriptions, event listeners.
  - `onErrorCaptured` — capture errors from descendants.
- Hooks must be called **synchronously inside `<script setup>`** (not in async callbacks).
- **`ref` in templates** (`ref="myEl"`) — gives you a DOM element reference, available *after* mount.

## Exercises
1. Use `onMounted` to log `'mounted'` and `onUnmounted` to log `'gone'`. Toggle the component with `v-if` to see both.
2. In `onMounted`, focus an `<input>` using a template ref.
3. Start a `setInterval` in `onMounted`; clean it up in `onUnmounted`. Verify with DevTools that no leaks remain.

## Checklist
- [ ] I default to `onMounted` for "do this after the component is on screen".
- [ ] I always pair side-effects with cleanup in `onUnmounted`.
- [ ] I can grab a DOM node via template refs.

## Resources
- Lifecycle: https://vuejs.org/guide/essentials/lifecycle.html
- Template refs: https://vuejs.org/guide/essentials/template-refs.html
