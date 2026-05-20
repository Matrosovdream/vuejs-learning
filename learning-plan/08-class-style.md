# 08 — Class & Style Bindings

## Goals
- Toggle classes and styles reactively without string concatenation.
- Combine static and dynamic classes.

## Concepts
- **Object syntax**: `:class="{ active: isActive, disabled: !canClick }"` — keys are classes, values are booleans.
- **Array syntax**: `:class="[base, isActive && 'active']"`.
- **Mixing static + dynamic** — `class="card"` and `:class="..."` merge automatically.
- **Inline style binding**: `:style="{ color: textColor, fontSize: size + 'px' }"`.
- **Style arrays**: `:style="[baseStyles, overrideStyles]"`.

## Exercises
1. Toggle an `active` class on a `<div>` when a button is clicked.
2. Build a "danger / warning / info" alert component where the class depends on a `type` ref.
3. Bind an element's `color` and `font-size` via `:style` to two refs and tweak them with inputs.

## Checklist
- [ ] I can toggle a class with object syntax.
- [ ] I can bind styles with camelCase JS keys.
- [ ] I prefer class bindings over template string juggling.

## Resources
- Class and style: https://vuejs.org/guide/essentials/class-and-style.html
