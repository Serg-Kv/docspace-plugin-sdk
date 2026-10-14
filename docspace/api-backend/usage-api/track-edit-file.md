# Track file editing

`GET /api/2.0/files/file/{fileId}/trackeditfile`

Tracks file changes when editing.

Operation ID: `trackEditFile`

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `fileId` | path | integer (int32) | Yes | The file ID to track editing changes. Example: `9846`. |
| `tabId` | query | string (uuid) | No | The tab ID to track editing changes. Example: `75a5f745-f697-4418-b38d-0fe0d277e258`. |
| `docKeyForTrack` | query | string | No | The document key for tracking changes. Example: `some text`. |
| `isFinish` | query | boolean | No | Specifies whether to finish file tracking or not. Example: `true`. |

## Responses

### 200 — File changes

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No |  |
| `response.key` | boolean | No | Example: `true`. |
| `response.value` | string, nullable | No | Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 403 — You don't have enough permission to perform the operation

