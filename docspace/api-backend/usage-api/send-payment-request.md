# Send a payment request

`POST /api/2.0/portal/payment/request`

Sends a request for the portal payment.

Operation ID: `sendPaymentRequest`

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
| `userName` | string, nullable | No | The name of the user submitting the sales request. Example: `some text`. |
| `email` | string, nullable | Yes | The contact email address for the sales inquiry. Example: `Sydney_Roberts4@hotmail.com`. |
| `message` | string, nullable | Yes | The details of the sales inquiry or payment request. Example: `some text`. |

Example:

```json
{
  "userName": "some text",
  "email": "Sydney_Roberts4@hotmail.com",
  "message": "some text"
}
```

## Responses

### 200 — Ok

### 400 — Incorrect email or message text is empty

### 401 — Unauthorized

### 429 — Request limit is exceeded

