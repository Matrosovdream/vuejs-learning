# Part 01 — Scaffold (create-vue with Router + Pinia)

## Goal
Create the Vite + Vue project from scratch, with Vue Router and Pinia included at
scaffold time.

## Concepts
- **`create-vue`** is Vue's official scaffolding tool, run via `npm create vue@latest`.
- Selecting Router/Pinia during scaffold wires them into `main.js` for you, instead
  of installing and configuring them by hand later.
- Project anatomy you'll get: `index.html` → loads `src/main.js` → mounts `App.vue`;
  plus `src/router/index.js` and `src/stores/` directories.

## Steps (Stan runs these)
1. From the repo root: `npm create vue@latest dashboard-practice`
2. Answer the prompts: TypeScript **No**, JSX **No**, **Router Yes**, **Pinia Yes**,
   Vitest **No**, E2E **No**, ESLint **No**, Prettier **No**, DevTools **Yes**.
3. `cd dashboard-practice && npm install && npm run dev`
4. Open the printed URL (usually http://localhost:5173); confirm the welcome page.

## Checklist
- [ ] Dev server runs and the create-vue welcome page shows.
- [ ] `src/router/index.js` and `src/stores/` exist.
- [ ] `main.js` shows `createApp(App).use(createPinia()).use(router).mount('#app')`.

## Resources
- create-vue: https://github.com/vuejs/create-vue
- Quick start: https://vuejs.org/guide/quick-start.html
