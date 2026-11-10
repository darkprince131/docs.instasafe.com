---
comments: true
---
# Contextual Access Management

Contextual access in the context of enterprise remote access refers to the concept of granting or restricting access to resources based on various contextual factors. Instead of relying solely on traditional methods like username and password, contextual access takes into account additional parameters to make access control decisions. These parameters may include:

**User Identity:** The individual attempting to access the system.

**Device Information:** Details about the device used for access, such as its type, operating system, and security posture.

**Location:** The physical or network location from which the access request originates.

**Time of Access:** The specific timeframe during which access is requested.

**Security Compliance:** Ensuring that the device complies with security policies and has the necessary security software and configurations.

By considering these contextual factors, organizations can implement a more dynamic and adaptive access control system. For example, a user might have different levels of access when attempting to log in from their office computer during regular working hours compared to accessing the system from a public Wi-Fi network during the weekend.

Contextual access enhances security by providing a more nuanced and adaptive approach to access control, reducing the risk of unauthorized access. This approach aligns with the principles of zero trust security, where trust is never assumed and must be continuously verified based on the current context of the user and their device.

InstaSafe Secure Access (ISA) provides the following contextual access features:

**Geo Binding** - Geo Binding helps ISA administrators to restrict the ISA User Agent connection to specific countries, thus further securing remote access to corporate resources.

**Device Binding** - Device Binding ensures that the users are allowed to make connections only from those devices registered in the ISA web console. This will eliminate attacks due to stolen or shared passwords. A user can be bound to multiple devices. 

**Device Checks** - Enables administrators to define rules that check endpoint devices for mandatory compliances. These rules determine whether a device is allowed to connect. As a result, non-compliant endpoints are prevented from accessing corporate resources.

**Two-Factor Authentication (2FA)** – 2FA or MFA adds one more layer of security to the ISA User Agent connection process, in addition to the username-password and certificate method of authentication. 

