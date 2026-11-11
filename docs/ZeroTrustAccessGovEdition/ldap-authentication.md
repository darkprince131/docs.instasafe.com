---
comments: true
---
LDAP (Lightweight Directory Access Protocol) authentication is a method of validating the identity of users by checking their credentials against an LDAP directory.

The the platform supports LDAP as an authentication method along with TOTP as a mechanism for multi-factor authentication.


**Prerequisites:**

- A Service account should be created in the tenant.

### Setting up InstaSafe ZTNA as a LDAP Identity Provider

1. Click on 'Identity Management' in the left menu. Click on 'Identity Provider' from the top menu.

2. Click on the '+' icon and select 'LDAP'

3. Give a name in the 'IDP Name' textbox.

4. Select a service account from the 'Select Service Account' dropdown.

5. Enable the 'Enable Multi-Factor Authentication' toggle, if multi-factor authentication is to be enabled for LDAP authentication.

6. Click on the 'Submit' button. Once LDAP profile is successfully created, there will be a new field called Bind DN. Review the value populated for the Bind DN.

7. Select the User Groups if LDAP Authentication is to be enabled for any specific User Groups.

**Note:** Only one LDAP Identity Provider profile can be created per tenant.1. 

Please refer the below video to configure InstaSafe ZTNA as a LDAP Identity Provider.

![ldapconfiguration](../static/ztaa/LDAP_config.gif)


### Configuration on the client

Configurations may vary depending on the client trying to authenticate with LDAP. The basic details are provided.

1. Bind DN which available in the InstaSafe ZTNA LDAP IDP profile will be the Bind DN for authenticating any requests coming to InstaSafe ZTNA. So in the client set the Bind DN to the Bind DN from InstaSafe ZTNA LDAP IDP profile and the password will be the service account password.

2. Base DN will be DC=instasafe,DC=io,o=<tenant name>￼

3. InstaSafe ZTNA supports two username attributes : uid and sAMAccountName. These are optional fields and can be configured if needed.

### Multi-factor authentication with LDAP

1. InstaSafe ZTNA supports TOTP as of now for MFA. OTP and Push notification is not supoprted as of now.

2. Users can add TOTP along with their password separating with “,”

3. In the Identity Provider section of InstaSafe ZTNA, select the LDAP IDP and enable the 'Enable Multi-Factor Authentication' toggle.

Please refer the below video for LDAP authentication with InstaSafe ZTNA from OpenVPN client.

![ldapmfa](../static/ztaa/LDAP_MFA.gif)

## Authenticating users against your own directory

The feature described above is the platform acting **as** an LDAP server, answering binds
from other systems. Authenticating your own users **against** Active Directory or OpenLDAP is
a separate feature with separate capabilities, configured under Authentication Profiles.

The limits noted on this page - TOTP as the second factor, and one profile per tenant - apply
to the identity-provider feature only. They do not apply to users signing in against the
organisation's own directory.

| | |
|---|---|
| **The query** | A Base DN scopes the search and an administrator-written LDAP filter decides which directory entries the profile covers. See [Directory Queries and the Login Identifier](directory-query.md). |
| **The login identifier** | Set per profile as the Username Attribute - sAMAccountName or User Principal Name for Active Directory, UID for OpenLDAP. Several profiles can cover one directory, so an account held under more than one identifier form can sign in with either. |
| **Second factors** | Users authenticating against a directory are challenged from the full set: TOTP, push, SMS OTP, email OTP, a FIDO2 key, or a backup code. See [Directory Authentication and the MFA Methods Available With It](directory-mfa.md). |
