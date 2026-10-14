# Get the customer balance

`GET /api/2.0/portal/payment/customer/balance`

Returns the customer balance from the accounting service.

Operation ID: `getCustomerBalance`

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

### 200 — The customer balance

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | Represents a balance with an account number and a list of sub-accounts. |
| `response.accountNumber` | integer (int32) | No | The account number. Example: `1234`. |
| `response.subAccounts` | object[], nullable | No | A list of sub-accounts. |
| `response.subAccounts.currency` | string, nullable | No | The three-character ISO 4217 currency symbol of the sub-account. Example: `some text`. |
| `response.subAccounts.amount` | number (double) | No | The balance of the sub-account in the specified currency. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 403 — No permissions to perform this action

