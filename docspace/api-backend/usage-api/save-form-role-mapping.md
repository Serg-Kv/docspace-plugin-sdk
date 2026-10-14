# Save form role mapping

`POST /api/2.0/files/file/{fileId}/formrolemapping`

Saves the form role mapping.

Operation ID: `saveFormRoleMapping`

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
| `fileId` | path | string | Yes |  |

## Request body

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `formId` | integer (int32) | Yes | The form ID. Example: `1234`. |
| `roles` | object[], nullable | Yes | The collection of roles. |
| `roles.roomId` | integer (int32) | No | The room ID. Example: `9846`. |
| `roles.roleName` | string, nullable | No | The role name. Example: `some text`. |
| `roles.roleColor` | string, nullable | No | The role color. Example: `some text`. |
| `roles.userId` | string (uuid) | No | The user ID. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |
| `roles.sequence` | integer (int32) | No | The role sequence. Example: `1234`. |
| `roles.submitted` | boolean | No | Specifies if the role was submitted or not. Example: `true`. |
| `roles.openedAt` | string (date-time) | No | The date and time when the role was opened. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `roles.submissionDate` | string (date-time) | No | The date and time when the role was submitted. Example: `2008-04-10T06:30:00.0000000+04:00`. |

Example:

```json
{
  "formId": 1234,
  "roles": [
    {
      "roomId": 9846,
      "roleName": "some text",
      "roleColor": "some text",
      "userId": "aae1e103-bca5-9fa1-ba8c-42058b4abf28",
      "sequence": 1234,
      "submitted": true,
      "openedAt": "2008-04-10T06:30:00.0000000+04:00",
      "submissionDate": "2008-04-10T06:30:00.0000000+04:00"
    }
  ]
}
```

## Responses

### 200 — Updated information about form role mappings

### 401 — Unauthorized

### 403 — You do not have enough permissions to edit the file

