# Remind a user password

`POST /api/2.0/people/password`

Reminds a password to the user using the email address specified in the request.

Operation ID: `sendUserPassword`

## Request body

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `email` | string (email) | Yes | The user email address. Example: `Sydney_Roberts4@hotmail.com`. |
| `recaptchaType` | string | No | The type of CAPTCHA validation used. One of: `Default`, `AndroidV2`, `iOSV2`, `hCaptcha`. Example: `Default`. |
| `recaptchaResponse` | string, nullable | No | The user's response to the CAPTCHA challenge. Example: `some text`. |

Example:

```json
{
  "email": "Sydney_Roberts4@hotmail.com",
  "recaptchaType": "Default",
  "recaptchaResponse": "some text"
}
```

## Responses

### 200 — Email with the password

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

### 403 — No permissions to perform this action

