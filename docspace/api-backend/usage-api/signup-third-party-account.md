# Create a third-pary account

`POST /api/2.0/people/thirdparty/signup`

Creates a third-party account with the parameters specified in the request.

Operation ID: `signupThirdPartyAccount`

## Request body

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `employeeType` | string | No | The user type. One of: `All`, `RoomAdmin`, `Guest`, `DocSpaceAdmin`, `User`. Example: `All`. |
| `firstName` | string, nullable | No | The user first name. Example: `Winfield`. |
| `lastName` | string, nullable | No | The user last name. Example: `Wyman`. |
| `email` | string (email), nullable | No | The user email address. Example: `Sydney_Roberts4@hotmail.com`. |
| `passwordHash` | string, nullable | No | The user password hash. Example: `some text`. |
| `key` | string, nullable | Yes | The user link key. Example: `some text`. |
| `culture` | string, nullable | No | The user culture code. Example: `some text`. |
| `serializedProfile` | string, nullable | Yes | The third-party profile in the serialized format Example: `some text`. |

Example:

```json
{
  "employeeType": "All",
  "firstName": "Winfield",
  "lastName": "Wyman",
  "email": "Sydney_Roberts4@hotmail.com",
  "passwordHash": "some text",
  "key": "some text",
  "culture": "some text",
  "serializedProfile": "some text"
}
```

## Responses

### 200 — Ok

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The user parameters. |
| `response.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 400 — Incorrect email

### 403 — The invitation link is invalid or its validity has expired

