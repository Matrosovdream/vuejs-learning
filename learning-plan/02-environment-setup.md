# 02 — Environment Setup

## Goals
- Have Node.js + npm installed and verified.
- Scaffold a Vue 3 project with Vite.
- Run the dev server and see the default app in the browser.
- Install Vue DevTools in your browser.

## Concepts
- **Node.js** — JavaScript runtime; needed for the build tools (not for running Vue in the browser).
- **npm** — Node's package manager; installs libraries.
- **Vite** — fast dev server + bundler; the recommended way to start a Vue project.
- **Project structure** — what `src/`, `public/`, `index.html`, `vite.config.js`, `package.json` are.

## Exercises
1. Check versions:
   ```sh
   node -v   # should be 18+ (20+ recommended)
   npm -v
   ```
2. Scaffold a project in `practice/02-setup/`:
   ```sh
   npm create vue@latest
   ```
   Pick: project name `hello-vue`, **No** to everything else for now (no TS, no router, no Pinia — we'll add those later).
3. Install and run:
   ```sh
   cd hello-vue
   npm install
   npm run dev
   ```
4. Open the URL Vite prints (usually http://localhost:5173). Edit `src/App.vue`, save, watch the browser update (hot reload).
5. Install **Vue DevTools** browser extension (Chrome/Firefox/Edge). Open it on your running app.

## Checklist
- [ ] `node -v` and `npm -v` both work.
- [ ] I scaffolded a project and ran `npm run dev` successfully.
- [ ] I can see the default Vue app in the browser.
- [ ] Vue DevTools extension is installed.
- [ ] I edited `App.vue` and saw the change hot-reload.

## Resources
- Quick start: https://vuejs.org/guide/quick-start.html
- Vite docs: https://vitejs.dev/
- DevTools: https://devtools.vuejs.org/
