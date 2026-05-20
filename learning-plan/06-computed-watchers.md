# 06 — Computed Properties & Watchers

## Goals
- Replace messy in-template logic with `computed`.
- Use `watch` and `watchEffect` to react to changes (e.g. fetch on input).

## Concepts
- **`computed(() => …)`** — derived reactive value; cached based on its dependencies; re-evaluates only when they change.
- **Computed vs method** — computed caches; a method runs on every re-render.
- **`watch(source, (newVal, oldVal) => …)`** — explicit observer; you declare exactly what to watch.
- **`watchEffect(() => …)`** — runs immediately, then re-runs whenever any reactive value it reads changes.
- **`{ immediate: true, deep: true }`** options.

## Exercises
1. Given `firstName` and `lastName` refs, expose a `fullName` computed.
2. Build a search box that watches the input and logs the value with a 300ms debounce (ask Claude how to debounce inside a watcher).
3. Use `watchEffect` to log a message every time `count` changes — compare ergonomics to `watch`.
4. Make a computed that returns `'even'` or `'odd'` based on `count`.

## Checklist
- [ ] I default to `computed` for derived state.
- [ ] I can pick between `watch` and `watchEffect`.
- [ ] I know computed is cached and a method is not.

## Resources
- Computed: https://vuejs.org/guide/essentials/computed.html
- Watchers: https://vuejs.org/guide/essentials/watchers.html
