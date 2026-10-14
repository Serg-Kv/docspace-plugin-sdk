# Check file uploads

`POST /api/2.0/files/{folderId}/upload/check`

Checks the file uploads to the folder with the ID specified in the request.

Operation ID: `checkUpload`

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
| `folderId` | path | integer (int32) | Yes | The folder ID. Example: `9846`. |

## Request body

The request parameters for checking file uploads.

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `filesTitle` | string[], nullable | No | The list of file titles. |

Example:

```json
{
  "filesTitle": [
    "some text"
  ]
}
```

## Responses

### 200 — Inserted file

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | string[] | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

