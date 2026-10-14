# Save the DNS settings

`PUT /api/2.0/settings/dns`

Saves the DNS settings specified in the request to the current portal.

Operation ID: `saveDnsSettings`

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
| `dnsName` | string, nullable | No | The DNS (Domain Name System) configuration name. Example: `some text`. |
| `enable` | boolean | No | Specifies whether the DNS settings are enabled. Example: `true`. |

Example:

```json
{
  "dnsName": "some text",
  "enable": true
}
```

## Responses

### 200 — Message about changing DNS

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

### 400 — Invalid domain name/incorrect length of doman name

### 401 — Unauthorized

### 402 — Your pricing plan does not support this option

### 405 — Method not allowed

