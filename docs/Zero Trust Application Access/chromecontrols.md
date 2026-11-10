---
comments: true
---
### Chrome Control 

The Chrome Endpoint Control feature allows Admins to restrict specific browser actions on end-user devices, enhancing security and preventing data leakage through web browsers.

### Key Capabilities
- Admins can restrict users from performing the following actions in Chrome:
- Downloading files
- Accessing Developer Tools (DevTools)
- Taking prints

Admins can configure this policy to be enforced either:
- At device boot (On Boot)
- When connected to the ZTNA agent (On Network Connection)

### Steps to Configure Chrome Endpoint Control

1. Go to Access Policy → Endpoint Policy.

2. Click on the “+” (Add New Policy) button.

3. Define: Provide a Policy Name, Description, and Expiry date.

4. Click Chrome Controls

5. Select from the available control types:
	- Block Developer Tools
	- Download Restrictions
	- Disable Printing
	- Disable Print Preview
	- Allow Screen Capture

        You can add multiple control types in a single policy.

6. Select the Operating Systems where this control should be enforced.

7. Assign Users/User Groups to whom this Chrome policy should apply.

8. Set Enforcement Condition
	- “On Boot” – Policy is applied at device startup.
	- “On VPN is connected” – Policy is applied when connected to the ZTNA agent.

9. Save the Policy

10. Click “Submit” to apply the policy.

### Check how the Chrome endpoint control policy gets applied in the end-user systems.

1. Launch the ZTNA UI Client
2. Enter the InstaSafe Workspace URL
3. Authenticate via the redirected InstaSafe login page
4. When prompted, click "Open InstaSafe ZTNA Agent."
5. The ZTNA Agent will launch — click Connect
6. Upon connection(if applied On VPN is connected), the Chrome control policy is applied.
7. Go to the browser & try to check whether control types are working as expected or not.


