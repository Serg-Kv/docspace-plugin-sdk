# Save the tenant quota settings

`PUT /api/2.0/settings/tenantquotasettings`

Saves the tenant quota settings specified in the request to the current portal.

Operation ID: `setTenantQuotaSettings`

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
| `tenantId` | integer (int32) | Yes | The ID of the tenant whose quota is being configured. Example: `1234`. |
| `quota` | integer (int64) | No | The storage quota limit in bytes allocated to the tenant. Example: `1234`. |

Example:

```json
{
  "tenantId": 1234,
  "quota": 1234
}
```

## Responses

### 200 — Tenant quota settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The tenant quota settings. |
| `response.enableQuota` | boolean | No | Specifies if the tenant quota is enabled or not. Example: `true`. |
| `response.quota` | integer (int64) | No | The tenant quota. Example: `1234`. |
| `response.lastRecalculateDate` | string (date-time), nullable | No | The date of the last tenant quota recalculation. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.lastModified` | string (date-time) | No | Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 402 — Your pricing plan does not support this option

### 405 — Not available

