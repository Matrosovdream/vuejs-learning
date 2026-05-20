# 16 — Forms, Validation & HTTP

## Goals
- Build a real form with validation and a loading/error UX.
- Fetch and post data from a backend API.

## Concepts
- **`v-model` on every input** — text, textarea, select, checkbox, radio. Modifiers: `.trim`, `.number`, `.lazy`.
- **Basic validation** — local refs for errors, validate on submit and/or via watchers. For real apps, libraries like **VeeValidate**, **Vuelidate**, or **Zod + custom logic** are common.
- **HTTP** — built-in `fetch` is fine; **axios** is popular for cleaner interceptors and timeouts.
- **UX states** — always represent `idle / loading / success / error` explicitly; don't conflate.
- **AbortController** — cancel in-flight requests when the component unmounts or the input changes again.

## Exercises
1. Build a sign-up form with `name`, `email`, `password`. Validate: all required, valid email, password ≥ 8 chars. Show field-level errors below each input.
2. Disable the submit button while the request is in flight; show a spinner.
3. Use https://jsonplaceholder.typicode.com/posts in a `useFetch` composable. Render the list. Add a "create post" form.
4. Add an AbortController so navigating away cancels the request.

## Checklist
- [ ] I can build a validated multi-field form.
- [ ] My UI handles loading and error states explicitly.
- [ ] I cancel requests on unmount.

## Resources
- Forms: https://vuejs.org/guide/essentials/forms.html
- VeeValidate: https://vee-validate.logaretm.com/v4/
- Axios: https://axios-http.com/
