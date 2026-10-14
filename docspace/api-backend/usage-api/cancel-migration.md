# Cancel migration

`POST /api/2.0/migration/cancel`

Cancels the migration.

Operation ID: `cancelMigration`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — Ok

### 401 — Unauthorized

### 403 — No permissions to perform this action

