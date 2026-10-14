# Check the document service URL

`PUT /api/2.0/files/docservice`

Checks the document service location URL.

Operation ID: `checkDocServiceUrl`

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
| `docServiceUrl` | string, nullable | Yes | The ONLYOFFICE Docs URL address. Example: `some text`. |
| `docServiceUrlInternal` | string, nullable | No | The ONLYOFFICE Docs URL address in the local private network. Example: `some text`. |
| `docServiceUrlPortal` | string, nullable | No | The ONLYOFFICE Docs URL address. Example: `some text`. |
| `docServiceSignatureSecret` | string, nullable | No | The signature secret of the ONLYOFFICE Docs. Example: `some text`. |
| `docServiceSignatureHeader` | string, nullable | No | The signature header of the ONLYOFFICE Docs. Example: `some text`. |
| `docServiceSslVerification` | boolean, nullable | No | Specifies if the SSL verification of the ONLYOFFICE Docs is enabled or not. Example: `true`. |

Example:

```json
{
  "docServiceUrl": "some text",
  "docServiceUrlInternal": "some text",
  "docServiceUrlPortal": "some text",
  "docServiceSignatureSecret": "some text",
  "docServiceSignatureHeader": "some text",
  "docServiceSslVerification": true
}
```

## Responses

### 200 — Document service information: the Document Server address, the Document Server address in the local private network, the Community Server address

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The document service URL parameters. |
| `response.version` | string, nullable | Yes | The version of the document service. Example: `some text`. |
| `response.docServiceUrlApi` | string, nullable | Yes | The document service URL API. Example: `some text`. |
| `response.docServiceUrl` | string, nullable | Yes | The document service URL. Example: `some text`. |
| `response.docServicePreloadUrl` | string, nullable | Yes | The URL used to preload the document service scripts. Example: `some text`. |
| `response.docServiceUrlInternal` | string, nullable | Yes | The internal document service URL. Example: `some text`. |
| `response.docServicePortalUrl` | string, nullable | Yes | The document service portal URL. Example: `some text`. |
| `response.docServiceSignatureHeader` | string, nullable | Yes | The document service signature header. Example: `some text`. |
| `response.docServiceSslVerification` | boolean | Yes | Specifies if the document service SSL verification is enabled. Example: `true`. |
| `response.isDefault` | boolean | Yes | Specifies if the document service is default. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 400 — Invalid input urls/Mixed Active Content is not allowed. HTTPS address for Document Server is required

### 401 — Unauthorized

