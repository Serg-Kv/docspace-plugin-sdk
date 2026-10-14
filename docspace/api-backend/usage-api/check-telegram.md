# Check the Telegram connection

`GET /api/2.0/settings/telegram/check`

Checks if the current user is connected to the Telegram Bot or not.

Operation ID: `checkTelegram`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — Status if user is linked or not

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No |  |
| `response.status` | integer (int32) | Yes | The registration Telegram status. One of: `0`, `1`, `2`. |
| `response.username` | string, nullable | No | Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

