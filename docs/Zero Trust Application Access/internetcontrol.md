---
comments: true
---

### Block Internet 

Unrestricted access to the internet at the workplace introduces a range of problems along with the many benefits. Unproductive or personal browsing by employees, the threat of downloading and infecting the enterprise network with viruses, malwares and bandwidth hogging are just a few of the numerous challenges.

To mitigate these threats, the InstaSafe Zero Trust platform offers the “Block Internet” endpoint control feature. This allows administrators to restrict internet access on end-user devices.

Supported Platforms. This control can be enforced on:
- Windows
- Linux
- Darwin (macOS)


The InstaSafe platform provides two flexible options to block internet access:

- When VPN is Connected: Internet access is blocked when the user is connected to the VPN (InstaSafe ZTNA Agent). The user can only access authorized applications via the secure gateway.

- When VPN is Not Connected: Internet access is blocked when the user is not connected to the VPN (InstaSafe ZTNA agent)..

This ensures that users cannot go online outside the secure network.

### Steps to Configure "Block Internet" Endpoint Control

1. Go to Access Policy → Endpoint Policy.

2. Click “Add New Policy”.

3. Define: Provide a Policy Name, Description, and Expiry date.

4. Enable “Block Internet” control.

5. Select the Operating Systems where the policy should apply.

6. Choose the target Users or User Groups to whom this policy will apply.

7. Select Blocking Condition
	- When VPN is Connected

	- When VPN is Not Connected

8. Save and Apply

9. Click “Submit” to enforce the policy.

### See How the “When VPN is Not Connected” option works in real-world scenarios:
### BlockInternet Apply

1. Launch the ZTNA UI Client
2. Enter the InstaSafe Workspace URL
3. Authenticate via the redirected InstaSafe login page
4. When prompted, click "Open InstaSafe ZTNA Agent."
5. The ZTNA Agent will launch — click Connect
6. Upon connection, the Block Internet policy is applied.

    When a user is connected to the VPN via the InstaSafe ZTNA agent, they can access only allowed applications and may have internet access depending on policy.
However, once the VPN is disconnected, access to both applications and the internet is blocked entirely.




