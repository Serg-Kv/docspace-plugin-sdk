# Deactivate a portal

`PUT /api/2.0/portal/suspend`

Deactivates the current portal.

Operation ID: `suspendPortal`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — OK

### 401 — Unauthorized

