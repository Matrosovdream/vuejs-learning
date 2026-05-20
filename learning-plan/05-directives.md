# 05 — Directives

## Goals
- Use the core built-in directives to drive your templates.
- Understand the shorthand syntax.

## Concepts
- **Directive** = special attribute starting with `v-` that applies reactive behavior to the DOM.
- **`v-bind:attr` / `:attr`** — bind any attribute or prop to an expression.
- **`v-on:event` / `@event`** — listen to DOM events.
- **`v-model`** — two-way binding on form inputs (and components later).
- **`v-if` / `v-else-if` / `v-else`** — conditional rendering (element removed from DOM).
- **`v-show`** — toggle CSS `display` (element stays in DOM).
- **`v-for="item in list"`** — render a list. Always add a `:key`.
- **Key choice** — use a stable unique id, NOT the array index unless the list never reorders.

## Exercises
1. Toggle a paragraph's visibility with a button using `v-if`. Then switch to `v-show`. When would you pick each?
2. Render a list of todos with `v-for`, including `:key="todo.id"`.
3. Build a text input with `v-model` that mirrors the value into a `<p>` below it live.
4. Add modifiers: `@click.prevent`, `v-model.trim`, `v-model.number` — try each and observe.

## Checklist
- [ ] I can use `:`, `@`, and `v-model` confidently.
- [ ] I always add `:key` in `v-for`.
- [ ] I know the difference between `v-if` and `v-show`.

## Resources
- List rendering: https://vuejs.org/guide/essentials/list.html
- Conditional rendering: https://vuejs.org/guide/essentials/conditional.html
- Form bindings: https://vuejs.org/guide/essentials/forms.html
