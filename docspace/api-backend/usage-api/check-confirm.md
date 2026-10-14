# Open confirmation email URL

`POST /api/2.0/authentication/confirm`

Opens a confirmation email URL to validate a certain action (employee invitation, portal removal, phone activation, etc.).

Operation ID: `checkConfirm`

## Request body

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `key` | string, nullable | No | The email validation key. Example: `some text`. |
| `emplType` | string | No | The user type. One of: `All`, `RoomAdmin`, `Guest`, `DocSpaceAdmin`, `User`. Example: `All`. |
| `email` | string (email), nullable | No | The email address. Example: `Sydney_Roberts4@hotmail.com`. |
| `encEmail` | string, nullable | No | The encrypted email address. Example: `some text`. |
| `uiD` | string (uuid), nullable | No | The user ID. Example: `75a5f745-f697-4418-b38d-0fe0d277e258`. |
| `type` | string | No | The confirmation email type. One of: `EmpInvite`, `LinkInvite`, `PortalSuspend`, `PortalContinue`, `PortalRemove`, `DnsChange`, `PortalOwnerChange`, `Activation`, `EmailChange`, `EmailActivation`, `PasswordChange`, `ProfileRemove`, `PhoneActivation`, `PhoneAuth`, `Auth`, and 4 more. Example: `EmpInvite`. |
| `first` | string, nullable | No | Specifies whether it is the first time account access or not. Example: `some text`. |
| `roomId` | string, nullable | No | The room ID. Example: `9846`. |

Example:

```json
{
  "key": "some text",
  "emplType": "All",
  "email": "Sydney_Roberts4@hotmail.com",
  "encEmail": "some text",
  "uiD": "75a5f745-f697-4418-b38d-0fe0d277e258",
  "type": "EmpInvite",
  "first": "some text",
  "roomId": "9846"
}
```

## Responses

### 200 — Validation result: Ok, Invalid, or Expired

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The confirmation parameters. |
| `response.result` | string | Yes | [Ok - Ok, Invalid - Invalid, Expired - Expired, TariffLimit - Tariff limit, UserExisted - User existed, UserExcluded - User excluded, QuotaFailed - Quota failed] One of: `Ok`, `Invalid`, `Expired`, `TariffLimit`, `UserExisted`, `UserExcluded`, `QuotaFailed`. Example: `Ok`. |
| `response.roomId` | string, nullable | No | The confirmation room ID. Example: `9846`. |
| `response.title` | string, nullable | No | The confirmation title. Example: `legacy_1080p_small_wooden_mouse`. |
| `response.email` | string, nullable | No | The confirmation email. Example: `Sydney_Roberts4@hotmail.com`. |
| `response.isAgent` | boolean | No | The confirmation is agent. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

