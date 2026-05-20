# 11 — Slots

## Goals
- Use `<slot />` to let parents inject markup into a child component.
- Use named slots and scoped slots.

## Concepts
- **Default slot** — child has `<slot />`, parent provides content between the component tags.
- **Named slots** — `<slot name="header" />` in child; `<template #header>...</template>` in parent.
- **Slot fallback** — content inside `<slot>fallback</slot>` is used if the parent provides nothing.
- **Scoped slots** — child exposes data to the parent's slot content:
  ```vue
  <!-- Child -->
  <slot :item="item" />

  <!-- Parent -->
  <Child v-slot="{ item }">{{ item.name }}</Child>
  ```

## Exercises
1. Build `<BaseCard>` with a default slot. Use it in two places with different content.
2. Extend `<BaseCard>` to also have `#header` and `#footer` named slots.
3. Build `<List :items="items">` that uses a scoped slot, so the parent can decide how to render each item.

## Checklist
- [ ] I can use a default slot.
- [ ] I can use named slots with `#name` shorthand.
- [ ] I understand what a scoped slot is and when to reach for it.

## Resources
- Slots: https://vuejs.org/guide/components/slots.html
