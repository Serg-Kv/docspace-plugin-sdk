# Update a storage

`PUT /api/2.0/settings/storage`

Updates a storage with the parameters specified in the request.

Operation ID: `updateStorage`

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
| `module` | string, nullable | Yes | The name for the storage module to be configured. Example: `some text`. |
| `props` | object[], nullable | No | The list of configuration key-value pairs for the storage module. |
| `props.key` | string, nullable | No | Example: `some text`. |
| `props.value` | string, nullable | No | Example: `some text`. |

Example:

```json
{
  "module": "some text",
  "props": [
    {
      "key": "some text",
      "value": "some text"
    }
  ]
}
```

## Responses

### 200 — Updated storage settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No |  |
| `response.module` | string, nullable | No | Example: `some text`. |
| `response.props` | object, nullable | No |  |
| `response.id` | string (uuid) | No | Example: `75a5f745-f697-4418-b38d-0fe0d277e258`. |
| `response.lastModified` | string (date-time) | No | Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 400 — Module

### 401 — Unauthorized

### 403 — No permissions to perform this action

