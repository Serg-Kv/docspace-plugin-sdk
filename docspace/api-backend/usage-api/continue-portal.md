# Restore a portal

`PUT /api/2.0/portal/continue`

Restores the current portal.

Operation ID: `continuePortal`

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

