---
comments: true
tags:
  - Available On Premises
---

# Advanced Settings

The Advanced Settings section in the ZTAA console provides fine-grained configuration controls to help administrators tailor the behavior of the ZTNA client and platform to meet organizational requirements.

These settings enhance security enforcement, optimize user experience, support legacy systems, and offer better control over device and user access. From enabling passwordless authentication to enforcing secure browsers or customizing client behavior, each option supports a variety of deployment scenarios—cloud-based, hybrid, or fully on-premises.

---

## Steps to Configure

- Log in to the ZTAA console as an admin  
<!-- paste image path according to url name "advanced-settings-landing.png" -->

- Click the profile dropdown (top-right corner)  

- Select Admin Portal  
<!-- paste image path according to url name "advanced-settings-admin.png" -->

- Go to My Profile
<!-- paste image path according to url name "advanced-settings-myprofile.png" -->

- Click the Organisation section  
<!-- paste image path according to url name "advanced-settings-settings.png" -->

- Scroll down to find Advanced Settings and click on it
<!-- past image path according to url name "advanced-settings-options.png" -->


---

## Features

### 1. Auto Connect ZTNA Client
Automatically initiates a ZTNA connection on user login for seamless and consistent secure access.

### 2. Block Password Reset for AD Users
Prevents AD users from resetting passwords via the portal. Must be managed via the domain controller.

### 3. Block Password Reset for Local Users
Prevents local users from resetting their passwords through the portal. Admin must handle password changes.

### 4. Block Rooted Mobiles
Blocks access from rooted or jailbroken mobile devices to ensure only secure devices are used.

### 5. Clear Agent Cache
Clears the ZTNA agent’s cache on launch for all users, ensuring fresh configurations.

### 6. Sync Users Without Phone
Allows directory sync to import users without a phone number, even though it's normally required.

### 7. Disable TCP Apps
Restricts access to TCP-based applications; only HTTP/HTTPS apps will be accessible.

### 8. Disable Welcome Email (Synced Users)
Prevents welcome emails from being sent to users imported via directory sync.

### 9. Enable Auto Connect Toggle
Allows users to enable/disable auto-connect from the ZTNA client interface.

### 10. Enable Azure SSO
Uses existing Microsoft login sessions to enable seamless authentication via the ZTNA agent.

### 11. Enable Clientless VPN Access
Allows access to Always ON apps through a browser without the desktop ZTNA client.

### 12. Enable Facial Authentication
Enables facial recognition for biometric login authentication.

### 13. Enable File Downloader
Shows a File Downloader app post-VPN connection for secure file access.

### 14. Enable Form Based Authentication
Supports form-based login for web apps using standard HTML forms.

### 15. Enable Geolocation Services
Collects location data from user devices to enforce location-based policies.

### 16. Authenticator Enables 2FA
Automatically enables TOTP 2FA when a user sets up an authenticator app.

### 17. Rest SQS
Uses REST APIs for message delivery instead of standard SQS; useful for restricted environments.

### 18. Enable WebAuthn
Allows passwordless login via WebAuthn-compliant devices (biometrics, security keys, etc.).

### 19. Enforce Device Check
Restricts access to verified and compliant devices only.

### 20. Enforce Secure Browser
Launches all network apps in the InstaSafe Secure Browser for enhanced security.

### 21. Force Authenticator
Requires users to complete authenticator app setup if 2FA is enabled.

### 22. Hide QR Code Setup for Authenticator App
Hides QR setup prompts; authenticator setup must be admin-guided.

### 23. Hide System Notification in ZTNA Client
Suppresses system notifications for a silent user experience.

### 24. Hide Authentication Prompt
Disables prompt for setting up authenticator during login.

### 25. Invalidate Session on Agent Close
Ends the session when the ZTNA agent is closed; user must re-authenticate next time.

### 26. Use ISA’s OTP
Allows legacy InstaSafe users to use their existing 2FA setup without re-enrollment.

### 27. Enable Legacy APIs
Uses older API versions for compatibility with legacy systems.

### 28. Local AD
Allows use of on-premises Active Directory without cloud gateways.

### 29. Logout User on VPN Disconnect
Logs out users from ZTNA agent when VPN disconnects or the agent is closed.

### 30. Prioritize AD Password Reset Over Azure
In hybrid setups, prioritizes password reset through on-prem AD by default.

### 31. Agent Calls ListMyApps API
Agent directly fetches apps list via API instead of using SQS—suitable for large app environments.

### 32. Enable Agent Keep Alives via TCP
Uses TCP for keep-alive signals to improve reliability in restricted networks.

### 33. Auto Close Browsers
Closes browser windows launched via ZTNA when VPN disconnects. Requires dataset App ID.

### 34. Check IP Format
Defines format of the Check IP URL response:  
- `0` = Plain text  
- `1` = JSON

### 35. ESS Client Key
Unique key used by the ESS client for tenant identification and log streaming.

### 36. Geolocation Check Interval
Sets how often (in minutes) the agent updates its geolocation.

### 37. OTP Send Limit
Maximum number of OTPs that can be sent to a user within a time window to prevent spamming.

### 38. MTU
Defines the maximum packet size (in bytes) for traffic through the ZTNA tunnel.

### 39. OTP Block Time Frame
Time (in minutes) after the **last** OTP sent, during which the send limit is enforced. Resets after this period.

### 40. OTP Rate Limit Time Frame
Time window (in minutes) starting from the **first** OTP sent, within which the send limit is applied.

### 41. Windows Login MFA Session Duration
Duration (in hours) after successful MFA login, during which the user won’t be prompted again.
