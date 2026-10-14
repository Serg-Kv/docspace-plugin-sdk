# Get the customer information

`GET /api/2.0/portal/payment/customerinfo`

Returns the customer information.

Operation ID: `getCustomerInfo`

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
| `refresh` | query | boolean | No | Specifies whether to refresh the payment information cache or not. Example: `true`. |

## Responses

### 200 — The customer info

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The customer information. |
| `response.portalId` | string, nullable | No | The portal ID. Example: `some text`. |
| `response.paymentMethodStatus` | string | No | The payment method status. One of: `None`, `Set`, `Expired`. Example: `None`. |
| `response.email` | string, nullable | No | The customer email address. Example: `Sydney_Roberts4@hotmail.com`. |
| `response.payer` | object | No | The user parameters. |
| `response.payer.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.payer.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.payer.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.payer.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.payer.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.payer.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.payer.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.payer.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.payer.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.payer.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.payer.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 403 — No permissions to perform this action

