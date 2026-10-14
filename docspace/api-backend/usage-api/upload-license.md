# Upload a license

`POST /api/2.0/settings/license`

Uploads a portal license specified in the request.

Operation ID: `uploadLicense`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Request body

Content type: `multipart/form-data`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `Files` | string[] (binary) | Yes | The list of license files to be uploaded. |

## Responses

### 200 — License

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | string | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 400 — The uploaded file could not be found

### 401 — Unauthorized

### 403 — Portal Access

### 405 — Your pricing plan does not support this option

