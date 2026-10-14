# Save the mail domain settings

`POST /api/2.0/settings/maildomainsettings`

Saves the mail domain settings specified in the request to the portal.

Operation ID: `saveMailDomainSettings`

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
| `type` | string | Yes | The type of the tenant trusted domains. One of: `None`, `Custom`, `All`. Example: `None`. |
| `domains` | string[], nullable | Yes | The list of authorized email domains that are considered trusted. |
| `inviteUsersAsVisitors` | boolean | Yes | Specifies the default permission level for the invited users (visitors or not). Example: `true`. |

Example:

```json
{
  "type": "None",
  "domains": [
    "some text"
  ],
  "inviteUsersAsVisitors": true
}
```

## Responses

### 200 — Message about the result of saving the mail domain settings

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

### 401 — Unauthorized

