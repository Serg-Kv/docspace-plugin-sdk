# Get the SMTP testing process status

`GET /api/2.0/smtpsettings/smtp/test/status`

Returns the status of the SMTP testing process.

Operation ID: `getSmtpOperationStatus`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — SMTP operation status

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The request parameters for tracking SMTP (Simple Mail Transfer Protocol) operation status. |
| `response.completed` | boolean | No | Specifies whether the SMTP operation has finished processing. Example: `true`. |
| `response.id` | string, nullable | No | The unique identifier for tracking the SMTP operation. Example: `{some-random-guid}`. |
| `response.error` | string, nullable | No | The error message if the SMTP operation encountered issues. Example: ``. |
| `response.status` | string, nullable | No | The current state of the SMTP operation. Example: ``. |
| `response.percents` | integer (int32) | No | The progress indicator showing completion percentage of the operation. Example: `0`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 402 — Your pricing plan does not support this option

