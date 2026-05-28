# Part 02 — Strip demo content + add simple CSS

## Goal
Remove the create-vue demo files so we have a clean base, and install our plain CSS
framework.

## Concepts
- A fresh scaffold ships demo components (`HelloWorld`, `TheWelcome`, icons) and demo
  views we don't need. Clearing them avoids confusion later.
- **Global stylesheet**: one `src/assets/main.css` imported once in `main.js` gives
  app-wide design tokens (CSS variables) and utility classes.
- **Global vs scoped CSS**: global classes (`.btn`, `.card`) live in `main.css`;
  component-specific styles go in a `<style scoped>` block inside that component.

## What we'll do
- Delete the demo: `src/components/*`, the demo `src/views/*`, `src/assets/base.css`
  / `logo.svg` references.
- Replace `src/assets/main.css` with our framework (tokens, buttons, cards, table,
  forms, badges, layout helpers).
- Trim `App.vue` down to a shell that renders `<RouterView />`.

## Checklist
- [ ] No leftover `HelloWorld` / `TheWelcome` imports anywhere.
- [ ] App loads with our CSS (background, fonts applied).
- [ ] `main.js` imports `./assets/main.css`.

## Resources
- SFC `<style scoped>`: https://vuejs.org/api/sfc-css-features.html
