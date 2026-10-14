# Send the mention message

`POST /api/2.0/files/file/{fileId}/sendeditornotify`

Sends a message to the users who are mentioned in the file with the ID specified in the request.

Operation ID: `sendEditorNotify`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `fileId` | path | integer (int32) | Yes | The file ID with the mention message. Example: `9846`. |

## Request body

The mention message.

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `actionLink` | object | No | The config parameter which contains the information about the action in the document that will be scrolled to. |
| `actionLink.action` | object | No | The information about the action in the document that will be scrolled to. |
| `actionLink.action.data` | string, nullable | No | The action data that will be scrolled to. Example: `some text`. |
| `actionLink.action.type` | string, nullable | No | The action type. Example: `some text`. |
| `emails` | string[], nullable | No | A list of emails that will receive the mention message. |
| `message` | string, nullable | No | The mention message. Example: `some text`. |

Example:

```json
{
  "actionLink": {
    "action": {
      "data": "some text",
      "type": "some text"
    }
  },
  "emails": [
    "some text"
  ],
  "message": "some text"
}
```

## Responses

### 200 — List of access rights information

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.user` | string, nullable | No | The name of the user the document will be shared with. Example: `some text`. |
| `response.permissions` | string, nullable | No | The access rights for the user with the name above. Can be "Full Access", "Read Only", or "Deny Access". Example: `some text`. |
| `response.isLink` | boolean | No | Specifies whether to change the user icon to the link icon. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

