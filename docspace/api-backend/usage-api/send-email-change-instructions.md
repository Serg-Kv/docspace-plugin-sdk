# Send instructions to change email

`POST /api/2.0/people/email`

Sends a message to the user email with the instructions to change the email address connected to the portal.

Operation ID: `sendEmailChangeInstructions`

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
| `userId` | string, nullable | No | The user ID. Example: `9846`. |
| `disable` | boolean, nullable | No | Specifies whether to disable a user or not. Example: `true`. |
| `email` | string (email), nullable | No | The user email address. Example: `Sydney_Roberts4@hotmail.com`. |
| `isUser` | boolean, nullable | No | Specifies if this is a guest or a user. Example: `true`. |
| `firstName` | string, nullable | No | The user first name. Example: `Winfield`. |
| `lastName` | string, nullable | No | The user last name. Example: `Wyman`. |
| `department` | string[] (uuid), nullable | No | The list of the user departments. |
| `title` | string, nullable | No | The user title. Example: `legacy_1080p_small_wooden_mouse`. |
| `location` | string, nullable | No | The user location. Example: `001 Schroeder Run, New Tabithaport, Colombia`. |
| `sex` | string | No | The user sex. One of: `Female`, `Male`. Example: `Female`. |
| `birthday` | object | No | The API date and time parameters. |
| `birthday.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `birthday.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `worksfrom` | object | No | The API date and time parameters. |
| `worksfrom.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `worksfrom.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `comment` | string, nullable | No | The user comment. Example: `some text`. |
| `contacts` | object[], nullable | No | The list of the user contacts. |
| `contacts.type` | string, nullable | No | The contact type. Example: `GTalk`. |
| `contacts.value` | string, nullable | No | The contact value. Example: `my@gmail.com`. |
| `files` | string, nullable | No | The user avatar photo URL. Example: `some text`. |
| `spam` | boolean, nullable | No | Specifies if tips, updates and offers are allowed to be sent to the user or not. Example: `true`. |

Example:

```json
{
  "userId": "9846",
  "disable": true,
  "email": "Sydney_Roberts4@hotmail.com",
  "isUser": true,
  "firstName": "Winfield",
  "lastName": "Wyman",
  "department": [
    "75a5f745-f697-4418-b38d-0fe0d277e258"
  ],
  "title": "legacy_1080p_small_wooden_mouse",
  "location": "001 Schroeder Run, New Tabithaport, Colombia",
  "sex": "Female",
  "birthday": {},
  "worksfrom": {},
  "comment": "some text",
  "contacts": [
    {
      "type": "GTalk",
      "value": "my@gmail.com"
    }
  ],
  "files": "some text",
  "spam": true
}
```

## Responses

### 200 — Message text

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

### 400 — Incorrect userId or email

### 401 — Unauthorized

### 403 — No permissions to perform this action

### 404 — User not found

