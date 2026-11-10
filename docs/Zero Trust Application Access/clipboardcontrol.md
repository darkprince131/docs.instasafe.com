---
comments: true
---
### Clipboard Control 

The Clipboard Control feature allows administrators to restrict copy-paste actions on end-user devices. This protects data by preventing sensitive data from being copied or transferred unintentionally or maliciously.

This control applies to devices running the following operating systems:

- Windows
- Linux
- Darwin (macOS)

Once enforced, the Clipboard control is triggered when the user connects to the ZTNA agent for application access.

### Steps to Configure Clipboard Endpoint Control

1. Navigate to Access Policy → Endpoint Policy in the admin dashboard.

2. Click on “Add New Policy”.

3. Provide the following details:
	- Policy Name
	- Policy Description

4. Enable the Clipboard Control option.

5. Select the applicable Operating Systems (Windows, Linux, Darwin).

6. Choose the Users or User Groups to which the policy should be applied.

7. Under Condition, select “When VPN is connected”.

8. Click on the “Submit” button to save and apply the policy.

### How It Works

1. Launch the ZTNA UI Client
2. Enter the InstaSafe Workspace URL
3. Authenticate via the redirected InstaSafe login page
4. When prompted, click "Open InstaSafe ZTNA Agent."
5. The ZTNA Agent will launch — click Connect
6. Upon connection, the Clipboard control policy is automatically applied, restricting any clipboard-based actions like copy-paste within the controlled session.





