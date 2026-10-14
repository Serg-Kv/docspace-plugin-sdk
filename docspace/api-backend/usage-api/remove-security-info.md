# Remove the sharing rights

`DELETE /api/2.0/files/share`

Removes the sharing rights from all the files and folders specified in the request.

Operation ID: `removeSecurityInfo`

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
| `returnSingleOperation` | boolean | No | Specifies whether to return only the current operation Example: `true`. |
| `folderIds` | integer[], nullable | No | The list of folder IDs of the base batch request. |
| `fileIds` | integer[], nullable | No | The list of file IDs of the base batch request. |

Example:

```json
{}
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

