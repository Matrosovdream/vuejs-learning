# 03 — First Vue App & Template Syntax

## Goals
- Understand how `main.js` mounts a root component into `index.html`.
- Read and write basic template syntax: text interpolation `{{ }}`, attribute binding `v-bind`, expressions inside templates.
- Know the structure of a `.vue` Single-File Component.

## Concepts
- **`createApp(App).mount('#app')`** — how Vue connects to the DOM.
- **SFC anatomy**:
  - `<template>` — HTML markup
  - `<script setup>` — JS logic (Composition API shorthand)
  - `<style>` — CSS (add `scoped` to limit to this component)
- **Mustaches** `{{ expression }}` — render text.
- **Attribute binding** `v-bind:href="url"` or shorthand `:href="url"`.
- **Expressions** — any single JS expression inside `{{ }}` or directives; not statements.

## Exercises
1. Replace the scaffold's `App.vue` with a minimal SFC that shows your name and the current year:
   ```vue
   <script setup>
   const name = 'Stan'
   const year = new Date().getFullYear()
   </script>

   <template>
     <h1>Hello, {{ name }}!</h1>
     <p>It is {{ year }}.</p>
   </template>
   ```
2. Add an `<a>` tag and bind its `href` with `:href` to a variable.
3. Try a calculation inside `{{ }}` — e.g. `{{ year + 1 }}`.
4. Try `v-html` (renders raw HTML). Then ask Claude *why you should almost never use it on user input*.

## Checklist
- [ ] I know what `main.js` does.
- [ ] I can write a component with `<script setup>` + `<template>`.
- [ ] I can interpolate variables and bind attributes.
- [ ] I understand the XSS risk of `v-html`.

## Resources
- Template syntax: https://vuejs.org/guide/essentials/template-syntax.html
