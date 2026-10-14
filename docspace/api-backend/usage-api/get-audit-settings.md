# Get the audit trail settings

`GET /api/2.0/security/audit/settings/lifetime`

Returns the audit trail settings.

Operation ID: `getAuditSettings`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — Audit settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `settings` | object | No | The tenant audit settings parameters. |
| `settings.loginHistoryLifeTime` | integer (int32) | No | The login history lifetime. Example: `1234`. |
| `settings.auditTrailLifeTime` | integer (int32) | No | The audit trail lifetime. Example: `1234`. |
| `settings.lastModified` | string (date-time) | No | Example: `2008-04-10T06:30:00.0000000+04:00`. |

### 401 — Unauthorized

### 402 — Your pricing plan does not support this option

