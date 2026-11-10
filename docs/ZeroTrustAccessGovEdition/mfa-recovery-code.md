---
comments: true
tags:
  - Available On Premises
---

Recovery codes are a critical component of Multi-Factor Authentication (MFA) that provide a secure backup method for account access in scenarios where the primary MFA device of the user is not available (e.g., lost or inaccessible device). Each recovery code is unique, one-time-use and should be stored securely by the user.

###Features

**One-Time Use:** Each recovery code can only be used once to access the account.

**Backup for MFA:** Enables account access if primary MFA methods are unavailable.

**Regeneration Option:** Users can regenerate new recovery codes if needed, invalidating the old ones.

**Secure Delivery:** Codes are displayed only once and must be securely saved by the user.

###How it Works

1. **Generation of Recovery Codes:** As illustrated in the video below, user needs to browse to the 'My Profile' section and in the page click on the 'Generate Backup Codes'. The Backup Codes will be generated and displayed to the user. User needs to click on the 'Confirm and Download Backup Codes' button to activate them. The Backup Codes will be downloaded to the user device which must be stored securely. 

2. **Using Recovery Code for MFA:** Administrator needs to enable the Recovery Code MFA option by checking the 'Backup Code' option in the Authentication Profile -> Allowed Secondary Authentications. Users when they try to login to the ZTAA platform will be provided the option of 'Backup Code' as a MFA factor. Users can make use of the Recovery code from the file downloaded earlier in 'My Profile'.


![](../static/ztaa/Recovery_Code.gif)

