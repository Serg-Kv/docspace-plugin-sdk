# Get conversion status

`GET /api/2.0/files/file/{fileId}/checkconversion`

Checks the conversion status of a file with the ID specified in the request.

Operation ID: `checkConversionStatus`

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
| `fileId` | path | integer (int32) | Yes | The file ID to check conversion status. Example: `9846`. |
| `start` | query | boolean | No | Specifies whether a conversion operation is started or not. Example: `true`. |

## Responses

### 200 — Conversion result

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.id` | string, nullable | Yes | The conversion operation ID. Example: `9846`. |
| `response.Operation` | string | Yes | The file operation type. One of: `Move`, `Copy`, `Delete`, `Download`, `MarkAsRead`, `Import`, `Convert`, `Duplicate`. Example: `Move`. |
| `response.progress` | integer (int32) | Yes | The conversion operation progress. Example: `1234`. |
| `response.source` | string, nullable | No | The source file for the conversion. Example: `some text`. |
| `response.result` | any, nullable | No | The resulting file after the conversion. |
| `response.error` | string, nullable | No | The conversion operation error message. Example: `some text`. |
| `response.processed` | string, nullable | No | Specifies if the conversion operation is processed or not. Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

