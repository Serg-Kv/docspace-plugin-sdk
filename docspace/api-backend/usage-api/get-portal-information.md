# Get a portal

`GET /api/2.0/portal`

Returns the current portal information.

Operation ID: `getPortalInformation`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — Current portal information

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The tenant parameters. |
| `response.affiliateId` | string, nullable | No | The affiliate ID. Example: `some text`. |
| `response.tenantAlias` | string, nullable | No | The tenant alias. Example: `some text`. |
| `response.calls` | boolean | No | Specifies if the calls are available for this tenant or not. Example: `true`. |
| `response.campaign` | string, nullable | No | The tenant campaign. Example: `some text`. |
| `response.creationDateTime` | string (date-time) | No | The tenant creation date and time. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.hostedRegion` | string, nullable | No | The hosted region. Example: `some text`. |
| `response.tenantId` | integer (int32) | No | The tenant ID. Example: `1234`. |
| `response.industry` | string | No | The tenant industry. One of: `Other`, `Accounting`, `AdvertisingMarketingPR`, `Banking`, `Consulting`, `Design`, `Education`, `Environment`, `FinancialServices`, `HealthCare`, `IT`, `Legal`, `Manufacturing`, `PublicSector`, `Publishing`, and 2 more. Example: `Other`. |
| `response.language` | string, nullable | No | The tenant language. Example: `some text`. |
| `response.lastModified` | string (date-time) | No | The date and time when the tenant was last modified. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.mappedDomain` | string, nullable | No | The tenant mapped domain. Example: `some text`. |
| `response.name` | string, nullable | No | The tenant name. Example: `Winfield Upton`. |
| `response.ownerId` | string (uuid) | No | The tenant owner ID. Example: `75a5f745-f697-4418-b38d-0fe0d277e258`. |
| `response.paymentId` | string, nullable | No | The tenant payment ID. Example: `some text`. |
| `response.spam` | boolean | No | Specifies if the ONLYOFFICE newsletter is allowed or not. Example: `true`. |
| `response.status` | string | No | The tenant status. One of: `Active`, `Suspended`, `RemovePending`, `Transfering`, `Restoring`, `Migrating`, `Encryption`. Example: `Active`. |
| `response.statusChangeDate` | string (date-time) | No | The date and time when the tenant status was changed. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.timeZone` | string, nullable | No | The tenant time zone. Example: `some text`. |
| `response.trustedDomains` | string[], nullable | No | The list of tenant trusted domains. |
| `response.trustedDomainsRaw` | string, nullable | No | The tenant trusted domains in the string format. Example: `some text`. |
| `response.trustedDomainsType` | string | No | The type of the tenant trusted domains. One of: `None`, `Custom`, `All`. Example: `None`. |
| `response.version` | integer (int32) | No | The tenant version Example: `1234`. |
| `response.versionChanged` | string (date-time) | No | The date and time when the tenant version was changed. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.region` | string, nullable | No | The tenant AWS region. Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

