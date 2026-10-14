# Reset the SMTP settings

`DELETE /api/2.0/smtpsettings/smtp`

Resets the SMTP settings of the current portal.

Operation ID: `resetSmtpSettings`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — Default SMTP settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The SMTP settings parameters. |
| `response.host` | string, nullable | No | The SMTP host. Example: `mail.example.com`. |
| `response.port` | integer (int32), nullable | No | The SMTP port. Example: `25`. |
| `response.senderAddress` | string, nullable | No | The sender address. Example: `notify@example.com`. |
| `response.senderDisplayName` | string, nullable | No | The sender display name. Example: `Postman`. |
| `response.credentialsUserName` | string, nullable | No | The credentials username. Example: `notify@example.com`. |
| `response.credentialsUserPassword` | string, nullable | No | The credentials user password. Example: `{password}`. |
| `response.enableSSL` | boolean | No | Specifies whether the SSL is enabled or not. Example: `false`. |
| `response.enableAuth` | boolean | No | Specifies whether the authentication is enabled or not. Example: `true`. |
| `response.useNtlm` | boolean | No | Specifies whether to use NTLM or not. Example: `false`. |
| `response.isDefaultSettings` | boolean | No | Specifies if the current settings are default or not. Example: `false`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 402 — Your pricing plan does not support this option

