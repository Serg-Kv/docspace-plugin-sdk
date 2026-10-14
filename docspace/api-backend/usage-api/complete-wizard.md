# Complete the Wizard settings

`PUT /api/2.0/settings/wizard/complete`

Completes the Wizard settings.

Operation ID: `completeWizard`

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
| `email` | string (email), nullable | Yes | The user's email address for authentication and communication. Example: `Sydney_Roberts4@hotmail.com`. |
| `passwordHash` | string, nullable | Yes | The hashed representation of the user's password. Example: `some text`. |
| `lng` | string, nullable | No | The user's preferred interface language code. Example: `some text`. |
| `timeZone` | string, nullable | No | The user's time zone identifier. Example: `some text`. |
| `amiId` | string, nullable | No | The Amazon Machine Image (AMI) identifier. Example: `some text`. |
| `subscribeFromSite` | boolean | No | Specifies whether the user opted in for site communications. Example: `true`. |

Example:

```json
{
  "email": "Sydney_Roberts4@hotmail.com",
  "passwordHash": "some text",
  "lng": "some text",
  "timeZone": "some text",
  "amiId": "some text",
  "subscribeFromSite": true
}
```

## Responses

### 200 — Wizard settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The Wizard settings. |
| `response.completed` | boolean | No | Specifies if the Wizard settings are completed or not Example: `true`. |
| `response.lastModified` | string (date-time) | No | Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 400 — Incorrect email address/The password is empty

### 401 — Unauthorized

### 402 — You must enter a license key or license key is not correct or license expired or user quota does not match the license

