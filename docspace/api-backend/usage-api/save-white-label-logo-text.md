# Save the white label logo text settings

`POST /api/2.0/settings/whitelabel/logotext/save`

Saves the white label logo text specified in the request.

Operation ID: `saveWhiteLabelLogoText`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `IsDark` | query | boolean | No | Specifies if the white label logo is for the dark theme or not. Example: `true`. |
| `IsDefault` | query | boolean | No | Specifies if the logo is for a default tenant or not. Example: `true`. |

## Request body

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `logoText` | string, nullable | No | The text to display alongside or in place of the logo. Example: `some text`. |
| `logo` | object[], nullable | No | The white label tenant IDs with their logos (light or dark). |
| `logo.key` | string, nullable | No | Example: `some text`. |
| `logo.value` | object | No | The request parameters for the theme-specific logo configurations. |
| `logo.value.light` | string, nullable | No | The URL or base64-encoded image data for the light theme logo. Example: `some text`. |
| `logo.value.dark` | string, nullable | No | The URL or base64-encoded image data for the dark theme logo. Example: `some text`. |

Example:

```json
{
  "logoText": "some text",
  "logo": [
    {
      "key": "some text",
      "value": {
        "light": "some text",
        "dark": "some text"
      }
    }
  ]
}
```

## Responses

### 200 — Boolean value: true if the operation is sucessful

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

### 401 — Unauthorized

### 403 — No permissions to perform this action

