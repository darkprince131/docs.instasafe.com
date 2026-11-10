---
comments: true
tags:
  - Available On Premises
  - Available On Cloud
---

Multi-factor authentication (MFA) is a layered approach to securing physical and logical access where a system requires a user to present a combination of two or more different authenticators to verify a user’s identity for login. MFA increases security because even if one authenticator becomes compromised, unauthorized users will be unable to meet the second authentication requirement and will not be able to access the targeted physical space or computer system.

A typical MFA login would require the user to present some combination of the following:

• Something you know: like a password or Personal Identification Number (PIN).

• Something you have: like a smart card, mobile token, or hardware token.

• Something you are: some form of biometric factor (facial recognition, fingerprint, palm print or voice recognition).

## Enabling Multi-Factor Authentication in InstaSafe ZTAA

Two factor authentication can be enabled under Auth profile tab in Identity Management section of the ZTAA Admin console. The Admin can set a Global Auth Profile which will enable different primary authentication methods as well as secondary authentication for all users. Exclusion to Auth profiles can also  be created for individual user or user groups to customize the authentication profile as per the organisation requirements.

The various methods of available Primary Authentication are:

* Password: Logging into ZTAA directly via password.
* AD: Logging into ZTAA via Active Directory credentials.
* SAML: Logging into ZTAA via organization's identity provider.

The various methods of available Secondary Authentication are:

* Email OTP
* SMS OTP
* TOTP from [InstaSafe Authenticator app](https://docs.instasafe.com/Zero%20Trust%20Application%20Access/026authenticator/) or any other Authenticator app
* Push Notification from InstaSafe Authenticator app
* Security Question & Answer
* WebAuthn (FIDO2/Passkey)

## Configure Global Authentication Profile 

1. Go to Auth Profiles tab under Identity Management.

2. Edit the Global Authentication profile.

3. Select the Primary mode of Authentication. In the Secondary Authentication enable OTP.

4. You may choose IP based filtering if you require else this can be skipped. This can be enabled later.

5. Set additional policies as per your organization's requirement. Click on Update once done.

The global Authentication Profile is now set.

The method to set up 2FA in ZTAA a can also be seen in the video given below.

![GlobalAuthprofile](../static/ztaa/AuthProfileConfig.gif)

## Adding Individual and Group level Exclusions

The Global auth profile is applicable on all users except for whom specific exclusions are provided. Exclusions can be configured for individuals as well as for user groups. Individual User exclusion takes precedence over Group exclusions which in turn precedes Global Auth Profile.

1. Under the Exclusion Tab select individual or Group based upon your requirements.

2. Add a new exclusion rule. Add User/User group to the rule. 

3. Select primary and secondary method of authentication.

4. Create additional rules as per your organization's requirement.

5. Click on Update once Done.

## Enabling Multi-Factor Authentication for Users that have Integrated InstaSafe Authenticator App

For users who have registered with the Instasafe Authenticator app, Two Factor Authentication will be automatically enabled for them even if it is not explicitly enabled for them in the Auth profile. This feature can be enabled for the specific tenant by the Admin.


