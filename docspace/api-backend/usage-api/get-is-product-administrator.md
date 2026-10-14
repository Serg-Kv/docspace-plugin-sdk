# Check a product administrator

`GET /api/2.0/settings/security/administrator`

Checks if the selected user is an administrator of a product with the ID specified in the request.

Operation ID: `getIsProductAdministrator`

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
| `productid` | query | string (uuid) | Yes | The ID of the product extracted from the query parameters. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |
| `userid` | query | string (uuid) | Yes | The user ID extracted from the query parameters. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |

## Responses

### 200 — Object with the user security information: product ID, user ID, administrator or not

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The product administrator parameters. |
| `response.productId` | string (uuid) | Yes | The product ID. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |
| `response.userId` | string (uuid) | Yes | The user unique identifier. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |
| `response.administrator` | boolean | Yes | Indicates whether the user has administrator privileges for the product. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

