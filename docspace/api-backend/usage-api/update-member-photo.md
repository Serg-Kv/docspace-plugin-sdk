# Update a user photo

`PUT /api/2.0/people/{userid}/photo`

Updates a photo of the user with the ID specified in the request.

Operation ID: `updateMemberPhoto`

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

The request parameters for updating a photo.

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `files` | string, nullable | No | The avatar photo URL. Example: `some text`. |

Example:

```json
{
  "files": "some text"
}
```

## Responses

### 200 — Updated thumbnail parameters: original photo, retina, maximum size photo, big, medium, small

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The thumbnails data parameters. |
| `response.original` | string, nullable | No | The thumbnail original photo. Example: `default_user_photo_size_1280-1280.png`. |
| `response.retina` | string, nullable | No | The thumbnail retina. Example: `default_user_photo_size_360-360.png`. |
| `response.max` | string, nullable | No | The thumbnail maximum size photo. Example: `default_user_photo_size_200-200.png`. |
| `response.big` | string, nullable | No | The thumbnail big size photo. Example: `default_user_photo_size_82-82.png`. |
| `response.medium` | string, nullable | No | The thumbnail medium size photo. Example: `default_user_photo_size_48-48.png`. |
| `response.small` | string, nullable | No | The thumbnail small size photo. Example: `default_user_photo_size_32-32.png`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 403 — No permissions to perform this action

### 404 — User not found

