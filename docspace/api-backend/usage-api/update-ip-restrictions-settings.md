# Update the IP restriction settings

`PUT /api/2.0/settings/iprestrictions/settings`

Updates the IP restriction settings with the parameters specified in the request.

Operation ID: `updateIpRestrictionsSettings`

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
| `ipRestrictions` | object[], nullable | Yes | The list of IP restriction addresses. |
| `ipRestrictions.ip` | string, nullable | Yes | Example: `some text`. |
| `ipRestrictions.forAdmin` | boolean | No | Example: `true`. |
| `enable` | boolean, nullable | No | Specifies whether to enable IP restrictions or not. Example: `true`. |

Example:

```json
{
  "ipRestrictions": [
    {
      "ip": "some text",
      "forAdmin": true
    }
  ],
  "enable": true
}
```

## Responses

### 200 — Updated IP restriction settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The parameters for configuring new IP restriction settings. |
| `response.ipRestrictions` | object[], nullable | Yes | The list of IP restriction addresses. |
| `response.ipRestrictions.ip` | string, nullable | Yes | Example: `some text`. |
| `response.ipRestrictions.forAdmin` | boolean | No | Example: `true`. |
| `response.enable` | boolean, nullable | No | Specifies whether to enable IP restrictions or not. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

