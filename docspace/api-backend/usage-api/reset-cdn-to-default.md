# Reset the CDN storage settings

`DELETE /api/2.0/settings/storage/cdn`

Resets the CDN storage settings to the default parameters.

Operation ID: `resetCdnToDefault`

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

