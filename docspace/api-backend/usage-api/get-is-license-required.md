# Request a license

`GET /api/2.0/settings/license/required`

Requests a portal license if necessary.

Operation ID: `getIsLicenseRequired`

## Responses

### 200 — Boolean value: true if the license is required

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | boolean | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

