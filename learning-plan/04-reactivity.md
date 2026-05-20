# 04 — Reactivity Fundamentals

## Goals
- Understand what "reactive" means in Vue.
- Use `ref()` and `reactive()` to make state that drives the UI.
- Know when to pick `ref` vs `reactive`.

## Concepts
- **Reactivity** = when a value changes, anything that depends on it re-runs (re-renders the UI, recomputes a value, etc.).
- **`ref(value)`** — wraps any value (primitive or object). Access/mutate with `.value` in `<script>`, but **not** in `<template>` (auto-unwrapped there).
- **`reactive(object)`** — makes an object deeply reactive. Use the object directly, no `.value`. Only works on objects/arrays.
- **Rule of thumb**: default to `ref` — it's more consistent. Use `reactive` for tightly-grouped object state when you prefer the no-`.value` ergonomics.
- **Reactivity caveats** — destructuring a `reactive` object loses reactivity; replacing the whole object also breaks it. `ref` avoids both.

## Exercises
1. Counter with `ref`:
   ```vue
   <script setup>
   import { ref } from 'vue'
   const count = ref(0)
   function inc() { count.value++ }
   </script>

   <template>
     <button @click="inc">{{ count }}</button>
   </template>
   ```
2. Rewrite the same counter using `reactive({ count: 0 })`. Notice the differences.
3. Create a `reactive` `user` object with `name` and `age`. Render both. Bind a button to increment `age`.
4. Try destructuring `const { name } = user` and rendering `name` — confirm it does NOT stay reactive. Ask Claude why and how `toRefs` fixes it.

## Checklist
- [ ] I can build a counter with `ref`.
- [ ] I know why `.value` is needed in `<script>` but not in `<template>`.
- [ ] I can explain `ref` vs `reactive` in one sentence each.

## Resources
- Reactivity: https://vuejs.org/guide/essentials/reactivity-fundamentals.html
