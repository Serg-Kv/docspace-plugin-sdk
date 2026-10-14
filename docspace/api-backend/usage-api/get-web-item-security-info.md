# Get the module availability

`GET /api/2.0/settings/security/{id}`

Returns the availability of the module with the ID specified in the request.

Operation ID: `getWebItemSecurityInfo`

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

### 200 — Boolean value: true - module is enabled, false - module is disabled

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | boolean | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

