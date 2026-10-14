# Finish migration

`POST /api/2.0/migration/finish`

Finishes the migration process.

Operation ID: `finishMigration`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Request body

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `isSendWelcomeEmail` | boolean | Yes | Specifies whether to send a welcome email or not. Example: `true`. |

Example:

```json
{
  "isSendWelcomeEmail": true
}
```

## Responses

### 200 — Ok

### 401 — Unauthorized

### 403 — No permissions to perform this action

