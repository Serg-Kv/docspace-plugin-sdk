# Chunked upload

`POST /api/2.0/files/{folderId}/upload/create_session`

Creates the session to upload large files in multiple chunks to the folder with the ID specified in the request.

 **Note**: Each chunk can have different length but the length should be multiple of <b>512</b> and greater or equal to <b>10 mb</b>. Last chunk can have any size.
After the initial response to the request with the <b>200 OK</b> status, you must get the <em>location</em> field value from the response. Send all your chunks to this location.
Each chunk must be sent in the exact order the chunks appear in the file.
After receiving each chunk, the server will respond with the current information about the upload session if no errors occurred.
When the number of bytes uploaded is equal to the number of bytes you sent in the initial request, the server responds with the <b>201 Created</b> status and sends you information about the uploaded file.
Information about created session which includes:
<ul>
<li><b>id:</b> unique ID of this upload session,</li>
<li><b>created:</b> UTC time when the session was created,</li>
<li><b>expired:</b> UTC time when the session will expire if no chunks are sent before that time,</li>
<li><b>location:</b> URL where you should send your next chunk,</li>
<li><b>bytes_uploaded:</b> number of bytes uploaded for the specific upload ID,</li>
<li><b>bytes_total:</b> total number of bytes which will be uploaded.</li>
</ul>

Operation ID: `createUploadSession`

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
| `folderId` | path | integer (int32) | Yes | The session folder ID. Example: `9079`. |

## Request body

The session parameters.

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `fileName` | string, nullable | Yes | The file name. Example: `some text`. |
| `fileSize` | integer (int64) | No | The file size. Example: `1234`. |
| `relativePath` | string, nullable | No | The relative path to the file. Example: `some text`. |
| `createOn` | object | No | The API date and time parameters. |
| `createOn.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `createOn.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `encrypted` | boolean | No | Specifies whether the file is encrypted or not. Example: `true`. |
| `createNewIfExist` | boolean | No | Specifies whether to create a new file if it already exists. Example: `true`. |

Example:

```json
{
  "fileName": "some text",
  "fileSize": 1234,
  "relativePath": "some text",
  "createOn": {},
  "encrypted": true,
  "createNewIfExist": true
}
```

## Responses

### 200 — Information about created session

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 403 — You don't have enough permission to create

