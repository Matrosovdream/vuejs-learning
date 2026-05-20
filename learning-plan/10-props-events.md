# 10 — Props & Events

## Goals
- Pass data **down** from parent to child via `defineProps`.
- Emit events **up** from child to parent via `defineEmits`.
- Use `v-model` on custom components.

## Concepts
- **Props are one-way down.** Don't mutate them in the child.
- **`defineProps`** (compile-time macro inside `<script setup>`):
  ```js
  const props = defineProps({
    title: { type: String, required: true },
    count: { type: Number, default: 0 }
  })
  ```
- **Events go up** via `defineEmits`:
  ```js
  const emit = defineEmits(['update', 'delete'])
  emit('update', newValue)
  ```
- **Custom `v-model`**: a prop named `modelValue` + an emit `update:modelValue`. Vue 3 also supports multiple v-models with names.

## Exercises
1. Build `<UserCard :name="..." :email="..." />`. Pass data from a parent list.
2. Build `<TodoItem :todo="todo" @toggle="..." @remove="..." />` — clicking a checkbox emits `toggle`, clicking a delete button emits `remove`.
3. Build a `<MyInput v-model="text" />` reusable input. Inside, use `modelValue` + `emit('update:modelValue', ...)`.
4. Add prop validation (`required`, `type`, `default`) and trigger a warning by passing the wrong type — observe the console.

## Checklist
- [ ] I can pass props with `defineProps` and validate them.
- [ ] I can emit events with `defineEmits`.
- [ ] I can build a component that supports `v-model`.

## Resources
- Props: https://vuejs.org/guide/components/props.html
- Events: https://vuejs.org/guide/components/events.html
- Custom v-model: https://vuejs.org/guide/components/v-model.html
