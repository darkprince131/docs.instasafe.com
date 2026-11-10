---
comments: true
---
# SAML Authentication

**SAML 2.0 configuration with AZURE AD**

SAML Authentication will be configured where InstaSafe ISA shall serve as the Service Provider (SP) and Entra ID shall serve as the Identity Provider (IdP).

- Log in to portal.azure.com and select Microsoft Entra ID
- Click on ‘Enterprise applications’ in the dashboard panel on the left
- Click on ‘New application’

![](../static/ISA/SAML/SAML.jpg)

- Click on ‘Create your own application’
- Provide a custom name like instasafeisa and click ‘Create’

![](../static/ISA/SAML/SAML1.jpg)

- Expand the newly created Application
- Click on ‘Single sign-on’ and then ‘Set up single sign-on’

![](../static/ISA/SAML/SAML2.jpg)

- Fill up the details of your SP (InstaSafe ISA)
    -   Identifier (Entity ID): http://companyname.instasafe.com
    -   Reply URL (ACS URL): https://companyname.instasafe.com/api/saml/acs
    -   Logout URL: https://companyname.instasafe.com/api/saml/acs

![](../static/ISA/SAML/SAML3.jpg)

- Download the Metadata from Entra ID (or copy all required values like Certificate, Entity ID, ACS URL, etc.) to be used later

![](../static/ISA/SAML/SAML4.jpg)

- Login to the InstaSafe ISA Portal  with Admin credentials
- Navigate to Authentication Profile >> SAML
- Click on ‘Add’

![](../static/ISA/SAML/SAML5.jpg)

- The values from Entra ID (copied earlier) can be manually entered here, or automatically populated by uploading the IdP Metadata file (downloaded earlier)
- Click ‘Add’

![](../static/ISA/SAML/SAML6.jpg)

- Once created, the SAML profile will be available to view

![](../static/ISA/SAML/SAML7.jpg)

- The SAML Authentication profile can be assigned to the User Group synced from Entra ID
    -   Navigate to User Groups
    -   Locate and expand the User Group synced from Entra ID
    -   Click on ‘Edit’
    -   In the ‘Authentication Profile’ drop-down, select the SAML profile created

- Click on ‘Update’

![](../static/ISA/SAML/SAML8.jpg)
