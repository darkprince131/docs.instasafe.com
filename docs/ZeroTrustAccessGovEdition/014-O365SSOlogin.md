---
comments: true
---
## Logging into O365 with InstaSafe ZTNA as SSO

<span dir="">Office 365 SSO integration by InstaSafe ZTNA provides secure access and full control over multiple Web and SaaS applications to enterprise users and clients. Using InstaSafe ZTNA as an users to Single Sign-On into Office 365 account with one set of login credentials, eliminating user-managed passwords and the risk of phishing. Single Sign-On for Office 365 sets up leverages the existing on-premise Active Directory infrastructure and provides seamless integration without the need to manage multiple on-premise and cloud identities.</span>

<span dir="">In addition to SSO for Office 365, users will have one-click access to all their apps and . Users requirement to secure Office 365 also helped us to introduce enhanced Office 365 Two-Factor Authentication solution. </span>

**<span dir="">Import Users from Azure AD</span>** 

<span dir="">Users need to be synced from Azure AD so that InstaSafe ZTNA recognises them and pulls all users details. Profile for O365 users will be existing in Azure AD.</span>

![Image](../static/ztaa/)

**<span dir="">Steps to Sync Azure AD profile</span>**

<span dir="">To sync users from Azure AD to InstaSafe ZTNA the admins need to login to AzureAD via the console </span>

 <span dir="">1- Log in as an admin and go to Identity Management</span>

<span dir=""> 2- Log into to Azure via an admin account</span>

<span dir="">3- Set Default Password for all users (Optional).</span>

<span dir="">4- Click on Sync button to import users.</span>

![Adding Users via Azure](../static/ztaa/ImportingUsersfromAzureAD.mp4)

**<span dir="">P.S Please search for individual user name to confirm that users have been successfully imported.</span>**


**<span dir="">Configuring InstaSafe ZTNA as IDP</span>**

1. <span dir="">Go to Identity Provider and configure a SAML profile for O365.</span>
| **<span dir="">Basic SAML Configuration setting</span>** | **<span dir="">SP Initiated</span>** | **<span dir="">IdP-Initiated</span>** | **<span dir="">Description</span>** |
| **<span dir="">Identifier (Entity ID)</span>** | <span dir="">Required for some apps</span> | <span dir="">Required for some apps</span> | <span dir="">This field will Uniquely identify InstaSafe ZTNA application. Azure AD sends the identifier to the application as the Audience parameter of the SAML token. The application is expected to validate it. This value also appears as the **Entity ID** in InstaSafe ZTNA provided by the application. </span> |
| **<span dir="">ACS URL (Reply URL/Redirection URL)</span>** | <span dir="">Required</span> | <span dir="">Required</span> | <span dir="">ACS or Assertion Consumer Service URL specifies where the application expects to receive the SAML token. This is to be obtained from the meta data file obtained for azure.</span> |
| **<span dir="">IDP URL and Logout URL</span>**  | <span dir="">Required</span> | <span dir="">Auto generated</span> | <span dir="">The IDP URL and Logout Url will be generated post successful configuration as a IDP and needs to be after configuration to be provided while configuring SP. </span> |

![Image](../static/ztaa/)

* <span dir="">IDP certificate and Private Key can be auto generated in the console</span>
* <span dir="">The Value of Subject ID field which has a default value as email has to be changed to **Custom Attribute** .</span>
* <span dir="">Subject ID format has to be set </span>
* <span dir="">Custom attribute field has to be mandatorily set to “**ext.onPremiseImmutableId**” </span>
* <span dir="">SP certificate can be the same as IDP certificate.</span>

![Image](../static/ztaa/)

**<span dir="">Setting up O365 as SP</span>**

<span dir="">Unlike other SaaS based application O365 does not have a User interface for SAML settings and the same has to carried out through powershell.</span>

1. <span dir="">Run the command “ **Connect-MsolService**” and enter admin credentials in the popup. </span>

![Image](../static/ztaa/)
1. <span dir="">Run the command ”Get -MSolDomainFederationSettings” to see the settings.</span>

![Image](../static/ztaa/)
1. <span dir="">Set the Environment variables to value as given blow.</span>

* <span dir="">$dom= Domain name of O365 for which SAML has to be configured</span>
* <span dir="">$BrandName= Any Brand Name. </span>
* <span dir="">$LogOnUrl= LogIn URL created above</span>
* <span dir="">$MyURI= SAML front end, Idp Entity ID. Captured in step -1</span>
* <span dir="">$MySigningCert = SAML Front end IDP Certificate</span>
* <span dir="">$Protocol= SAML</span>
* <span dir="">$logOffUri = Logout URL created above</span>

<span dir="">\
 ![Image](../static/ztaa/)

**<span dir="">Signing into Office Account</span>**

1. <span dir="">After configuration, Visit Portal.office.com. and enter username. </span>

![Image](../static/ztaa/)

1. <span dir="">You will be redirected to InstaSafe ZTNA authentication page. Enter your credentials</span>

![Image](../static/ztaa/)

<span dir="">Upon successful authentication you will be able to login to your office account.</span>

![Image](../static/ztaa/)
