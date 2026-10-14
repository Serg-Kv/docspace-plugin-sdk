# Get the payment page URL

`PUT /api/2.0/portal/payment/url`

Returns the URL to the payment page.

Operation ID: `getPaymentUrl`

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
| `backUrl` | string, nullable | No | The URL where the user will be redirected after payment processing. Example: `some text`. |
| `quantity` | object, nullable | No | The payment quantity. |

Example:

```json
{
  "backUrl": "some text",
  "quantity": [
    {
      "key": "some text",
      "value": 1234
    }
  ]
}
```

## Responses

### 200 — The URL to the payment page

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | string | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 403 — No permissions to perform this action

