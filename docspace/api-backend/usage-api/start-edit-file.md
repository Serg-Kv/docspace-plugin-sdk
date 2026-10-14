# Start file editing

`POST /api/2.0/files/file/{fileId}/startedit`

Informs about opening a file with the ID specified in the request for editing, locking it from being deleted or moved (this method is called by the mobile editors).

Operation ID: `startEditFile`

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `fileId` | path | integer (int32) | Yes | The file ID to start editing. Example: `9846`. |

## Request body

The file parameters to start editing.

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `editingAlone` | boolean | No | Specifies whether to share the file with other users for editing or not. Example: `true`. |

Example:

```json
{
  "editingAlone": true
}
```

## Responses

### 200 — File key for Document Service

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

### 403 — You don't have enough permission to view the file

