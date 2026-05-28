# Part 04 — API client (fetch wrapper)

## Goal
Build one small module that every store uses to talk to the backend, so token
handling and error handling live in a single place.

## Concepts
- **Wrapper over `fetch`**: instead of calling `fetch` everywhere, centralize it.
- **Base URL** from env: `import.meta.env.VITE_API_URL`.
- **Auth header**: attach `Authorization: Bearer <token>` when a token exists.
- **JSON helpers**: set `Content-Type`, `JSON.stringify` the body, parse the response.
- **Error handling**: throw on non-2xx so callers can `try/catch`; special-case
  `401` (token invalid → force logout).
- **Query strings**: build `?search=...&page=...` from a params object.

## What we'll build
- `src/api/client.js` exposing `apiGet`, `apiPost`, `apiPut`, `apiPatch`, `apiDelete`
  (or a single `request` + helpers).
- Reads the token from the auth store / localStorage and sets the header.
- On `401`, clears the session and redirects to `/login`.

## Endpoints
- Used by all later parts; no endpoint of its own.

## Checklist
- [ ] One function builds requests with base URL + token header.
- [ ] Non-2xx responses throw with a useful message.
- [ ] 401 triggers logout/redirect.

## Resources
- Fetch API: https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API
- Vite env vars: https://vite.dev/guide/env-and-mode.html
