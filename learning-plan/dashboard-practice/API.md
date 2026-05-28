# Backend API spec — Admin Dashboard

This is the contract the Vue frontend expects. Build your backend to match these
shapes and the frontend will work without changes. You can use any stack
(Node/Express, FastAPI, Laravel, etc.).

## Conventions

- **Base URL:** configurable via `VITE_API_URL` (default `http://localhost:3000/api`).
  All paths below are relative to that base.
- **Format:** JSON request and response bodies. `Content-Type: application/json`.
- **Auth:** after login, the frontend sends `Authorization: Bearer <token>` on
  every protected request.
- **CORS:** the backend must allow the Vite dev origin
  (`http://localhost:5173`) and the `Authorization` + `Content-Type` headers.
- **Errors:** non-2xx responses should return `{ "message": "human readable error" }`.
  Use proper status codes: `400` validation, `401` missing/invalid token,
  `403` forbidden, `404` not found, `422` validation details.
- **Lists are paginated** and return an envelope: `{ items, total, page, pageSize }`.

---

## 1. Auth

### POST /auth/login
Request:
```json
{ "email": "admin@example.com", "password": "secret123" }
```
Response `200`:
```json
{
  "token": "eyJhbGciOi...",
  "user": { "id": 1, "name": "Admin User", "email": "admin@example.com", "role": "admin" }
}
```
Response `401`: `{ "message": "Invalid email or password" }`

### GET /auth/me  *(protected)*
Returns the current user for the supplied token. Used to restore the session on
page refresh.
Response `200`:
```json
{ "id": 1, "name": "Admin User", "email": "admin@example.com", "role": "admin" }
```
Response `401`: `{ "message": "Unauthenticated" }`

### POST /auth/logout  *(protected, optional)*
Invalidate the token server-side if you track sessions. Response `204`.
(The frontend also just drops the token locally, so this is optional.)

---

## 2. Stats (dashboard landing)

### GET /stats  *(protected)*
Response `200`:
```json
{
  "totalProducts": 128,
  "totalOrders": 542,
  "revenue": 84210.50,
  "pendingOrders": 17
}
```

---

## 3. Categories (for product filter dropdown)

### GET /categories  *(protected)*
Response `200`:
```json
[
  { "id": 1, "name": "Electronics" },
  { "id": 2, "name": "Apparel" },
  { "id": 3, "name": "Home" }
]
```

---

## 4. Products

**Product shape:**
```json
{
  "id": 12,
  "name": "Wireless Mouse",
  "sku": "WM-1001",
  "categoryId": 1,
  "category": "Electronics",
  "price": 29.99,
  "stock": 143,
  "status": "active",
  "createdAt": "2026-04-10T12:00:00Z"
}
```
`status` is one of: `active`, `archived`.

### GET /products  *(protected)*
Query params (all optional):
| param      | type   | meaning                                            |
|------------|--------|----------------------------------------------------|
| `search`   | string | match name or sku (case-insensitive)               |
| `categoryId` | int  | filter by category                                 |
| `status`   | string | `active` \| `archived`                             |
| `sort`     | string | e.g. `price`, `-price`, `name`, `-createdAt` (`-` = desc) |
| `page`     | int    | 1-based, default 1                                 |
| `pageSize` | int    | default 10                                          |

Response `200`:
```json
{
  "items": [ { "...product..." } ],
  "total": 128,
  "page": 1,
  "pageSize": 10
}
```

### GET /products/:id  *(protected)*
Response `200`: a single product object. `404` if not found.

### POST /products  *(protected)*
Request (no id/createdAt):
```json
{ "name": "...", "sku": "...", "categoryId": 1, "price": 9.99, "stock": 10, "status": "active" }
```
Response `201`: the created product (with `id`, `createdAt`).
Response `422`: `{ "message": "Validation failed", "errors": { "sku": "already exists" } }`

### PUT /products/:id  *(protected)*
Request: same fields as POST. Response `200`: updated product.

### DELETE /products/:id  *(protected)*
Response `204` (no body). `404` if not found.

---

## 5. Orders

**Order (list row) shape:**
```json
{
  "id": 5005,
  "orderNumber": "ORD-2026-5005",
  "customerName": "Jane Doe",
  "customerEmail": "jane@example.com",
  "status": "pending",
  "total": 129.97,
  "itemCount": 3,
  "createdAt": "2026-05-20T09:30:00Z"
}
```
`status` is one of: `pending`, `paid`, `shipped`, `delivered`, `cancelled`.

### GET /orders  *(protected)*
Query params (all optional):
| param      | type   | meaning                                            |
|------------|--------|----------------------------------------------------|
| `search`   | string | match orderNumber, customerName, or customerEmail  |
| `status`   | string | one of the statuses above                          |
| `dateFrom` | string | ISO date, inclusive lower bound on createdAt       |
| `dateTo`   | string | ISO date, inclusive upper bound                    |
| `sort`     | string | e.g. `-createdAt`, `total`, `-total`               |
| `page`     | int    | 1-based, default 1                                 |
| `pageSize` | int    | default 10                                          |

Response `200`: `{ items, total, page, pageSize }`.

### GET /orders/:id  *(protected)*
Returns the order plus its line items:
```json
{
  "id": 5005,
  "orderNumber": "ORD-2026-5005",
  "customerName": "Jane Doe",
  "customerEmail": "jane@example.com",
  "status": "pending",
  "total": 129.97,
  "createdAt": "2026-05-20T09:30:00Z",
  "items": [
    { "productId": 12, "name": "Wireless Mouse", "qty": 2, "price": 29.99 },
    { "productId": 30, "name": "USB-C Cable",    "qty": 1, "price": 69.99 }
  ]
}
```

### PATCH /orders/:id/status  *(protected)*
Request:
```json
{ "status": "shipped" }
```
Response `200`: the updated order. `400` if the status value is invalid.

---

## Suggested seed / test login

Create at least one user the frontend can log in with:
```
email:    admin@example.com
password: secret123
```
Seed ~30 products across 3 categories and ~40 orders across the statuses so the
lists, filters, and pagination have something to show.

---

## Build order note

The frontend is built in this rough order, so the endpoints you'll want first:
1. `POST /auth/login` + `GET /auth/me`  (needed for login & route guards)
2. `GET /products` (+ `GET /categories`)  (the first list + filters)
3. `GET /products/:id`, `POST/PUT/DELETE /products`  (detail + CRUD)
4. `GET /orders`, `GET /orders/:id`, `PATCH /orders/:id/status`
5. `GET /stats`  (dashboard landing)
