# Update the wallet payment quantity

`PUT /api/2.0/portal/payment/updatewallet`

Updates the wallet payment quantity with the parameters specified in the request.

Operation ID: `updateWalletPayment`

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
| `quantity` | object, nullable | No | The mapping of item identifiers to their respective quantities in the payment. |
| `productQuantityType` | string | No | The type of action performed on a product's quantity. One of: `Set`, `Add`, `Sub`, `Renew`. Example: `Set`. |

Example:

```json
{
  "quantity": [
    {
      "key": "some text",
      "value": 1234
    }
  ],
  "productQuantityType": "Set"
}
```

## Responses

### 200 — Boolean value: true if the operation is successful

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | boolean | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 403 — No permissions to perform this action

