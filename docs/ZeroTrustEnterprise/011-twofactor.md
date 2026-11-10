---
comments: true
---
### Enabling Two Factor Authentication

Two factor authentication can be enabled under Auth profile tab in Identity management Section.  The admin can set a global auth profile which will enable different primary authentication methods as well secondary authentication for all users. Exclusion to Auth profiles can also  be created for individual user or user group.

The various method of primary Authentication available are

* Password- Logging into ZTAA directly via password.
* AD-  Logging into ZTAA via AD credentials.
* SAML and Oauth- Logging into ZTAA via organization's SSO.

The various method of Secondary Authentication availabe are

* OTP
* Captcha

### To configure Global Auth Profile 

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

### Enabling Two Factor Authentication for Users that have Integrated InstaSafe Authenticator App

For users who have registered with the Instasafe Authenticator app, Two Factor Authentication will be automatically enabled for them even if it is not explicitly enabled for them in the Auth profile. This feature can be enabled for the specific tenant by the Admin.


