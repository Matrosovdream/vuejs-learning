# 09 — Components Basics

## Goals
- Split a UI into small reusable components.
- Import and use a child component inside a parent.
- Understand component naming conventions.

## Concepts
- Each `.vue` file is a component. The file name (PascalCase preferred: `TodoItem.vue`) is the component.
- **Import + use**:
  ```vue
  <script setup>
  import TodoItem from './TodoItem.vue'
  </script>
  <template>
    <TodoItem />
  </template>
  ```
  With `<script setup>`, importing is enough — no manual registration.
- Each component has its **own** reactive state — instances are isolated.
- Style **`scoped`** keeps CSS local to the component.

## Exercises
1. Create `Greeting.vue` that just shows `<h1>Hello!</h1>`. Use it inside `App.vue`.
2. Refactor your counter from step 04 into its own `Counter.vue` component. Render two `<Counter />` and confirm they have independent state.
3. Create a `Card.vue` that has its own scoped CSS — verify the styles don't leak.

## Checklist
- [ ] I can split UI into files and import children.
- [ ] I understand that each `<Counter />` has independent state.
- [ ] I know what `<style scoped>` does.

## Resources
- Components basics: https://vuejs.org/guide/essentials/component-basics.html
- SFC: https://vuejs.org/guide/scaling-up/sfc.html
