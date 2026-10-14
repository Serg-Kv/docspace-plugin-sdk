# Start file conversion

`PUT /api/2.0/files/file/{fileId}/checkconversion`

Starts a conversion operation of a file with the ID specified in the request.

Operation ID: `startFileConversion`

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
| `fileId` | path | integer (int32) | Yes | The file ID to start conversion proccess. Example: `9846`. |

## Request body

The parameters for checking file conversion.

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `fileId` | integer (int32) | No | The file ID to check conversion proccess. Example: `9846`. |
| `sync` | boolean | No | Specifies if the conversion process is synchronous or not. Example: `true`. |
| `startConvert` | boolean | No | Specifies whether to start a conversion process or not. Example: `true`. |
| `version` | integer (int32) | No | The file version that is converted. Example: `1234`. |
| `password` | string, nullable | No | The password of the converted file. Example: `vfmf2vO1Kp`. |
| `outputType` | string, nullable | No | The conversion output type. Example: `some text`. |
| `createNewIfExist` | boolean | No | Specifies whether to create a new file if it exists or not. Example: `true`. |

Example:

```json
{
  "fileId": 9846,
  "sync": true,
  "startConvert": true,
  "version": 1234,
  "password": "vfmf2vO1Kp",
  "outputType": "some text",
  "createNewIfExist": true
}
```

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

