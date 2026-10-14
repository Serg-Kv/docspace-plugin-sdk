# Set the password settings

`PUT /api/2.0/settings/security/password`

Sets the portal password settings.

Operation ID: `updatePasswordSettings`

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
| `minLength` | integer (int32) | Yes | The minimum number of characters required for valid passwords. Example: `1234`. |
| `upperCase` | boolean | No | Specifies whether the password should contain the uppercase letters or not. Example: `true`. |
| `digits` | boolean | No | Specifies whether the password should contain the digits or not. Example: `true`. |
| `specSymbols` | boolean | No | Specifies whether the password should contain the special symbols or not. Example: `true`. |

Example:

```json
{
  "minLength": 1234,
  "upperCase": true,
  "digits": true,
  "specSymbols": true
}
```

## Responses

### 200 — Password settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The password settings parameters. |
| `response.minLength` | integer (int32) | Yes | The minimum number of characters required for valid passwords. Example: `1234`. |
| `response.upperCase` | boolean | Yes | Specifies whether the password should contain the uppercase letters or not. Example: `true`. |
| `response.digits` | boolean | Yes | Specifies whether the password should contain the digits or not. Example: `true`. |
| `response.specSymbols` | boolean | Yes | Specifies whether the password should contain the special symbols or not. Example: `true`. |
| `response.allowedCharactersRegexStr` | string, nullable | Yes | The allowed password characters in the regex string format. Example: `some text`. |
| `response.digitsRegexStr` | string, nullable | Yes | The password digits in the regex string format. Example: `some text`. |
| `response.upperCaseRegexStr` | string, nullable | Yes | The password uppercase letters in the regex string format. Example: `some text`. |
| `response.specSymbolsRegexStr` | string, nullable | Yes | The passaword special symbols in the regex string format. Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 400 — MinLength

### 401 — Unauthorized

