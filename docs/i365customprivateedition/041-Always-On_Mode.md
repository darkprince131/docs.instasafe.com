---
comments: true
---
# Always-On Mode

When an InstaSafe Secure Access (ISA) user has **Authentication Type** set to **‘Certificate’** instead of **'Password+Certs'**, this is defined as Always-On mode.  

In Always-On mode, when the User Agent attempts to connect to the ISA server, the user will be prompted for the username and password only during the installation of the User Agent. In subsequent attempts to connect, the ISA Agent will connect automatically, without user input, using the user-specific certificate for authentication. However, if Two-Factor Authentication (TFA) is enabled for the user or the user group, the user will be served the push notification to select the method for receiving OTP. Additional security parameters such as Device Checks, Device Binding, and Geo Binding will be implemented, if the ‘Extended Validation for Certs’ feature is enabled. 

| Authentication Type | ISA User Agent Connection | Password Prompt | 2FA (if configured)| Security Check (if configured) |
| ------------ | ------------ | ------------ |------------ | ------------ |
| Password+Certs | On Demand | Yes | Yes | Yes |
| Certificate | Always-On | No | Yes | Yes |

  Note: Security checks include Device Binding, Geo Binding and Device Checks 

While the ISA User Agent will not prompt for credential authentication in Always-On mode, users still need to authenticate themselves with their domain credentials in order to login to the domain profile on their systems. As Always-on performs a non-interactive login, authentication is performed based on user and device certificates. 

## **When should Always-On mode be implemented:**

- Implement Always-On mode when corporate policy requires remote users to be continuously connected to the domain.
- Choose Always-On mode when convenience is prioritized over enhanced security.
- In certain cases where corporate policy mandates remote users to maintain a constant connection to the corporate network for monitoring purposes through session logs.

For more security and compliance requirements where Multi-Factor Authentication (MFA) is mandatory, Always-On mode is not recommended. 
