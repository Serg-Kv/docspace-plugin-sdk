# Get the payment settings

`GET /api/2.0/settings/payment`

Returns the portal payment settings.

Operation ID: `getPaymentSettings`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — Payment settings: sales email, feedback and support URL, link to pay for a portal, Standalone or not, current license, maximum quota quantity

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The payment settings parameters. |
| `response.salesEmail` | string, nullable | Yes | The email address for sales inquiries and support. Example: `some text`. |
| `response.feedbackAndSupportUrl` | string, nullable | No | The URL for accessing the feedback and support resources. Example: `some text`. |
| `response.buyUrl` | string, nullable | Yes | The URL for purchasing or upgrading the product. Example: `some text`. |
| `response.standalone` | boolean | Yes | Indicates whether the system is running in standalone mode. Example: `true`. |
| `response.currentLicense` | object | Yes | The current license information. |
| `response.currentLicense.trial` | boolean | Yes | Specifies whether the license is trial or not. Example: `true`. |
| `response.currentLicense.dueDate` | string (date-time) | Yes | The date when the license expires. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.max` | integer (int32) | Yes | The maximum quota quantity. Example: `1234`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

