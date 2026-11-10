---
comments: true
tags:
  - Available On Premises
---

## Backup Code MFA

Backup Codes are a backup secondary authentication method that allow users to complete login when primary MFA methods (like TOTP, SMS, or Push Notification) are unavailable. Each user is issued a set of single-use, pre-generated codes for secure fallback access.

### Preconditions

- Backup Codes must be enabled in the assigned Auth Profile.

- The user must have generated and securely stored their backup codes from their My Profile section.



## Steps to Generate Backup Codes

- Log in to the ZTAA Console.

- Navigate to Account → Backup Codes.

- Click on Generate Backup Codes.

- A new list of single-use codes will be generated.

- Download or copy these codes and store them securely.

<!-- paste image path according to url name "backup-login-profile.png" -->





## Steps to Use 


- Navigate to the ZTAA login page.

- Enter your username and complete Primary Authentication (e.g., password, AD, or SAML).

- On the Secondary Authentication screen, select Backup Codes

<!-- paste image path according to url name "backup-login-select.png" -->

- Enter any unused recovery code from your list.

<!-- paste image path according to url name "backup-login-code.png" -->

- Click Continue to complete the login process.



**Note:** Each recovery code can only be used once. Once all codes are used, users must generate a new set from their My Profile → Account → Backup Codes.


