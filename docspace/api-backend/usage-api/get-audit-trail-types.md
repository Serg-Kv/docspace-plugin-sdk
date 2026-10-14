# Get audit trail types

`GET /api/2.0/security/audit/types`

Returns all the available audit trail types.

Operation ID: `getAuditTrailTypes`

## Responses

### 200 — Audit trail types

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

