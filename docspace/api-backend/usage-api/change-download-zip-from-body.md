# Change the archive format (using body parameters)

`PUT /api/2.0/files/settings/downloadtargz`

Changes the format of the downloaded archive from .zip to .tar.gz. This method uses the body parameters.

Operation ID: `changeDownloadZipFromBody`

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

### 200 — Archive

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The archiving class unification interface. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

