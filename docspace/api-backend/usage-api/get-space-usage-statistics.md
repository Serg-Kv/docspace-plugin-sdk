# Get the space usage statistics

`GET /api/2.0/settings/statistics/spaceusage/{id}`

Returns the space usage statistics for the module with the ID specified in the request.

Operation ID: `getSpaceUsageStatistics`

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
| `id` | path | string (uuid) | Yes | The ID extracted from the route parameters. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |

## Responses

### 200 — Module space usage statistics

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.name` | string, nullable | No | The item name. Example: `Item name`. |
| `response.icon` | string, nullable | No | The item icon path. Example: `Item icon path`. |
| `response.disabled` | boolean | No | Specifies if the item is disabled or not. Example: `false`. |
| `response.size` | string, nullable | No | The item used space. Example: `0 Byte`. |
| `response.url` | string, nullable | No | The item URL. Example: `Item url`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

