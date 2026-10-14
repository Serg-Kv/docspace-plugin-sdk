# Save the Documents Firebase device token

`POST /api/2.0/settings/push/docregisterdevice`

Saves the Firebase device token specified in the request for the Documents application.

Operation ID: `docRegisterPusnNotificationDevice`

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
| `firebaseDeviceToken` | string, nullable | No | The Firebase device token. Example: `some text`. |
| `isSubscribed` | boolean | No | Specifies whether the user is subscribed to the push notifications or not. Example: `true`. |

Example:

```json
{
  "firebaseDeviceToken": "some text",
  "isSubscribed": true
}
```

## Responses

### 200 — FireBase user

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The Firebase user parameters. |
| `response.id` | integer (int32) | No | The Firebase user ID. Example: `9846`. |
| `response.userId` | string (uuid) | No | The user ID. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |
| `response.tenantId` | integer (int32) | No | The tenant ID. Example: `1234`. |
| `response.firebaseDeviceToken` | string, nullable | No | The Firebase device token. Example: `some text`. |
| `response.application` | string, nullable | No | The Firebase application. Example: `some text`. |
| `response.isSubscribed` | boolean, nullable | No | Specifies if the user is subscribed to the push notifications or not. Example: `true`. |
| `response.tenant` | object | No | The database tenant parameters. |
| `response.tenant.id` | integer (int32) | No | The tenant ID. Example: `9846`. |
| `response.tenant.name` | string, nullable | No | The tenant name. Example: `Winfield Upton`. |
| `response.tenant.alias` | string, nullable | No | The tenant alias. Example: `some text`. |
| `response.tenant.mappedDomain` | string, nullable | No | Mapped domain Example: `some text`. |
| `response.tenant.version` | integer (int32) | No | The tenant version. Example: `1234`. |
| `response.tenant.version_Changed` | string (date-time), nullable | No | The Version_changed field. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.tenant.versionChanged` | string (date-time) | No | The date and time when the version was changed. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.tenant.language` | string, nullable | No | The tenant language. Example: `some text`. |
| `response.tenant.timeZone` | string, nullable | No | The tenant time zone. Example: `some text`. |
| `response.tenant.trustedDomainsRaw` | string, nullable | No | The tenant trusted domains raw. Example: `some text`. |
| `response.tenant.trustedDomainsEnabled` | string | No | The type of the tenant trusted domains. One of: `None`, `Custom`, `All`. Example: `None`. |
| `response.tenant.status` | string | No | The tenant status. One of: `Active`, `Suspended`, `RemovePending`, `Transfering`, `Restoring`, `Migrating`, `Encryption`. Example: `Active`. |
| `response.tenant.statusChanged` | string (date-time), nullable | No | The date and time when the tenant status was changed. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.tenant.statusChangedHack` | string (date-time) | No | The hacked date and time when the tenant status was changed. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.tenant.creationDateTime` | string (date-time) | No | The tenant creation date. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.tenant.ownerId` | string (uuid), nullable | No | The tenant owner ID. Example: `75a5f745-f697-4418-b38d-0fe0d277e258`. |
| `response.tenant.paymentId` | string, nullable | No | The tenant payment ID. Example: `some text`. |
| `response.tenant.industry` | string | No | The tenant industry. One of: `Other`, `Accounting`, `AdvertisingMarketingPR`, `Banking`, `Consulting`, `Design`, `Education`, `Environment`, `FinancialServices`, `HealthCare`, `IT`, `Legal`, `Manufacturing`, `PublicSector`, `Publishing`, and 2 more. Example: `Other`. |
| `response.tenant.lastModified` | string (date-time) | No | The date and time when the tenant was last modified. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.tenant.calls` | boolean | No | Specifies if the calls are available for the current tenant or not. Example: `true`. |
| `response.tenant.partner` | object | No | The database tenant partner parameters. |
| `response.tenant.partner.tenantId` | integer (int32) | No | The tenant ID. Example: `1234`. |
| `response.tenant.partner.partnerId` | string, nullable | No | The partner ID. Example: `some text`. |
| `response.tenant.partner.affiliateId` | string, nullable | No | The affiliate ID. Example: `some text`. |
| `response.tenant.partner.campaign` | string, nullable | No | The tenant partner campaign. Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

