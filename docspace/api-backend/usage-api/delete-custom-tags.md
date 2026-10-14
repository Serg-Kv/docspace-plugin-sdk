# Delete the custom room tags

`DELETE /api/2.0/files/tags`

Deletes a bunch of custom room tags specified in the request.

Operation ID: `deleteCustomTags`

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
| `names` | string[], nullable | No | The list of tag names. |

Example:

```json
{
  "names": [
    "some text"
  ]
}
```

## Responses

### 200 — Ok

### 401 — Unauthorized

### 403 — You don't have enough permission to perform the operation

