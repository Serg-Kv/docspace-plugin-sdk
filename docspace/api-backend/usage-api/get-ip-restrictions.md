# Get the IP portal restrictions

`GET /api/2.0/settings/iprestrictions`

Returns the IP portal restrictions.

Operation ID: `getIpRestrictions`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — List of IP restrictions parameters

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.ip` | string, nullable | Yes | Example: `some text`. |
| `response.forAdmin` | boolean | No | Example: `true`. |
| `response.id` | integer (int32) | No | Example: `9846`. |
| `response.tenantId` | integer (int32) | No | Example: `1234`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

