# Set wallet auto top-up settings

`POST /api/2.0/portal/payment/topupsettings`

Sets the wallet auto top-up settings.

Operation ID: `setTenantWalletSettings`

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
| `settings` | object | No | The tenant wallet settings. |
| `settings.enabled` | boolean | No | Specifies whether automatic top-up for the tenant wallet is enabled. Example: `true`. |
| `settings.minBalance` | integer (int32) | No | The minimum wallet balance at which automatic top-up will be triggered. Must be between 5 and 1000. Example: `1234`. |
| `settings.upToBalance` | integer (int32) | No | The maximum wallet balance at which automatic top-up will be triggered. Must be between 6 and 5000. Example: `1234`. |
| `settings.currency` | string, nullable | No | The three-character ISO 4217 currency symbol. Example: `some text`. |
| `settings.lastModified` | string (date-time) | No | The date and time when the tenant wallet settings were last modified. Example: `2008-04-10T06:30:00.0000000+04:00`. |

Example:

```json
{
  "settings": {
    "enabled": true,
    "minBalance": 1234,
    "upToBalance": 1234,
    "currency": "some text",
    "lastModified": "2008-04-10T06:30:00.0000000+04:00"
  }
}
```

## Responses

### 200 — The wallet auto top up settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `settings` | object | No | The tenant wallet settings. |
| `settings.enabled` | boolean | No | Specifies whether automatic top-up for the tenant wallet is enabled. Example: `true`. |
| `settings.minBalance` | integer (int32) | No | The minimum wallet balance at which automatic top-up will be triggered. Must be between 5 and 1000. Example: `1234`. |
| `settings.upToBalance` | integer (int32) | No | The maximum wallet balance at which automatic top-up will be triggered. Must be between 6 and 5000. Example: `1234`. |
| `settings.currency` | string, nullable | No | The three-character ISO 4217 currency symbol. Example: `some text`. |
| `settings.lastModified` | string (date-time) | No | The date and time when the tenant wallet settings were last modified. Example: `2008-04-10T06:30:00.0000000+04:00`. |

### 401 — Unauthorized

### 403 — No permissions to perform this action

