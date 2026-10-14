# Get third-party accounts

`GET /api/2.0/people/thirdparty/providers`

Returns a list of the available third-party accounts.

Operation ID: `getThirdPartyAuthProviders`

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `inviteView` | query | boolean | No | Specifies whether to return providers that are available for invitation links, i.e. the user can login or register through these providers. Example: `true`. |
| `settingsView` | query | boolean | No | Specifies whether to display the provider settings in a pop-up window (true) or redirect them to the desktop application (false). Example: `true`. |
| `clientCallback` | query | string | No | The method that is called after authentication. Example: `some text`. |
| `fromOnly` | query | string | No | The provider name if a response is required only from this provider. Example: `some text`. |

## Responses

### 200 — List of third-party accounts

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.provider` | string, nullable | Yes | The account provider. Example: `some text`. |
| `response.url` | string (uri), nullable | Yes | The account URL. Example: `some text`. |
| `response.linked` | boolean | Yes | Specifies if an account is linked with other profiles or not. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

