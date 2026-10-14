# Get the default SSO settings

`GET /api/2.0/settings/ssov2/default`

Returns the default portal SSO settings.

Operation ID: `getDefaultSsoSettingsV2`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — Default SSO settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The SSO portal settings. |
| `response.lastModified` | string (date-time) | No | Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.enableSso` | boolean, nullable | No | Specifies if the SSO settings are enabled or not. Example: `true`. |
| `response.idpSettings` | object | No | The SSO IdP settings. |
| `response.idpSettings.entityId` | string, nullable | No | The entity ID. Example: `some text`. |
| `response.idpSettings.ssoUrl` | string, nullable | No | The SSO URL. Example: `some text`. |
| `response.idpSettings.ssoBinding` | string, nullable | No | The SSO binding. Example: `some text`. |
| `response.idpSettings.sloUrl` | string, nullable | No | The SLO URL. Example: `some text`. |
| `response.idpSettings.sloBinding` | string, nullable | No | The SLO binding. Example: `some text`. |
| `response.idpSettings.nameIdFormat` | string, nullable | No | The name ID format. Example: `some text`. |
| `response.idpCertificates` | object[], nullable | No | The list of the IdP certificates. |
| `response.idpCertificates.selfSigned` | boolean | No | Specifies if a certificate is self-signed or not. Example: `true`. |
| `response.idpCertificates.crt` | string, nullable | No | The CRT certificate file. Example: `some text`. |
| `response.idpCertificates.key` | string, nullable | No | The certificate key. Example: `some text`. |
| `response.idpCertificates.action` | string, nullable | No | The certificate action. Example: `some text`. |
| `response.idpCertificates.domainName` | string, nullable | No | The certificate domain name. Example: `some text`. |
| `response.idpCertificates.startDate` | string (date-time) | No | The certificate start date. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.idpCertificates.expiredDate` | string (date-time) | No | The certificate expiration date. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.idpCertificateAdvanced` | object | No | The IdP advanced certificate parameters. |
| `response.idpCertificateAdvanced.verifyAlgorithm` | string, nullable | No | The certificate verification algorithm. Example: `some text`. |
| `response.idpCertificateAdvanced.verifyAuthResponsesSign` | boolean | No | Specifies if the signatures of the SAML authentication responses sent to SP will be verified or not. Example: `true`. |
| `response.idpCertificateAdvanced.verifyLogoutRequestsSign` | boolean | No | Specifies if the signatures of the SAML logout requests sent to SP will be verified or not. Example: `true`. |
| `response.idpCertificateAdvanced.verifyLogoutResponsesSign` | boolean | No | Specifies if the signatures of the SAML logout responses sent to SP will be verified or not. Example: `true`. |
| `response.idpCertificateAdvanced.decryptAlgorithm` | string, nullable | No | The certificate decryption algorithm. Example: `some text`. |
| `response.idpCertificateAdvanced.decryptAssertions` | boolean | No | Specifies if the assertions will be decrypted or not. Example: `true`. |
| `response.spLoginLabel` | string, nullable | No | The SP login label. Example: `some text`. |
| `response.spCertificates` | object[], nullable | No | The list of the SP certificates. |
| `response.spCertificates.selfSigned` | boolean | No | Specifies if a certificate is self-signed or not. Example: `true`. |
| `response.spCertificates.crt` | string, nullable | No | The CRT certificate file. Example: `some text`. |
| `response.spCertificates.key` | string, nullable | No | The certificate key. Example: `some text`. |
| `response.spCertificates.action` | string, nullable | No | The certificate action. Example: `some text`. |
| `response.spCertificates.domainName` | string, nullable | No | The certificate domain name. Example: `some text`. |
| `response.spCertificates.startDate` | string (date-time) | No | The certificate start date. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.spCertificates.expiredDate` | string (date-time) | No | The certificate expiration date. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.spCertificateAdvanced` | object | No | The SP advanced certificate parameters. |
| `response.spCertificateAdvanced.signingAlgorithm` | string, nullable | No | The certificate signing algorithm. Example: `some text`. |
| `response.spCertificateAdvanced.signAuthRequests` | boolean | No | Specifies if SP will sign the SAML authentication requests sent to IdP or not. Example: `true`. |
| `response.spCertificateAdvanced.signLogoutRequests` | boolean | No | Specifies if SP will sign the SAML logout requests sent to IdP or not. Example: `true`. |
| `response.spCertificateAdvanced.signLogoutResponses` | boolean | No | Specifies if SP will sign the SAML logout responses sent to IdP or not. Example: `true`. |
| `response.spCertificateAdvanced.encryptAlgorithm` | string, nullable | No | The certificate encryption algorithm. Example: `some text`. |
| `response.spCertificateAdvanced.decryptAlgorithm` | string, nullable | No | The certificate decryption algorithm. Example: `some text`. |
| `response.spCertificateAdvanced.encryptAssertions` | boolean | No | Specifies if the assertions will be encrypted or not. Example: `true`. |
| `response.fieldMapping` | object | No | The SSO field mapping. |
| `response.fieldMapping.firstName` | string, nullable | No | The first name. Example: `Winfield`. |
| `response.fieldMapping.lastName` | string, nullable | No | The last name. Example: `Wyman`. |
| `response.fieldMapping.email` | string (email), nullable | No | The email address. Example: `Sydney_Roberts4@hotmail.com`. |
| `response.fieldMapping.title` | string, nullable | No | The title. Example: `legacy_1080p_small_wooden_mouse`. |
| `response.fieldMapping.location` | string, nullable | No | The location. Example: `001 Schroeder Run, New Tabithaport, Colombia`. |
| `response.fieldMapping.phone` | string, nullable | No | The phone number. Example: `some text`. |
| `response.hideAuthPage` | boolean | No | Specifies if the authentication page will be hidden or not. Example: `true`. |
| `response.usersType` | integer (int32) | No | The user type. Example: `1234`. |
| `response.disableEmailVerification` | boolean | No | Specifies if the email verification is disabled or not. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

