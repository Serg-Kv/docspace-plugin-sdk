# Get notification channels

`GET /api/2.0/settings/notification/channels`

Returns a list of notification channels.

Operation ID: `getNotificationChannels`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — Notification settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The notification channel settings. |
| `response.channels` | object[], nullable | No | The list of notification channels. |
| `response.channels.name` | string, nullable | Yes | The notification channel name. Example: `Winfield Upton`. |
| `response.channels.isEnabled` | boolean | Yes | Specifies whether the notification channel is enabled. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

