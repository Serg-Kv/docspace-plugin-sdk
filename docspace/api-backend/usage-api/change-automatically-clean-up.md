# Update the trash bin auto-clearing setting

`PUT /api/2.0/files/settings/autocleanup`

Updates the trash bin auto-clearing setting.

Operation ID: `changeAutomaticallyCleanUp`

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
| `set` | boolean | No | Specifies whether to enable the auto-clearing or not. Example: `true`. |
| `gap` | string | No | The period when the trash bin will be cleared. One of: `OneWeek`, `TwoWeeks`, `OneMonth`, `ThirtyDays`, `TwoMonths`, `ThreeMonths`. Example: `OneWeek`. |

Example:

```json
{
  "set": true,
  "gap": "OneWeek"
}
```

## Responses

### 200 — The auto-clearing setting properties: auto-clearing or not, a time interval when the auto-clearing will be performed

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The auto-clearing setting parameters. |
| `response.isAutoCleanUp` | boolean | No | Specifies whether to permanently delete files in the Trash folder. Example: `true`. |
| `response.gap` | string | No | The period when the trash bin will be cleared. One of: `OneWeek`, `TwoWeeks`, `OneMonth`, `ThirtyDays`, `TwoMonths`, `ThreeMonths`. Example: `OneWeek`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

