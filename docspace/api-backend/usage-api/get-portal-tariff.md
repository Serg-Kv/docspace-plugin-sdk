# Get a portal tariff

`GET /api/2.0/portal/tariff`

Returns the current portal tariff.

Operation ID: `getPortalTariff`

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
| `refresh` | query | boolean | No | The value indicating whether the current portal tariff information should be refreshed. Example: `true`. |

## Responses

### 200 — Current portal tariff

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The tariff parameters. |
| `response.id` | integer (int32) | No | The tariff ID. Example: `9846`. |
| `response.state` | string | No | The tariff state. One of: `Trial`, `Paid`, `Delay`, `NotPaid`. Example: `Trial`. |
| `response.dueDate` | string (date-time) | Yes | The tariff due date. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.delayDueDate` | string (date-time) | No | The tariff delay due date. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.licenseDate` | string (date-time) | No | The tariff license date. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.customerId` | string, nullable | No | The tariff customer ID. Example: `some text`. |
| `response.quotas` | object[], nullable | Yes | The list of tariff quotas. |
| `response.quotas.id` | integer (int32) | No | The quota ID. Example: `9846`. |
| `response.quotas.quantity` | integer (int32) | No | The quota quantity. Example: `1234`. |
| `response.quotas.wallet` | boolean | No | The quota applies to the wallet or not Example: `true`. |
| `response.quotas.dueDate` | string (date-time), nullable | No | The quota due date. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.quotas.nextQuantity` | integer (int32), nullable | No | The quota next quantity. Example: `1234`. |
| `response.quotas.state` | string | No | The quota state. One of: `Active`, `Overdue`. Example: `Active`. |
| `response.overdueQuotas` | object[], nullable | No | The list of overdue tariff quotas. |
| `response.overdueQuotas.id` | integer (int32) | No | The quota ID. Example: `9846`. |
| `response.overdueQuotas.quantity` | integer (int32) | No | The quota quantity. Example: `1234`. |
| `response.overdueQuotas.wallet` | boolean | No | The quota applies to the wallet or not Example: `true`. |
| `response.overdueQuotas.dueDate` | string (date-time), nullable | No | The quota due date. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.overdueQuotas.nextQuantity` | integer (int32), nullable | No | The quota next quantity. Example: `1234`. |
| `response.overdueQuotas.state` | string | No | The quota state. One of: `Active`, `Overdue`. Example: `Active`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

