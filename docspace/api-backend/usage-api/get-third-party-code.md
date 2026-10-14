# Get the code request

`GET /api/2.0/thirdparty/{provider}`

Returns a request to get the confirmation code from URL.

 **Note**: List of providers: Google, Dropbox, Docusign, Box, OneDrive, Wordpress.

Operation ID: `getThirdPartyCode`

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
| `provider` | path | string | Yes | The identity provider used for authentication. One of: `Facebook`, `Google`, `Dropbox`, `Docusign`, `Box`, `OneDrive`, `GosUslugi`, `LinkedIn`, `MailRu`, `VK`, `Wordpress`, `Yahoo`, `Yandex`, `Github`. Example: `Facebook`. |

## Responses

### 200 — Code request

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

