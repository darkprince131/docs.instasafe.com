---
comments: true
search:
  exclude: true
---

**Superseded.** This is the previous version of this page, kept for comparison. The current
page is [LDAP Authentication](ldap-authentication.md).

LDAP (Lightweight Directory Access Protocol) authentication is a method of validating the identity of users by checking their credentials against an LDAP directory.

The ZTAA platform supports LDAP as an authentication method along with TOTP as a mechanism for multi-factor authentication.


**Prerequisites:**

- A Service account should be created in the tenant.

### Setting up ZTAA as a LDAP Identity Provider

1. Click on 'Identity Management' in the left menu. Click on 'Identity Provider' from the top menu.

2. Click on the '+' icon and select 'LDAP'

3. Give a name in the 'IDP Name' textbox.

4. Select a service account from the 'Select Service Account' dropdown.

5. Enable the 'Enable Multi-Factor Authentication' toggle, if multi-factor authentication is to be enabled for LDAP authentication.

6. Click on the 'Submit' button. Once LDAP profile is successfully created, there will be a new field called Bind DN. Review the value populated for the Bind DN.

7. Select the User Groups if LDAP Authentication is to be enabled for any specific User Groups.

**Note:** Only one LDAP Identity Provider profile can be created per tenant.1. 

Please refer the below video to configure ZTAA as a LDAP Identity Provider.

![ldapconfiguration](../static/ztaa/LDAP_config.gif)


### Configuration on the client

Configurations may vary depending on the client trying to authenticate with LDAP. The basic details are provided.

1. Bind DN which available in the ZTAA LDAP IDP profile will be the Bind DN for authenticating any requests coming to ZTAA. So in the client set the Bind DN to the Bind DN from ZTAA LDAP IDP profile and the password will be the service account password.

2. Base DN will be DC=instasafe,DC=io,o=<tenant name>￼

3. ZTAA supports two username attributes : uid and sAMAccountName. These are optional fields and can be configured if needed.

### Multi-factor authentication with LDAP

1. ZTAA supports TOTP as of now for MFA. OTP and Push notification is not supoprted as of now.

2. Users can add TOTP along with their password separating with “,”

3. In the Identity Provider section of ZTAA, select the LDAP IDP and enable the 'Enable Multi-Factor Authentication' toggle.

Please refer the below video for LDAP authentication with ZTAA from OpenVPN client.

![ldapmfa](../static/ztaa/LDAP_MFA.gif)

