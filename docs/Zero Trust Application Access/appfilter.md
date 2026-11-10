---
comments: true
---
### App Filter Endpoint Control 

The App Filter endpoint control feature empowers administrators to block specific applications from running on end-user devices. This is crucial for enforcing security and compliance by preventing the usage of unauthorized or high-risk applications.

This control is supported on devices running:
	- Windows
	- Linux
	- Darwin (macOS)

Admins can choose to enforce the App Filter:
	- When the user connects to the ZTNA agent (VPN mode), or
	- Immediately upon device boot (always-on control)

### Steps to Configure App Filter Endpoint Control

1. Go to Configuration → Data Management.

2. Click “Add New Dataset”.

3. Set the Dataset Variable Type to “Application”.

4. Enter the Dataset Name and Description, then click “Create Dataset”.

5. Open the newly created dataset.

6. Toggle to Edit Mode.

7. Navigate to the Records tab.

8. Click the “+ Add Record” button.

9. Enter the Application Name for each app you want to block. You can add multiple records to block several applications.

### Create an App Filter Policy

1. Navigate to Access Policy → Endpoint Policy.

2. Click “Add New Policy”.

3. Enter the Policy Name and Description.

4. Select “App Filter Control” and associate it with the previously created Application dataset.

5. Choose the dataset created for the App filter created now and choose applicable Operating Systems.

6. Select the target Users or User Groups to whom the policy should apply.

7. Define when the control should be active:

	- When VPN is connected, or

	- At device boot

8. Click “Submit” to apply the policy.

### How It Works

1. Launch the ZTNA UI Client
2. Enter the InstaSafe Workspace URL
3. Authenticate via the redirected InstaSafe login page
4. When prompted, click "Open InstaSafe ZTNA Agent."
5. The ZTNA Agent will launch — click Connect
6. Upon connection, the App filter policy is automatically applied(if selected VPN is connected), restricting applications within the controlled session.
