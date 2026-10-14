# Get the company white label settings

`GET /api/2.0/settings/rebranding/company`

Returns the company white label settings.

Operation ID: `getCompanyWhiteLabelSettings`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — Company white label settings

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

### 401 — Unauthorized

