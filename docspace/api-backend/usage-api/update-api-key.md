# Update an API key

`PUT /api/2.0/keys/{keyId}`

Updates an existing API key changing its name, permissions, and status.

Operation ID: `updateApiKey`

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
| `keyId` | path | string (uuid) | Yes | The unique identifier of the API key to update. Example: `75a5f745-f697-4418-b38d-0fe0d277e258`. |

## Request body

The request parameters for updating an existing API key.

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `name` | string, nullable | No | The new name for the API key. Example: `Winfield Upton`. |
| `permissions` | string[], nullable | No | The new list of permissions for the API key. |
| `isActive` | boolean, nullable | No | Indicates whether the API key should be active or not. Example: `true`. |

Example:

```json
{
  "name": "Winfield Upton",
  "permissions": [
    "some text"
  ],
  "isActive": true
}
```

## Responses

### 200 — Update optional params for user api keys

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

