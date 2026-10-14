# Get the customer operations

`GET /api/2.0/portal/payment/customer/operations`

Returns the report of customer operations from the accounting service.

Operation ID: `getCustomerOperations`

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
| `startDate` | query | string (date-time) | No | The report start date. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `endDate` | query | string (date-time) | No | The report end date. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `participantName` | query | string | No | The participant name. Example: `some text`. |
| `credit` | query | boolean | No | Specifies whether to include credit operations in the report. The default value is true. Example: `true`. |
| `debit` | query | boolean | No | Specifies whether to include debit operations in the report. The default value is true. Example: `true`. |
| `offset` | query | integer (int32) | No | The number of items to skip for pagination. The default value is 0. Example: `1234`. |
| `limit` | query | integer (int32) | No | The maximum number of items to return for pagination. The default value is 25. Example: `1234`. |

## Responses

### 200 — The customer operations

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | Represents a report containing a collection of operations. |
| `response.collection` | object[], nullable | No | A collection of operations. |
| `response.collection.date` | object | No | The API date and time parameters. |
| `response.collection.date.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.collection.date.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.collection.service` | string, nullable | No | The service related to the operation. Example: `some text`. |
| `response.collection.description` | string, nullable | No | The brief operation description. Example: `some text`. |
| `response.collection.details` | string, nullable | No | The detailed information about the operation. Example: `some text`. |
| `response.collection.serviceUnit` | string, nullable | No | The service unit. Example: `some text`. |
| `response.collection.quantity` | integer (int32) | No | The quantity of the service used. Example: `1234`. |
| `response.collection.currency` | string, nullable | No | The three-character ISO 4217 currency symbol of the operation. Example: `some text`. |
| `response.collection.credit` | number (double) | No | The credit amount of the operation. |
| `response.collection.debit` | number (double) | No | The debit amount of the operation. |
| `response.collection.participantName` | string, nullable | No | The participant original name. Example: `some text`. |
| `response.collection.participantDisplayName` | string, nullable | No | The participant display name. Example: `some text`. |
| `response.offset` | integer (int32) | No | The report data offset. Example: `1234`. |
| `response.limit` | integer (int32) | No | The report data limit. Example: `1234`. |
| `response.totalQuantity` | integer (int32) | No | The total quantity of operations in the report. Example: `1234`. |
| `response.totalPage` | integer (int32) | No | The total number of pages in the report. Example: `1234`. |
| `response.currentPage` | integer (int32) | No | The current page number of the report. Example: `1234`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 403 — No permissions to perform this action

