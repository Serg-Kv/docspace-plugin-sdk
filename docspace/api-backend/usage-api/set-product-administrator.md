# Set a product administrator

`PUT /api/2.0/settings/security/administrator`

Sets the selected user as an administrator of a product with the ID specified in the request.

Operation ID: `setProductAdministrator`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Request body

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `productId` | string (uuid) | Yes | The product ID for which permissions are being set. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |
| `userId` | string (uuid) | Yes | The ID of the user whose permissions are being configured. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |
| `administrator` | boolean | No | Specifies whether the user has administrative privileges. Example: `true`. |

Example:

```json
{
  "productId": "aae1e103-bca5-9fa1-ba8c-42058b4abf28",
  "userId": "aae1e103-bca5-9fa1-ba8c-42058b4abf28",
  "administrator": true
}
```

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

### 402 — Your pricing plan does not support this option

### 403 — Only portal owner can set user as administrator

