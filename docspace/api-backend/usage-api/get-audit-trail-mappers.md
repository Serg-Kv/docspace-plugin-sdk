# Get audit trail mappers

`GET /api/2.0/security/audit/mappers`

Returns the mappers for the audit trail types.

Operation ID: `getAuditTrailMappers`

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `productType` | query | string | No | The type of product related to the audit trail. One of: `Documents`, `Login`, `Settings`, `Contacts`. Example: `Documents`. |
| `moduleType` | query | string | No | The location associated with the audit trail. One of: `None`, `Files`, `Folders`, `DocumentsSettings`, `Rooms`, `Settings`, `Contacts`, `Agents`. Example: `None`. |

## Responses

### 200 — Audit trail mappers

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

