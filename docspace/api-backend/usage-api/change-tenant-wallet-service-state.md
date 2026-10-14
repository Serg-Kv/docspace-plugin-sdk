# Change wallet service state

`POST /api/2.0/portal/payment/servicestate`

Changes the wallet service state.

Operation ID: `changeTenantWalletServiceState`

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
| `service` | string | No | The wallet service type. One of: `WebSearch`, `AITools`, `Backup`, `Storage`. Example: `WebSearch`. |
| `enabled` | boolean | No | Specifies whether the wallet service is enabled. Example: `true`. |

Example:

```json
{
  "service": "WebSearch",
  "enabled": true
}
```

## Responses

### 200 — The wallet service settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The wallet services settings. |
| `response.enabledServices` | string[], nullable | No | The list of the enabled wallet services. One of: `WebSearch`, `AITools`, `Backup`, `Storage`. |
| `response.lastModified` | string (date-time) | No | The date and time when the wallet services settings were last modified. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 403 — No permissions to perform this action

