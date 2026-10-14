# Get the recommended quota

`GET /api/2.0/portal/quota/right`

Returns the recommended quota for the current portal.

Operation ID: `getRightQuota`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — Recommended portal quota

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The current tenant quota. |
| `response.tenantId` | integer (int32) | No | The tenant ID. Example: `1234`. |
| `response.name` | string, nullable | No | The tenant name. Example: `Default`. |
| `response.price` | number (double) | No | The tenant price. Example: `10`. |
| `response.priceCurrencySymbol` | string, nullable | No | The tenant price currency symbol. Example: `some text`. |
| `response.priceISOCurrencySymbol` | string, nullable | No | The tenant price three-character ISO 4217 currency symbol. Example: `some text`. |
| `response.productId` | string, nullable | No | The tenant product ID. Example: `9846`. |
| `response.serviceName` | string, nullable | No | The service name. Example: `some text`. |
| `response.visible` | boolean | No | Specifies if the tenant quota is visible or not. Example: `true`. |
| `response.wallet` | boolean | No | Specifies if the tenant quota applies to the wallet or not Example: `true`. |
| `response.dueDate` | string (date-time), nullable | No | The quota due date. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.features` | string, nullable | No | The tenant quota features. Example: `some text`. |
| `response.maxFileSize` | integer (int64) | No | The tenant maximum file size. Example: `26214400`. |
| `response.maxTotalSize` | integer (int64) | No | The tenant maximum total size. Example: `9223372036854776000`. |
| `response.countUser` | integer (int32) | No | The number of portal users. Example: `1234`. |
| `response.countRoomAdmin` | integer (int32) | No | The number of portal room administrators. Example: `1234`. |
| `response.usersInRoom` | integer (int32) | No | The number of room users. Example: `1234`. |
| `response.countRoom` | integer (int32) | No | The number of rooms. Example: `1234`. |
| `response.nonProfit` | boolean | No | Specifies if the tenant quota is nonprofit or not. Example: `true`. |
| `response.trial` | boolean | No | Specifies if the tenant quota is trial or not. Example: `true`. |
| `response.free` | boolean | No | Specifies if the tenant quota is free or not. Example: `true`. |
| `response.update` | boolean | No | Specifies if the tenant quota is updated or not. Example: `true`. |
| `response.audit` | boolean | No | Specifies if the audit trail is available or not. Example: `true`. |
| `response.docsEdition` | boolean | No | Specifies if ONLYOFFICE Docs is included in the tenant quota or not. Example: `true`. |
| `response.ldap` | boolean | No | Specifies if the LDAP settings are available or not. Example: `true`. |
| `response.sso` | boolean | No | Specifies if the SSO settings are available or not. Example: `true`. |
| `response.statistic` | boolean | No | Specifies if the statistics settings are available or not. Example: `true`. |
| `response.branding` | boolean | No | Specifies if the branding settings are available or not. Example: `true`. |
| `response.customization` | boolean | No | Specifies if the customization settings are available or not. Example: `true`. |
| `response.lifetime` | boolean | No | Specifies if the license has the lifetime settings or not. Example: `true`. |
| `response.custom` | boolean | No | Specifies if the custom domain URL is available or not. Example: `true`. |
| `response.restore` | boolean | No | Specifies if the restore is enabled or not. Example: `true`. |
| `response.oauth` | boolean | No | Specifies if Oauth is available or not. Example: `true`. |
| `response.contentSearch` | boolean | No | Specifies if the content search is available or not. Example: `true`. |
| `response.thirdParty` | boolean | No | Specifies if the third-party accounts linking is available or not. Example: `true`. |
| `response.year` | boolean | No | Specifies if the tenant quota is yearly subscription or not. Example: `true`. |
| `response.countFreeBackup` | integer (int32) | No | The number of free backups within a month. Example: `1234`. |
| `response.backup` | boolean | No | Specifies if the backup anabled as a wallet service or not. Example: `true`. |
| `response.countAIAgent` | integer (int32) | No | The number of AI agents. Example: `1234`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

