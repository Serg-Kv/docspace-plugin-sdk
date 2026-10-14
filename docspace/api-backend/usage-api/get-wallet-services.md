# Get wallet services

`GET /api/2.0/portal/payment/walletservices`

Returns the available wallet services.

Operation ID: `getWalletServices`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — List of available wallet services

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.id` | integer (int32) | Yes | The quota ID. Example: `9846`. |
| `response.title` | string, nullable | Yes | The quota title. Example: `legacy_1080p_small_wooden_mouse`. |
| `response.price` | object | Yes | The price parameters. |
| `response.price.value` | number (double), nullable | No | The price value. Example: `10`. |
| `response.price.currencySymbol` | string, nullable | No | The currency symbol. Example: `some text`. |
| `response.price.isoCurrencySymbol` | string, nullable | No | The three-character ISO 4217 currency symbol. Example: `some text`. |
| `response.nonProfit` | boolean | Yes | Specifies if the quota is nonprofit or not. Example: `true`. |
| `response.free` | boolean | Yes | Specifies if the quota is free or not. Example: `true`. |
| `response.trial` | boolean | Yes | Specifies if the quota is trial or not. Example: `true`. |
| `response.features` | object[], nullable | Yes | The list of tenant quota features. |
| `response.features.id` | string, nullable | No | The ID of the tenant quota feature. Example: `9846`. |
| `response.features.title` | string, nullable | No | The title of the tenant quota feature. Example: `legacy_1080p_small_wooden_mouse`. |
| `response.features.image` | string, nullable | No | The image URL of the tenant quota feature. Example: `some text`. |
| `response.features.value` | any, nullable | No | The value of the tenant quota feature. |
| `response.features.type` | string, nullable | No | The type of the tenant quota feature. Example: `some text`. |
| `response.features.used` | object | No | The used space parameters of the tenant quota feature. |
| `response.features.used.value` | any, nullable | Yes | The used space value. |
| `response.features.used.title` | string, nullable | No | The used space title. Example: `legacy_1080p_small_wooden_mouse`. |
| `response.features.priceTitle` | string, nullable | No | The price title of the tenant quota feature. Example: `some text`. |
| `response.usersQuota` | object | No | The tenant entity quota settings. |
| `response.usersQuota.enableQuota` | boolean | No | Specifies if the quota is enabled for the tenant entity or not. Example: `true`. |
| `response.usersQuota.defaultQuota` | integer (int64) | No | The default quota of the tenant entity. Example: `1234`. |
| `response.usersQuota.lastRecalculateDate` | string (date-time), nullable | No | The date of the last quota recalculation. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.roomsQuota` | object | No | The tenant entity quota settings. |
| `response.roomsQuota.enableQuota` | boolean | No | Specifies if the quota is enabled for the tenant entity or not. Example: `true`. |
| `response.roomsQuota.defaultQuota` | integer (int64) | No | The default quota of the tenant entity. Example: `1234`. |
| `response.roomsQuota.lastRecalculateDate` | string (date-time), nullable | No | The date of the last quota recalculation. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.aiAgentsQuota` | object | No | The tenant entity quota settings. |
| `response.aiAgentsQuota.enableQuota` | boolean | No | Specifies if the quota is enabled for the tenant entity or not. Example: `true`. |
| `response.aiAgentsQuota.defaultQuota` | integer (int64) | No | The default quota of the tenant entity. Example: `1234`. |
| `response.aiAgentsQuota.lastRecalculateDate` | string (date-time), nullable | No | The date of the last quota recalculation. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.tenantCustomQuota` | object | No | The tenant quota settings. |
| `response.tenantCustomQuota.enableQuota` | boolean | No | Specifies if the tenant quota is enabled or not. Example: `true`. |
| `response.tenantCustomQuota.quota` | integer (int64) | No | The tenant quota. Example: `1234`. |
| `response.tenantCustomQuota.lastRecalculateDate` | string (date-time), nullable | No | The date of the last tenant quota recalculation. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.tenantCustomQuota.lastModified` | string (date-time) | No | Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.dueDate` | string (date-time), nullable | No | The due date. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

