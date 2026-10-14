# Get the product administrators

`GET /api/2.0/settings/security/administrator/{productid}`

Returns a list of all the administrators of a product with the ID specified in the request.

Operation ID: `getProductAdministrators`

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
| `productid` | path | string (uuid) | Yes | The ID of the product extracted from the route parameters. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |

## Responses

### 200 — List of product administrators with the following parameters

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
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

### 401 — Unauthorized

