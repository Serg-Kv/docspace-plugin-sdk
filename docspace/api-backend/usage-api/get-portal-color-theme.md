# Get a color theme

`GET /api/2.0/settings/colortheme`

Returns the portal color theme.

Operation ID: `getPortalColorTheme`

## Responses

### 200 — Settings of the portal themes

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The custom color themes settings. |
| `response.themes` | object[], nullable | No | The list of the custom color themes. |
| `response.themes.id` | integer (int32) | No | The custom color theme ID. Example: `1`. |
| `response.themes.name` | string, nullable | No | The custom color theme name. Example: `blue`. |
| `response.themes.main` | object | No | The custom color theme color parameters. |
| `response.themes.main.accent` | string, nullable | No | The accent color. Example: `#4781D1`. |
| `response.themes.main.buttons` | string, nullable | No | The button color. Example: `#5299E0`. |
| `response.themes.text` | object | No | The custom color theme color parameters. |
| `response.themes.text.accent` | string, nullable | No | The accent color. Example: `#4781D1`. |
| `response.themes.text.buttons` | string, nullable | No | The button color. Example: `#5299E0`. |
| `response.selected` | integer (int32) | No | Specifies whether the custom color theme is selected. Example: `1234`. |
| `response.limit` | integer (int32) | No | The maximum number of the custom color themes. Example: `1234`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

