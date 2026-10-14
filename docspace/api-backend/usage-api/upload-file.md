# Upload a file

`POST /api/2.0/files/{folderId}/upload`

Uploads a file specified in the request to the selected folder by single file uploading or standart multipart/form-data method.

 **Note**:  You can upload files in two different ways:
 <ol>
<li>Using single file upload. You should set the Content-Type and Content-Disposition headers to specify a file name and content type, and send the file to the request body.</li>
<li>Using standart multipart/form-data method.</li>
</ol>

Operation ID: `uploadFile`

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
| `folderId` | path | integer (int32) | Yes | The folder ID to upload a file. Example: `9846`. |

## Request body

The request parameters for uploading a file.

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `file` | string (binary), nullable | No | The file to be uploaded. |
| `contentType` | object | No |  |
| `contentType.boundary` | string, nullable | No | Example: `some text`. |
| `contentType.charSet` | string, nullable | No | Example: `some text`. |
| `contentType.mediaType` | string, nullable | No | Example: `some text`. |
| `contentType.name` | string, nullable | No | Example: `Winfield Upton`. |
| `contentType.parameters` | object[], nullable | No |  |
| `contentDisposition` | object | No |  |
| `contentDisposition.dispositionType` | string, nullable | No | Example: `some text`. |
| `contentDisposition.parameters` | object[], nullable | No |  |
| `contentDisposition.fileName` | string, nullable | No | Example: `some text`. |
| `contentDisposition.creationDate` | string (date-time) | No | Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `contentDisposition.modificationDate` | string (date-time) | No | Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `contentDisposition.inline` | boolean | No | Example: `true`. |
| `contentDisposition.readDate` | string (date-time) | No | Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `contentDisposition.size` | integer (int64) | No | Example: `1234`. |
| `files` | string[] (binary), nullable | No | The list of files when specified as multipart/form-data. |
| `createNewIfExist` | boolean | No | Specifies whether to create the new file if it already exists or not. Example: `true`. |
| `storeOriginalFileFlag` | boolean, nullable | No | Specifies whether to upload documents in the original formats as well or not. Example: `true`. |
| `keepConvertStatus` | boolean | No | Specifies whether to keep the file converting status or not. Example: `true`. |
| `stream` | string (binary), nullable | No | The request input stream. |

Example:

```json
{
  "file": "string",
  "contentType": {
    "boundary": "some text",
    "charSet": "some text",
    "mediaType": "some text",
    "name": "Winfield Upton"
  },
  "contentDisposition": {
    "dispositionType": "some text",
    "fileName": "some text",
    "creationDate": "2008-04-10T06:30:00.0000000+04:00",
    "modificationDate": "2008-04-10T06:30:00.0000000+04:00",
    "inline": true,
    "readDate": "2008-04-10T06:30:00.0000000+04:00",
    "size": 1234
  },
  "files": [
    "string"
  ],
  "createNewIfExist": true,
  "storeOriginalFileFlag": true,
  "keepConvertStatus": true,
  "stream": "string"
}
```

## Responses

### 200 — Inserted file

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

### 404 — Folder not found

