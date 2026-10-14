# Get the document service URL

`GET /api/2.0/files/docservice`

Returns the URL address of the connected editors.

Operation ID: `getDocServiceUrl`

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `version` | query | boolean | No | Specifies whether to return the editor version or not. Example: `true`. |

## Responses

### 200 — The document service URL with the editor version specified

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

