# Create the editing session

`POST /api/2.0/files/file/{fileId}/edit_session`

Creates a session to edit the existing file with multiple chunks (needed for WebDAV).

 **Note**: Information about created session which includes:
<ul>
<li><b>id:</b> unique ID of this upload session,</li>
<li><b>created:</b> UTC time when the session was created,</li>
<li><b>expired:</b> UTC time when the session will expire if no chunks are sent before that time,</li>
<li><b>location:</b> URL where you should send your next chunk,</li>
<li><b>bytes_uploaded:</b> number of bytes uploaded for the specific upload ID,</li>
<li><b>bytes_total:</b> total number of bytes which will be uploaded.</li>
</ul>

Operation ID: `createEditSession`

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
| `fileId` | path | integer (int32) | Yes | The file ID. Example: `9846`. |
| `fileSize` | query | integer (int64) | No | The file size in bytes. Example: `1234`. |

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

### 403 — You don't have enough permission to edit the file

