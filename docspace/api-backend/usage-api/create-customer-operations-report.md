# Start the customer operations report generation

`POST /api/2.0/portal/payment/customer/operationsreport`

Starts generating a customer operations report as an "xlsx" file and saves it in Documents.

Operation ID: `createCustomerOperationsReport`

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
| `startDate` | string (date-time), nullable | No | The report start date. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `endDate` | string (date-time), nullable | No | The report end date. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `participantName` | string, nullable | No | The participant name. Example: `some text`. |
| `credit` | boolean, nullable | No | Specifies whether to include credit operations in the report. Example: `true`. |
| `debit` | boolean, nullable | No | Specifies whether to include debit operations in the report. Example: `true`. |

Example:

```json
{
  "startDate": "2008-04-10T06:30:00.0000000+04:00",
  "endDate": "2008-04-10T06:30:00.0000000+04:00",
  "participantName": "some text",
  "credit": true,
  "debit": true
}
```

## Responses

### 200 — Ok

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The Document Builder task parameters. |
| `response.id` | string, nullable | Yes | The Document Builder task ID. Example: `9846`. |
| `response.error` | string, nullable | Yes | The error message occurred during the document building process. Example: `some text`. |
| `response.percentage` | integer (int32) | Yes | The progress percentage of the document building process. Example: `1234`. |
| `response.isCompleted` | boolean | Yes | Specifies whether the document building process is completed or not. Example: `true`. |
| `response.status` | string | Yes | [Created - Created, Running - Running, Completed - Completed, Canceled - Canceled, Failted - Failted] One of: `Created`, `Running`, `Completed`, `Canceled`, `Failted`. Example: `Created`. |
| `response.resultFileId` | any, nullable | Yes | The result file ID. |
| `response.resultFileName` | string, nullable | Yes | The result file name. Example: `some text`. |
| `response.resultFileUrl` | string, nullable | Yes | The result file URL. Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

