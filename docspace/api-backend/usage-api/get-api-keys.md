# Get current user's API keys

`GET /api/2.0/keys`

Returns a list of all API keys for the current user.

Operation ID: `getApiKeys`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — List of api keys for user

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.id` | string (uuid) | Yes | The API key unique identifier. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |
| `response.name` | string, nullable | Yes | The API key name. Example: `Winfield Upton`. |
| `response.key` | string, nullable | Yes | The full API key value (only returned when creating a new key). Example: `some text`. |
| `response.keyPostfix` | string, nullable | No | The API key postfix (used for identification). Example: `some text`. |
| `response.permissions` | string[], nullable | Yes | The list of permissions granted to the API key. |
| `response.lastUsed` | object | No | The API date and time parameters. |
| `response.lastUsed.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.lastUsed.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.createOn` | object | No | The API date and time parameters. |
| `response.createOn.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.createOn.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.createBy` | object | No | The user parameters. |
| `response.createBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.createBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.createBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.createBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.createBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.createBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.createBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.createBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.createBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.createBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.createBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.expiresAt` | object | No | The API date and time parameters. |
| `response.expiresAt.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.expiresAt.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.isActive` | boolean | Yes | Indicates whether the API key is active or not. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

