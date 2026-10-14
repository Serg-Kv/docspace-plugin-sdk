# Get the backup storages

`GET /api/2.0/settings/storage/backup`

Returns a list of all the backup storages.

Operation ID: `getAllBackupStorages`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `Dump` | query | boolean | No | Example: `true`. |

## Responses

### 200 — List of the backup storages with the following parameters

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.id` | string, nullable | Yes | The storage ID. Example: `9846`. |
| `response.title` | string, nullable | Yes | The storage title. Example: `legacy_1080p_small_wooden_mouse`. |
| `response.properties` | object[], nullable | No | The list of storage authentication keys. |
| `response.properties.name` | string, nullable | Yes | The authorization key name. Example: `Winfield Upton`. |
| `response.properties.value` | string, nullable | Yes | The authorization key value. Example: `some text`. |
| `response.properties.title` | string, nullable | No | The authorization key title. Example: `legacy_1080p_small_wooden_mouse`. |
| `response.current` | boolean | Yes | Specifies if this is the current portal storage or not. Example: `true`. |
| `response.isSet` | boolean | Yes | Specifies if this storage can be set or not. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 402 — Your pricing plan does not support this option

