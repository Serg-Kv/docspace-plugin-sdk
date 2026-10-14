# Terminate the room index export

`DELETE /api/2.0/files/rooms/indexexport`

Terminates the room index export.

Operation ID: `terminateRoomIndexExport`

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

