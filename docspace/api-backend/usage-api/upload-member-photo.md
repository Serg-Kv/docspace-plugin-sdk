# Upload a user photo

`POST /api/2.0/people/{userid}/photo`

Uploads a photo of the user with the ID specified in the request.

Operation ID: `uploadMemberPhoto`

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
| `userid` | path | string | Yes | The user ID. Example: `9846`. |

## Request body

Content type: `multipart/form-data`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `formCollection` | object[] | Yes | The image data. |
| `formCollection.key` | string, nullable | No | Example: `some text`. |
| `formCollection.value` | string[] | No |  |

## Responses

### 200 — Result of file uploading

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The file upload result. |
| `response.success` | boolean | No | Specifies if the upload operation is successful or not. Example: `true`. |
| `response.data` | any, nullable | No | The file upload result data. |
| `response.message` | string, nullable | No | The file upload result message. Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 400 — The uploaded file could not be found

### 401 — Unauthorized

### 403 — No permissions to perform this action

### 413 — Image size is too large

### 415 — Unknown image file type

