# Calculate the wallet payment amount

`PUT /api/2.0/portal/payment/calculatewallet`

Calculates an amount of the wallet payment with the parameters specified in the request.

Operation ID: `calculateWalletPayment`

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

### 200 — Payment calculation

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The parameters of the calculated payment amount. |
| `response.operationId` | integer (int64) | No | The operation unique identifier. Example: `1234`. |
| `response.amount` | number (double) | No | The calculated payment amount. |
| `response.currency` | string, nullable | No | The three-character ISO 4217 currency symbol used for the payment calculation. Example: `some text`. |
| `response.quantity` | integer (int32) | No | The quantity associated with the payment calculation. Example: `1234`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 403 — No permissions to perform this action

