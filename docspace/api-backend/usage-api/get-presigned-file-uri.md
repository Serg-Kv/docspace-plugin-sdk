# Get file download link asynchronously

`GET /api/2.0/files/file/{fileId}/presigned`

Returns a link to download a file with the ID specified in the request asynchronously.

Operation ID: `getPresignedFileUri`

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
| `fileId` | path | integer (int32) | Yes | The file unique identifier. Example: `9846`. |

## Responses

### 200 — File download link

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The file link properties. |
| `response.filetype` | string, nullable | Yes | The type of the file for the source viewed or edited document. Example: `some text`. |
| `response.token` | string, nullable | No | The encrypted signature added to the config in the form of a token. Example: `some text`. |
| `response.url` | string (uri), nullable | Yes | The absolute URL where the source viewed or edited document is stored. Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

