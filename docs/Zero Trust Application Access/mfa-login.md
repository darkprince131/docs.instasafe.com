---
comments: true
tags:
  - Available On Premises
  - Available On Cloud
---

## SMS OTP Authentication ##

SMS OTP (One-Time Password via SMS) is a commonly used secondary authentication method that sends a unique numeric code to the user’s registered mobile number. It adds a secure second layer of verification after the primary login. 

### Preconditions:

- The user's mobile number must be registered and verified in ZTAA.
 
- SMS OTP must be enabled in the assigned Auth Profile.



### Steps to Use:

- Navigate to the ZTAA login page.

- Enter your username and complete Primary Authentication.

- On the Secondary Authentication screen, select SMS OTP.

- An OTP is sent via SMS to the registered mobile number.

- Enter the OTP in the provided input field.

- Click Verify to complete login.




## Email OTP Authentication ##

Email OTP is a secondary authentication method where a time-limited code is sent to the user's registered email address to validate their identity.

### Preconditions:

- The user must have a verified email address in ZTAA.

- Email OTP must be enabled in the assigned Auth Profile.



### Steps to Use:

- Visit the ZTAA login page.

- Enter your username and complete Primary Authentication.

- On the Secondary Authentication screen, choose Email OTP.

- Check your email inbox for the OTP message from ZTAA.

- Enter the received OTP in the login screen.

- Click Continue to complete login.






## TOTP Authentication (Time-based One-Time Password) ##

TOTP is a secure MFA method that uses time-based tokens generated in an authenticator app such as InstaSafe Authenticator, Google Authenticator, or Microsoft Authenticator.

### Preconditions:

- The user must pair their ZTAA account with a supported TOTP app during setup.

- TOTP must be enabled in the assigned Auth Profile.



### Steps to Use:

- Go to the ZTAA login page.
 
- Enter your username and complete Primary Authentication.
 
- On the Secondary Authentication screen, select TOTP.
 
- Open the authenticator app on your mobile device.
 
- Retrieve the 6-digit TOTP for your ZTAA account.

- Enter the code in the TOTP field and click on continue.





## Push Notification Authentication ##

Push Notification provides a user-friendly and secure authentication experience by sending a login approval request to the user’s registered mobile device via the InstaSafe Authenticator app.

### Preconditions:

- InstaSafe Authenticator app must be installed and linked to the user's ZTAA account.

- Push Notification must be enabled in the assigned Auth Profile.

- Mobile device should have internet connectivity and notifications enabled.



### Steps to Use:

- Navigate to the ZTAA login page.
 
- Enter your username and complete Primary Authentication.
 
- A Push Notification is automatically sent to your registered mobile device.
 
- Open the InstaSafe Authenticator app.

- Tap Approve to complete the authentication process.

