# Get used space of files

`GET /api/2.0/files/filesusedspace`

Returns the used space of files in the root folders.

Operation ID: `getFilesUsedSpace`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — Used space of files in the root folders

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The file statistics result parameters. |
| `response.myDocumentsUsedSpace` | object | No | The file statictics folder parameters. |
| `response.myDocumentsUsedSpace.title` | string, nullable | No | The folder title. Example: `legacy_1080p_small_wooden_mouse`. |
| `response.myDocumentsUsedSpace.usedSpace` | integer (int64) | No | The used space in the folder. Example: `1234`. |
| `response.trashUsedSpace` | object | No | The file statictics folder parameters. |
| `response.trashUsedSpace.title` | string, nullable | No | The folder title. Example: `legacy_1080p_small_wooden_mouse`. |
| `response.trashUsedSpace.usedSpace` | integer (int64) | No | The used space in the folder. Example: `1234`. |
| `response.archiveUsedSpace` | object | No | The file statictics folder parameters. |
| `response.archiveUsedSpace.title` | string, nullable | No | The folder title. Example: `legacy_1080p_small_wooden_mouse`. |
| `response.archiveUsedSpace.usedSpace` | integer (int64) | No | The used space in the folder. Example: `1234`. |
| `response.roomsUsedSpace` | object | No | The file statictics folder parameters. |
| `response.roomsUsedSpace.title` | string, nullable | No | The folder title. Example: `legacy_1080p_small_wooden_mouse`. |
| `response.roomsUsedSpace.usedSpace` | integer (int64) | No | The used space in the folder. Example: `1234`. |
| `response.aiAgentsUsedSpace` | object | No | The file statictics folder parameters. |
| `response.aiAgentsUsedSpace.title` | string, nullable | No | The folder title. Example: `legacy_1080p_small_wooden_mouse`. |
| `response.aiAgentsUsedSpace.usedSpace` | integer (int64) | No | The used space in the folder. Example: `1234`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

