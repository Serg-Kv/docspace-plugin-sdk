# Create file thumbnails

`POST /api/2.0/files/thumbnails`

Creates thumbnails for the files with the IDs specified in the request.

Operation ID: `createThumbnails`

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

### 200 — List of file IDs

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

