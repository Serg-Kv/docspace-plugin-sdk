# Save the additional white label settings

`POST /api/2.0/settings/rebranding/additional`

Saves the additional white label settings specified in the request.

Operation ID: `saveAdditionalWhiteLabelSettings`

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
| `settings` | object | No | The additional white label settings. |
| `settings.startDocsEnabled` | boolean | No | Specifies if the sample documents are displayed or hidden. Example: `true`. |
| `settings.helpCenterEnabled` | boolean | No | Specifies if the Help Center link is available or not. Example: `true`. |
| `settings.feedbackAndSupportEnabled` | boolean | No | Specifies if the "Feedback & Support" link is available or not. Example: `true`. |
| `settings.userForumEnabled` | boolean | No | Specifies if the user forum is available or not. Example: `true`. |
| `settings.videoGuidesEnabled` | boolean | No | Specifies if the Video Guides link is available or not. Example: `true`. |
| `settings.licenseAgreementsEnabled` | boolean | No | Specifies if the License Agreements link is available or not. Example: `true`. |
| `settings.lastModified` | string (date-time) | No | Example: `2008-04-10T06:30:00.0000000+04:00`. |

Example:

```json
{
  "settings": {
    "startDocsEnabled": true,
    "helpCenterEnabled": true,
    "feedbackAndSupportEnabled": true,
    "userForumEnabled": true,
    "videoGuidesEnabled": true,
    "licenseAgreementsEnabled": true,
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

### 400 — Settings is empty

### 401 — Unauthorized

### 403 — No permissions to perform this action

