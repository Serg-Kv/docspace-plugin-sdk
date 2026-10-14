# Get login history

`GET /api/2.0/security/audit/login/last`

Returns all the latest user login activity, including successful logins and error logs.

Operation ID: `getLastLoginEvents`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — List of login events

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.id` | integer (int32) | No | The login event ID. Example: `9846`. |
| `response.date` | object | No | The API date and time parameters. |
| `response.date.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.date.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.user` | string, nullable | No | The user name of the login event. Example: `some text`. |
| `response.userId` | string (uuid) | No | The user ID of the login event. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |
| `response.login` | string, nullable | No | The user login of the login event. Example: `some text`. |
| `response.action` | string, nullable | No | The login event action. Example: `some text`. |
| `response.actionId` | string | No | The event action ID. One of: `LoginSuccess`, `LoginSuccessViaSocialAccount`, `LoginFailInvalidCombination`, `LoginFailSocialAccountNotFound`, `LoginFailDisabledProfile`, `LoginFail`, `Logout`, `LoginSuccessViaSms`, `LoginFailViaSms`, `LoginFailIpSecurity`, `LoginSuccessViaApi`, `LoginSuccessViaSocialApp`, `LoginSuccessViaApiSms`, `LoginFailViaApi`, `LoginFailViaApiSms`, and 297 more. Example: `LoginSuccess`. |
| `response.ip` | string, nullable | No | The login event IP. Example: `some text`. |
| `response.country` | string, nullable | No | The login event country. Example: `some text`. |
| `response.city` | string, nullable | No | The login event city. Example: `some text`. |
| `response.browser` | string, nullable | No | The login event browser. Example: `some text`. |
| `response.platform` | string, nullable | No | The login event platform. Example: `some text`. |
| `response.page` | string, nullable | No | The login event page. Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 402 — Your pricing plan does not support this option

