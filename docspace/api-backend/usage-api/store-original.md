# Change the ability to upload original formats

`PUT /api/2.0/files/storeoriginal`

Changes the ability to upload documents in the original formats as well.

Operation ID: `storeOriginal`

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
| `set` | boolean | No | Specifies whether to set the specified settings or not. Example: `true`. |

Example:

```json
{
  "set": true
}
```

## Responses

### 200 — Boolean value: true if the operation is successful

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

