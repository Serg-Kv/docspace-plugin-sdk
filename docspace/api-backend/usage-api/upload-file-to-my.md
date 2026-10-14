# Upload a file to the 'My documents' section

`POST /api/2.0/files/@my/upload`

Uploads a file specified in the request to the "My documents" section by single file uploading or standart multipart/form-data method.

 **Note**:  You can upload files in two different ways:
 <ol>
<li>Using single file upload. You should set the Content-Type and Content-Disposition headers to specify a file name and content type, and send the file to the request body.</li>
<li>Using standart multipart/form-data method.</li>
</ol>

Operation ID: `uploadFileToMy`

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
| `inDto` | query | object | No | The request parameters for uploading a file. |

## Responses

### 200 — Uploaded file(s)

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

### 404 — File not found

