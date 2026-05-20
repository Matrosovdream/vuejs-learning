# 17 — Build, Deploy & Testing Basics

## Goals
- Produce a production build and understand what's in `dist/`.
- Deploy to a static host.
- Write a handful of unit tests for components and composables.

## Concepts
- **`npm run build`** → outputs `dist/` (static HTML/JS/CSS). **`npm run preview`** serves it locally.
- **Env variables** — `.env`, `.env.production`. Only vars prefixed with `VITE_` are exposed to client code.
- **Deploy targets** — Netlify, Vercel, Cloudflare Pages, GitHub Pages. Any static host works.
- **Routing on static hosts** — for `history` mode you must configure SPA fallback (`/* -> /index.html`) or the host's equivalent.
- **Unit testing** — **Vitest** (built for Vite) + **@vue/test-utils** for mounting components.

## Exercises
1. Run `npm run build` then `npm run preview`. Open the preview URL.
2. Deploy your project to **Netlify** or **Vercel** by connecting the GitHub repo. (Or drag the `dist/` folder to Netlify Drop.)
3. Install Vitest:
   ```sh
   npm i -D vitest @vue/test-utils jsdom
   ```
   Add a `test` script. Write one test that mounts your `Counter` and asserts the count increments on click.
4. Write a unit test for a composable (no component needed — just call the function).

## Checklist
- [ ] I built and previewed the app locally.
- [ ] I deployed it to a live URL.
- [ ] I wrote at least one component test and one composable test.

## Resources
- Vite build: https://vitejs.dev/guide/build.html
- Vitest: https://vitest.dev/
- Vue Test Utils: https://test-utils.vuejs.org/
