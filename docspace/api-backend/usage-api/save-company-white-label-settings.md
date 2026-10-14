# Save the company white label settings

`POST /api/2.0/settings/rebranding/company`

Saves the company white label settings specified in the request.

Operation ID: `saveCompanyWhiteLabelSettings`

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
| `settings` | object | No | The company white label settings. |
| `settings.companyName` | string, nullable | No | The company name. Example: `some text`. |
| `settings.site` | string (uri), nullable | No | The company site. Example: `some text`. |
| `settings.email` | string (email), nullable | No | The company email address. Example: `Sydney_Roberts4@hotmail.com`. |
| `settings.address` | string, nullable | No | The company address. Example: `some text`. |
| `settings.phone` | string (tel), nullable | No | The company phone number. Example: `some text`. |
| `settings.IsLicensor` | boolean | No | Specifies if a company is a licensor or not. Example: `true`. |
| `settings.hideAbout` | boolean | No | Specifies if the About page is visible or not Example: `true`. |
| `settings.lastModified` | string (date-time) | No | Example: `2008-04-10T06:30:00.0000000+04:00`. |

Example:

```json
{
  "settings": {
    "companyName": "some text",
    "site": "some text",
    "email": "Sydney_Roberts4@hotmail.com",
    "address": "some text",
    "phone": "some text",
    "IsLicensor": true,
    "hideAbout": true,
    "lastModified": "2008-04-10T06:30:00.0000000+04:00"
  }
}
```

## Responses

### 200 — Boolean value: true if the operation is successful

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | boolean | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 400 — Argument is empty or invalid

### 401 — Unauthorized

### 403 — No permissions to perform this action

