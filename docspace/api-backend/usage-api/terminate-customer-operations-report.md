# Terminate the customer operations report generation

`DELETE /api/2.0/portal/payment/customer/operationsreport`

Terminates generating a customer operations report.

Operation ID: `terminateCustomerOperationsReport`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — Ok

### 401 — Unauthorized

