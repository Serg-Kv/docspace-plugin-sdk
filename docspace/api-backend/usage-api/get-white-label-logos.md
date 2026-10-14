# Get the white label logos

`GET /api/2.0/settings/whitelabel/logos`

Returns the white label logos.

Operation ID: `getWhiteLabelLogos`

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `IsDark` | query | boolean | No | Specifies if the white label logo is for the dark theme or not. Example: `true`. |
| `IsDefault` | query | boolean | No | Specifies if the logo is for a default tenant or not. Example: `true`. |

## Responses

### 200 — White label logos

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.type` | integer (int32) | No | One of: `1`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9`, `10`, `11`, `12`, `13`, `14`, `15`, and 1 more. |
| `response.name` | string, nullable | No | The white label file name. Example: `Winfield Upton`. |
| `response.size` | object | No |  |
| `response.size.aspectRatio` | boolean | No | Example: `true`. |
| `response.size.fillArea` | boolean | No | Example: `true`. |
| `response.size.greater` | boolean | No | Example: `true`. |
| `response.size.height` | integer (int32) | No |  |
| `response.size.ignoreAspectRatio` | boolean | No | Example: `true`. |
| `response.size.isPercentage` | boolean | No | Example: `true`. |
| `response.size.less` | boolean | No | Example: `true`. |
| `response.size.limitPixels` | boolean | No | Example: `true`. |
| `response.size.width` | integer (int32) | No |  |
| `response.size.x` | integer (int32) | No | Example: `1234`. |
| `response.size.y` | integer (int32) | No | Example: `1234`. |
| `response.path` | object | No | The white label item path parameters. |
| `response.path.light` | string, nullable | No | The path to the light theme logo. Example: `some text`. |
| `response.path.dark` | string, nullable | No | The path to the dark theme logo. Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

