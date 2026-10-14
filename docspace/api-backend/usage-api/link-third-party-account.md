# Link a third-pary account

`PUT /api/2.0/people/thirdparty/linkaccount`

Links a third-party account specified in the request to the user profile.

Operation ID: `linkThirdPartyAccount`

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
| `serializedProfile` | string, nullable | No | The third-party profile in the serialized format. Example: `some text`. |

Example:

```json
{
  "serializedProfile": "some text"
}
```

## Responses

### 200 — Ok

### 401 — Unauthorized

### 405 — Error not allowed option

