---
comments: true
---
# Always-On Mode

When an InstaSafe Secure Access (ISA) user has **Authentication Type** set to **‘Certificate’** instead of **'Password+Certs'**, this is defined as Always-On mode. 

**Advantages of Always-On:**

- The InstaSafe User Agent will always be running in the background, even after shutdown and/or reboot.
- To prevent accidental disconnection, the Agent icon will not be visible in the notification area after the first reboot following installation.
- PCs can join a domain remotely. During the domain joining process, if the PC needs to be restarted, the Agent will automatically connect in the background during startup, allowing the computer to fetch the necessary Group Policies and settings from the domain server.
- Group Policy settings can be pushed by the domain administrator to take effect immediately.
- Domain password resets can be made at the logon screen.
- Convenience in usage without having to connect manually to the corporate network.

**When should Always-On mode be implemented:**

- Implement Always-On mode when corporate policy requires remote users to be continuously connected to the domain.
- Choose Always-On mode when convenience is prioritized over enhanced security.
- In certain cases where corporate policy mandates remote users to maintain a constant connection to the corporate network for monitoring purposes through session logs.
