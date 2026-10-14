# Get folder form filter

`GET /api/2.0/files/{folderId}/formfilter`

Returns the form filter of a folder with the ID specified in the request.

Operation ID: `getFolder`

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `folderId` | path | integer (int32) | Yes | The folder unique identifier. Example: `9846`. |

## Responses

### 200 — Ok

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.key` | string, nullable | No | Example: `some text`. |
| `response.type` | string, nullable | No | Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

