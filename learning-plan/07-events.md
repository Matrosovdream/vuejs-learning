# 07 — Methods & Event Handling

## Goals
- Handle DOM events with `@event` and define handler functions.
- Use event modifiers and key modifiers idiomatically.
- Pass arguments to handlers.

## Concepts
- **Inline vs method handler**: `@click="count++"` (inline) vs `@click="onClick"` (method reference).
- **Passing arguments**: `@click="remove(todo.id)"` — wrapped in a function call.
- **Accessing the native event**: `@click="onClick($event)"` or `(e) => onClick(e, extra)`.
- **Event modifiers**: `.prevent`, `.stop`, `.once`, `.self`, `.capture`, `.passive`.
- **Key modifiers**: `@keyup.enter`, `@keyup.esc`, `@keydown.ctrl.s` (chord).

## Exercises
1. Build a form with a submit button. Use `@submit.prevent="onSubmit"` and log the form data.
2. Build a list of items with a "remove" button each — `@click="remove(item.id)"`.
3. Make an input that calls `search()` only on **Enter**: `@keyup.enter="search"`.
4. Use `@click.stop` on a nested button to prevent the parent's click handler from firing.

## Checklist
- [ ] I can pass arguments and still access `$event`.
- [ ] I know at least 3 event modifiers and when to use them.
- [ ] I can build a basic form with `@submit.prevent`.

## Resources
- Event handling: https://vuejs.org/guide/essentials/event-handling.html
