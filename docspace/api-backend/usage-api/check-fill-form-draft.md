# Check the form draft filling

`POST /api/2.0/files/masterform/{fileId}/checkfillformdraft`

Checks if the current file is a form draft which can be filled out.

Operation ID: `checkFillFormDraft`

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `fileId` | path | integer (int32) | Yes | The file ID of the form draft. Example: `9846`. |

## Request body

The parameters for checking the form draft filling.

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `version` | integer (int32) | Yes | The file version of the form draft. Example: `1234`. |
| `action` | string, nullable | No | The action with the form draft. Example: `some text`. |
| `requestView` | boolean | No | Specifies whether to request the form for viewing or not. Example: `true`. |
| `requestEmbedded` | boolean | No | Specifies whether to request an embedded form or not. Example: `true`. |

Example:

```json
{
  "version": 1234,
  "action": "some text"
}
```

## Responses

### 200 — Link to the form

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | string | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 403 — You don't have enough permission to view the file

