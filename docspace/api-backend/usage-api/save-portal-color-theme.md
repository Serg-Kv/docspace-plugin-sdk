# Save a color theme

`PUT /api/2.0/settings/colortheme`

Saves the portal color theme specified in the request.

Operation ID: `savePortalColorTheme`

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
| `theme` | object | No | The custom color theme settings. |
| `theme.id` | integer (int32) | No | The custom color theme ID. Example: `1`. |
| `theme.name` | string, nullable | No | The custom color theme name. Example: `blue`. |
| `theme.main` | object | No | The custom color theme color parameters. |
| `theme.main.accent` | string, nullable | No | The accent color. Example: `#4781D1`. |
| `theme.main.buttons` | string, nullable | No | The button color. Example: `#5299E0`. |
| `theme.text` | object | No | The custom color theme color parameters. |
| `theme.text.accent` | string, nullable | No | The accent color. Example: `#4781D1`. |
| `theme.text.buttons` | string, nullable | No | The button color. Example: `#5299E0`. |
| `selected` | integer (int32), nullable | No | Specifies the optional value indicating the selected custom color theme. Example: `1234`. |

Example:

```json
{
  "theme": {
    "id": 1,
    "name": "blue",
    "main": {
      "accent": "#4781D1",
      "buttons": "#5299E0"
    },
    "text": {
      "accent": "#4781D1",
      "buttons": "#5299E0"
    }
  },
  "selected": 1234
}
```

## Responses

### 200 — Portal theme settings

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

### 401 — Unauthorized

