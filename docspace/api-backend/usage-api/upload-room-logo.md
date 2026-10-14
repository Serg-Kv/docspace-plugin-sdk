# Upload a room logo image

`POST /api/2.0/files/logos`

Uploads a temporary image to create a room logo.

Operation ID: `uploadRoomLogo`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Request body

Content type: `multipart/form-data`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `FormCollection` | object[] | No | The image data. |
| `FormCollection.key` | string, nullable | No | Example: `some text`. |
| `FormCollection.value` | string[] | No |  |

## Responses

### 200 — Upload result

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The upload result parameters. |
| `response.success` | boolean | No | Specifies if the upload operation is successful or not. Example: `true`. |
| `response.data` | any, nullable | No | The uploaded data. |
| `response.message` | string, nullable | No | The message sent after the successful upload operation. Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 403 — No permissions to perform this action

