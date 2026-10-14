# Send congratulations

`POST /api/2.0/portal/sendcongratulations`

Sends congratulations to the user after registering a portal.

Operation ID: `sendCongratulations`

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `Userid` | query | string (uuid) | Yes | The user ID to receive the congratulatory message. Example: `75a5f745-f697-4418-b38d-0fe0d277e258`. |
| `Key` | query | string | Yes | The template identifier or email configuration key. Example: `some text`. |

## Responses

### 200 — Ok

### 403 — No permissions to perform this action

