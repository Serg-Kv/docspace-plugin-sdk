# Get currencies

`GET /api/2.0/portal/payment/currencies`

Returns the available portal currencies.

Operation ID: `getPaymentCurrencies`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — List of available portal currencies

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.isoCountryCode` | string, nullable | No | The ISO country code. Example: `some text`. |
| `response.isoCurrencySymbol` | string, nullable | No | The ISO currency symbol. Example: `some text`. |
| `response.currencyNativeName` | string, nullable | No | The currency native name. Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

