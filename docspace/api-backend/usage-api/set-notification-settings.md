# Enable notifications

`POST /api/2.0/settings/notification`

Enables the notification type specified in the request.

Operation ID: `setNotificationSettings`

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
| `type` | string | Yes | The notification type. One of: `Badges`, `RoomsActivity`, `DailyFeed`, `UsefullTips`. Example: `Badges`. |
| `isEnabled` | boolean | No | Specifies if the specified notification type is enabled or not. Example: `true`. |

Example:

```json
{
  "type": "Badges",
  "isEnabled": true
}
```

## Responses

### 200 — Notification settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The notification settings parameters. |
| `response.type` | string | No | The notification type. One of: `Badges`, `RoomsActivity`, `DailyFeed`, `UsefullTips`. Example: `Badges`. |
| `response.isEnabled` | boolean | No | Specifies if the notification type is enabled or not. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

