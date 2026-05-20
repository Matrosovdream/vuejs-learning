# 15 — State Management with Pinia

## Goals
- Understand when you need a store (and when you don't).
- Define a Pinia store and use it across components.

## Concepts
- **Pinia** is the official state management library for Vue 3 (replaces Vuex). Tiny, typed, DevTools integration.
- **When to reach for a store**: state shared across distant components, persisted across routes, or coordinated mutations. For nearby state, just lift to a parent or use a composable.
- **Define a store** (setup-style — recommended):
  ```js
  import { defineStore } from 'pinia'
  import { ref, computed } from 'vue'

  export const useCounterStore = defineStore('counter', () => {
    const count = ref(0)
    const double = computed(() => count.value * 2)
    function inc() { count.value++ }
    return { count, double, inc }
  })
  ```
- **Use it**:
  ```js
  const counter = useCounterStore()
  counter.count    // reactive
  counter.inc()
  ```
- **Don't destructure raw** — use `storeToRefs(store)` to keep reactivity when you destructure values.

## Exercises
1. Install Pinia and register it in `main.js`.
2. Build a `useTodosStore` with `todos`, `add(text)`, `toggle(id)`, `remove(id)`, and a `remaining` getter.
3. Use the same store from two unrelated components and confirm they stay in sync.
4. Try destructuring without `storeToRefs` — observe what breaks. Then fix with `storeToRefs`.

## Checklist
- [ ] I can create and use a Pinia store with `<script setup>`.
- [ ] I know to use `storeToRefs` when destructuring.
- [ ] I can articulate when NOT to use a store.

## Resources
- Pinia: https://pinia.vuejs.org/
