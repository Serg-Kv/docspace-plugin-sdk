# Close the admin helper

`PUT /api/2.0/settings/closeadminhelper`

Closes the administrator helper notification.

Operation ID: `closeAdminHelper`

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

### 405 — Not available

