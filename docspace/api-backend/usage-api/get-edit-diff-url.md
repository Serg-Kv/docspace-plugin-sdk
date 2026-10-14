# Get changes URL

`GET /api/2.0/files/file/{fileId}/edit/diff`

Returns a URL to the changes of a file version specified in the request.

Operation ID: `getEditDiffUrl`

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `fileId` | path | integer (int32) | Yes | The file ID. Example: `9846`. |
| `version` | query | integer (int32) | No | The file version. Example: `1234`. |

## Responses

### 200 — File version history data

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The file editing history data. |
| `response.changesUrl` | string (uri), nullable | No | The URL address of the file with the document changes data. Example: `some text`. |
| `response.key` | string, nullable | Yes | The document identifier used to unambiguously identify the document file. Example: `some text`. |
| `response.previous` | object | No | The file editing history URL parameters. |
| `response.previous.key` | string, nullable | No | The document identifier of the previous version of the document. Example: `some text`. |
| `response.previous.url` | string (uri), nullable | No | The url address of the previous version of the document. Example: `some text`. |
| `response.previous.fileType` | string, nullable | No | The document extension. Example: `some text`. |
| `response.token` | string, nullable | No | The encrypted signature added to the parameter in the form of a token. Example: `some text`. |
| `response.url` | string (uri), nullable | Yes | The URL address of the current document version. Example: `some text`. |
| `response.version` | integer (int32) | Yes | The document version number. Example: `1234`. |
| `response.fileType` | string, nullable | Yes | The document extension. Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

