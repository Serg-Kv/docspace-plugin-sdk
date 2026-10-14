# Get portal capabilities

`GET /api/2.0/capabilities`

Returns the information about portal capabilities.

Operation ID: `getPortalCapabilities`

## Responses

### 200 — Portal capabilities

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The capabilities parameters. |
| `response.ldapEnabled` | boolean | Yes | Specifies if the LDAP settings are enabled or not. Example: `false`. |
| `response.ldapDomain` | string, nullable | No | The LDAP domain. Example: `some text`. |
| `response.providers` | string[], nullable | Yes | The list of providers. |
| `response.ssoLabel` | string, nullable | Yes | The SP login label. Example: ``. |
| `response.oauthEnabled` | boolean | Yes | Specifies if OAuth is enabled or not. Example: `true`. |
| `response.ssoUrl` | string (uri), nullable | Yes | The SSO URL. If this parameter is empty, then the SSO settings are disabled. Example: ``. |
| `response.identityServerEnabled` | boolean | Yes | Specifies if identity server is enabled or not Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

