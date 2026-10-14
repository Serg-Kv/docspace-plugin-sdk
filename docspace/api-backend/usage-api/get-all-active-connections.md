# Get active connections

`GET /api/2.0/security/activeconnections`

Returns all the active connections to the portal.

Operation ID: `getAllActiveConnections`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — Active portal connections

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The active connections parameters. |
| `response.loginEvent` | integer (int32) | Yes | The login event. Example: `1234`. |
| `response.items` | object[], nullable | No | The list of active connection items. |
| `response.items.id` | integer (int32) | Yes | The active connection ID. Example: `9846`. |
| `response.items.tenantId` | integer (int32) | Yes | The tenant ID. Example: `1234`. |
| `response.items.userId` | string (uuid) | Yes | The user ID. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |
| `response.items.mobile` | boolean | No | Specifies if the active connection has a mobile phone or not. Example: `true`. |
| `response.items.ip` | string, nullable | No | The IP address of the active connection. Example: `some text`. |
| `response.items.country` | string, nullable | No | The active connection country. Example: `some text`. |
| `response.items.city` | string, nullable | No | The active connection city. Example: `some text`. |
| `response.items.browser` | string, nullable | No | The active connection browser. Example: `some text`. |
| `response.items.platform` | string, nullable | No | The active connection platform. Example: `some text`. |
| `response.items.date` | object | No | The API date and time parameters. |
| `response.items.date.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.items.date.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.items.page` | string, nullable | No | The active connection page. Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

