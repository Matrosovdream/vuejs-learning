# 13 — Composition API Deep Dive

## Goals
- Master `<script setup>` patterns.
- Extract reusable logic into **composables**.
- Understand `provide` / `inject` for cross-component data without prop drilling.

## Concepts
- **`<script setup>`** is the modern shorthand: top-level bindings are auto-exposed to the template, imports are auto-registered.
- **Composables** = functions named `useXxx` that encapsulate reactive logic and can be reused across components. They are *the* Vue equivalent of React hooks.
  ```js
  // useCounter.js
  import { ref } from 'vue'
  export function useCounter(initial = 0) {
    const count = ref(initial)
    function inc() { count.value++ }
    return { count, inc }
  }
  ```
- **`provide` / `inject`** — share state down a deep tree without passing props at every level.
- **`toRefs` / `toRef`** — turn reactive object properties back into individual refs (preserves reactivity on destructure).
- **`shallowRef` / `shallowReactive`** — opt out of deep reactivity for performance.

## Exercises
1. Extract your counter into `composables/useCounter.js`. Use it in two different components.
2. Build `useMousePosition()` that returns `{ x, y }` refs updated by a `mousemove` listener — attach in `onMounted`, detach in `onUnmounted`.
3. Build `useFetch(url)` returning `{ data, error, loading }`. Use it in a component.
4. Use `provide('theme', ref('dark'))` in a top component, `inject('theme')` in a grandchild.

## Checklist
- [ ] I can write a custom `useXxx()` composable.
- [ ] I clean up listeners inside composables (using `onUnmounted`).
- [ ] I know when to reach for `provide`/`inject` instead of props.

## Resources
- Composables: https://vuejs.org/guide/reusability/composables.html
- Provide/inject: https://vuejs.org/guide/components/provide-inject.html
