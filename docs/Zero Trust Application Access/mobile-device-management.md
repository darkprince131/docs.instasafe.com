---
comments: true
---

Mobile Device Management (MDM) is required for organizations to effectively manage and secure the use of mobile devices such as smartphones, tablets, and laptops that access corporate resources. As employees increasingly use mobile devices for work, especially in Bring Your Own Device (BYOD) environments, MDM helps maintain control over these devices, ensuring data security, compliance with corporate policies, and effective IT management.

## **Use Cases for Conditional Access in MDM:**

**Protecting Corporate Email**: Only allow users to access corporate email (like Exchange Online or Gmail for Business) from managed devices that comply with the organization’s security policies.

**Accessing Cloud Applications**: Ensure that users can only access cloud applications such as Microsoft O365, Salesforce, or Google Workspace when their devices are compliant and the user is authenticated through MFA.

**Securing BYOD Environments**: Allow employees to use their personal devices for work purposes but enforce strict conditional access policies that ensure corporate data is only accessible when devices meet security standards.

## **InstaSafe mZTNA mobile app integration with MDM for Conditional Access:**

The InstaSafe mobile app (mZNTA) available over Android and iOS can integrate with Mobile Device Management (MDM) solutions to provide conditional access to Microsoft 0365 and any web application which supports SAML along with the access to private applications.

With the integration to MDM, the mZTNA mobile app provides access to  Microsoft 0365, Salesforce, or Google Workspace only when the mZTNA mobile app is installed and managed by the MDM. If the mZTNA app is not installed by the MDM and users try to directly install it from PlayStore or AppStore and try to access Microsoft 0365, Salesforce, or Google Workspace then their access will be restricted.

## **Prerequisites for InstaSafe integration with MDM for Conditional Access:**

1. InstaSafe needs to be configured as the Identity Provider (iDP) for the cloud application access (Microsoft O365, Salesforce, or Google Workspace).

2. A unique secret key provided by InstaSafe needs to be configured for the InstaSafe mZTNA app while adding it in the MDM platform.


