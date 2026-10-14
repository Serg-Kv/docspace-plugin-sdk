# Upload and initialize migration

`POST /api/2.0/migration/init/{migratorName}`

Uploads and initializes a migration with a migrator name specified in the request.

Operation ID: `uploadAndInitializeMigration`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `migratorName` | path | string | Yes | The migrator name extracted from the route parameters. Example: `some text`. |

## Responses

### 200 — Ok

### 401 — Unauthorized

### 403 — No permissions to perform this action

