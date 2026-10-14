# Send a message to the administrator

`POST /api/2.0/settings/sendadmmail`

Sends a message to the administrator email when unauthorized users encounter issues accessing DocSpace.

Operation ID: `sendAdminMail`

## Request body

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `message` | string, nullable | Yes | The content of the administrator message to be sent. Example: `some text`. |
| `email` | string (email), nullable | Yes | Email Example: `Sydney_Roberts4@hotmail.com`. |
| `culture` | string, nullable | No | Culture Example: `some text`. |
| `recaptchaType` | string | No | The type of CAPTCHA validation used. One of: `Default`, `AndroidV2`, `iOSV2`, `hCaptcha`. Example: `Default`. |
| `recaptchaResponse` | string, nullable | No | The user's response to the CAPTCHA challenge. Example: `some text`. |

Example:

```json
{
  "message": "some text",
  "email": "Sydney_Roberts4@hotmail.com",
  "culture": "some text",
  "recaptchaType": "Default",
  "recaptchaResponse": "some text"
}
```

## Responses

### 200 — Message about the result of sending a message

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

### 400 — Incorrect email or message text is empty

### 429 — Request limit is exceeded

