---
comments: true
---
# Accessing the Platform

**Log In to the Admin Portal**

- Visit the [InstaSafe Admin Portal](https://my.instasafe.net/login_verify).
- Enter your company's unique slug name (an identifier for your company) and click "Continue".
- Provide your registered email address and password to log in.

**Download the InstaSafe Client**

- After logging in, navigate to the "Downloads" section.
- Select the appropriate client version compatible with your operating system (Windows, macOS, Linux, iOS, or Android) and download it.

**Install and Configure the Client**

- Install the downloaded client on your device.
- Launch the InstaSafe Zero Trust Client.
- Enter your company's slug name and click "Continue".
- Provide your username (registered email) and password when prompted.

**Access Assigned Applications**

- Upon successful authentication, the client will display the applications assigned to you.
- Click on the desired application to access it securely through the InstaSafe platform.

**Zero Trust Network Access**

**Account Setup**

- Invitation Email: If your organization uses ZTNA, you will typically receive an invitation email with setup instructions.
- Account Credentials: Ensure you have the necessary credentials (username and password), often tied to your company email.

**Portal Access**

- Admin Portal Login: Access the ZTNA portal via the URL provided by your organization. Example: [InstaSafe Admin Portal](https://my.instasafe.net/login_verify) 
- Slug or Domain Name: Input your organization's unique identifier (often referred to as a slug).
- Credentials: Log in using your registered email and password. Some platforms might require multi-factor authentication (MFA).

**Download and Install the ZTNA Client**

- Locate the Client: After logging in, navigate to the “Downloads” or “Client” section on the platform.
- Install Software: Download the client for your operating system (Windows, macOS, Linux, iOS, or Android).
- Configure the Client:
    - Enter your organization’s slug or domain.
    - Log in with your username and password.

# Configuring policy

**Log In to the InstaSafe Admin Portal**

- Visit the [InstaSafe Admin Portal](https://my.instasafe.net/login_verify).
- Enter your organization’s slug or domain name and log in using admin credentials.

**Navigate to Policy Management**

- Once logged in, locate the Policy or Access Control section in the dashboard.
- This section allows administrators to create, modify, and manage security policies.

**Define Policy Scope**

- User Group: Choose the user groups (e.g., employees, contractors, vendors) the policy will apply to.
- Applications or Resources: Select the applications or network resources users will access under this policy.
- Access Levels: Determine if the access will be full, restricted, or read-only.

**Set Authentication Requirements**

- Multi-Factor Authentication (MFA): Enforce MFA for all or specific users.
- Identity Provider (IdP) Integration: Configure Single Sign-On (SSO) or integrate with your organization’s IdP (e.g. Okta, Azure AD).

**Define Conditional Access Policies**

- Device Compliance: Allow access only from compliant devices (e.g., with endpoint security).
- Geolocation: Restrict access based on geographic location or IP addresses.
- Time-Based Access: Set policies for access during specific timeframes.

# Managing User and Devices

Managing users and devices in InstaSafe Technology Private Limited's Zero Trust Network Access (ZTNA) platform involves creating and organizing user profiles, assigning roles, managing devices, and ensuring compliance with security policies. Below is a comprehensive guide to managing users and devices effectively:

**Access the Admin Portal**

- Login: Use your admin credentials to access the [InstaSafe Admin Portal](https://my.instasafe.net/login_verify)
- Navigate to User and Device Management: Locate the "Users" and "Devices" sections in the admin dashboard.

**1. Managing Users**

**1.1. Adding Users**

_Manual Addition:_

- Go to the "Users" section and click Add User.
- Provide details such as the user's name, email address, and role.
- Assign the user to relevant groups (e.g., Employees, Contractors).

_Bulk Upload:_

- Use the CSV upload feature to add multiple users simultaneously.
- Download the sample template, fill in user details, and upload it.

_Integration with Identity Providers (IdP):_

- Connect InstaSafe to your organization's IdP (e.g., Okta, Azure AD) for automated user provisioning.

**1.2. Editing or Deactivating Users**

- Select the user from the list.
- Edit user details, roles, or access permission.
- Deactivate users who no longer need access.

**1.3. Assigning Roles and Policies**

- Define user roles (Admin, Sub-admin, User).
- Assign access policies based on roles.

**1.4. Monitoring User Activity**

- Review event logs to monitor login attempts, resource access, and unusual activities.

**2. Managing Devices**

**2.1. Adding Devices**

- User Devices: Devices are registered when users log in via the InstaSafe client for the first time.
- Manual Registration: Admins can manually register devices by entering the device name, type, and unique identifier (e.g., MAC address).

**2.2. Enforce Device Compliance**

- Endpoint Security Checks: Configure policies to allow access only from compliant devices.
- Certificates: Enforce device certificate installation to validate trusted devices.
- OS Updates: Ensure devices meet minimum OS version requirements for secirity.

**2.3. Monitoring Devices**

- Track all connected devices in the **Devices** section.
- View details such as device name, type, IP address and last login time.

**2.4. Removing or Blocking Devices**

- Disable or block devices that are stolen or no longer in use.
- Revoke certificates associated with compromised devices.


