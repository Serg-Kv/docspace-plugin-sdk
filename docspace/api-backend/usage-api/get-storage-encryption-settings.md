# Get the storage encryption settings

`GET /api/2.0/settings/encryption/settings`

Returns the storage encryption settings.

Operation ID: `getStorageEncryptionSettings`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — Storage encryption settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The encryption settings. |
| `response.password` | string, nullable | No | The encryption password. Example: `vfmf2vO1Kp`. |
| `response.status` | string | No | [Decrypted - Decrypted, EncryptionStarted - Encryption started, Encrypted - Encrypted, DecryptionStarted - Decryption started] One of: `Decrypted`, `EncryptionStarted`, `Encrypted`, `DecryptionStarted`. Example: `Decrypted`. |
| `response.notifyUsers` | boolean | No | Specifies if the users will be notified about the encryption operation or not. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 403 — No permissions to perform this action

### 405 — Method not allowed

