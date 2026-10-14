# Save the room quota settings

`POST /api/2.0/settings/roomquotasettings`

Saves the room quota settings specified in the request to the current portal.

Operation ID: `saveRoomQuotaSettings`

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
| `enableQuota` | boolean | No | Specifies whether the storage quota restrictions are enabled. Example: `true`. |
| `defaultQuota` | integer | Yes | The default storage quota value applied to new users. Example: `1234`. |

Example:

```json
{
  "enableQuota": true,
  "defaultQuota": 1234
}
```

## Responses

### 200 — Tenant room quota settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The room quota settings. |
| `response.enableQuota` | boolean | No | Specifies if the quota is enabled for the tenant entity or not. Example: `true`. |
| `response.defaultQuota` | integer (int64) | No | The default quota of the tenant entity. Example: `1234`. |
| `response.lastRecalculateDate` | string (date-time), nullable | No | The date of the last quota recalculation. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.lastModified` | string (date-time) | No | Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 402 — Your pricing plan does not support this option

