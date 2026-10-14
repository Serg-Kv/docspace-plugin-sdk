# Send SMS code

`POST /api/2.0/authentication/sendsms`

Sends SMS with an authentication code.

Operation ID: `sendSmsCode`

## Request body

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `userName` | string, nullable | No | The username or email used for authentication. Example: `some text`. |
| `password` | string, nullable | No | The password in plain text for user authentication. Example: `vfmf2vO1Kp`. |
| `passwordHash` | string, nullable | No | The hashed password for secure verification. Example: `some text`. |
| `provider` | string, nullable | No | The type of authentication provider (e.g., internal, Google, Azure). Example: `some text`. |
| `accessToken` | string, nullable | No | The access token used for authentication with external providers. Example: `some text`. |
| `serializedProfile` | string, nullable | No | The serialized user profile data, if applicable. Example: `some text`. |
| `code` | string, nullable | No | The code for two-factor authentication. Example: `some text`. |
| `codeOAuth` | string, nullable | No | The authorization code used for obtaining OAuth tokens. Example: `some text`. |
| `session` | boolean | No | Specifies whether the authentication is session-based. Example: `true`. |
| `confirmData` | object | No | The additional confirmation data required for authentication. |
| `confirmData.email` | string (email), nullable | No | The email address to confirm the user's identity. Example: `Randall63@hotmail.com`. |
| `confirmData.first` | boolean, nullable | No | Specifies whether this is the first access to the user's account. Example: `true`. |
| `confirmData.key` | string, nullable | No | The unique confirmation key for validating user identity. Example: `some text`. |
| `recaptchaType` | string | No | The type of CAPTCHA validation used. One of: `Default`, `AndroidV2`, `iOSV2`, `hCaptcha`. Example: `Default`. |
| `recaptchaResponse` | string, nullable | No | The user's response to the CAPTCHA challenge. Example: `some text`. |
| `culture` | string, nullable | No | The culture code for localization during authentication. Example: `some text`. |

Example:

```json
{
  "userName": "some text",
  "password": "vfmf2vO1Kp",
  "passwordHash": "some text",
  "provider": "some text",
  "accessToken": "some text",
  "serializedProfile": "some text",
  "code": "some text",
  "codeOAuth": "some text",
  "session": true,
  "confirmData": {
    "email": "Randall63@hotmail.com",
    "first": true,
    "key": "some text"
  },
  "recaptchaType": "Default",
  "recaptchaResponse": "some text",
  "culture": "some text"
}
```

## Responses

### 200 — Authentication data

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The authentication token parameters. |
| `response.token` | string, nullable | No | The authentication token. Example: `abcde12345`. |
| `response.expires` | string (date-time) | No | The token expiration time. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.sms` | boolean | No | Specifies if the authentication code is sent by SMS or not. Example: `false`. |
| `response.phoneNoise` | string, nullable | No | The phone number. Example: ``. |
| `response.tfa` | boolean | No | Specifies if the two-factor application is used or not. Example: `false`. |
| `response.tfaKey` | string, nullable | No | The two-factor authentication key. Example: ``. |
| `response.confirmUrl` | string (uri), nullable | No | The confirmation email URL. Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 400 — userName, password or passworHash is empty

### 429 — Too many login attempts. Please try again later

