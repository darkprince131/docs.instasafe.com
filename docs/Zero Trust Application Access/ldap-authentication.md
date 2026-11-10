---
comments: true
---
# LDAP Authentication 

LDAP (Lightweight Directory Access Protocol) authentication allows user identity verification by validating credentials against a directory server. The ZTAA platform supports LDAP as an authentication method, with TOTP-based Multi-Factor Authentication (MFA) as an added security layer.


## Prerequisites

- A service account must be created within the ZTAA tenant.
- Required TCP ports must be open:
  - `389` for Go Auth
  - `389` and `636` for NGINX
- Update configuration in:
  - Go Auth properties file
  - NGINX properties file
- OpenVPN server must be created and configured.
- In AWS Security Group, OpenVPN IP must be allowed on TCP port `389`.


## Step-by-Step Configuration

### 1. Configure ZTAA as an LDAP Identity Provider

- Navigate to:  
  `ZTAA Console → Identity Management → Identity Provider`
- Click the ➕ button and select **LDAP**.
- Provide an **IDP Name**, then click **Next**.

    ![ ](../static/ztaa/LDAP-1_select_ldap.png)
    
    ![ ](../static/ztaa/LDAP-2_ldap_profile_name.png)


- Choose a **Service Account** from the dropdown.
- (Optional) Enable the **Multi-Factor Authentication (MFA)** toggle.
- Click **Submit**.

    ![ ](../static/ztaa/LDAP-3_service_acc_mfa.png)

- Once created, the **Bind DN** field will be displayed.  
  **Note** this value — it will be used during OpenVPN integration.

    ![ ](../static/ztaa/LDAP-4_bind_value.png)

### 2. Create a User and User Group in ZTAA

- [Create an User](https://docs.instasafe.io/Zero%20Trust%20Application%20Access/004-creatingusers/):  
  Navigate to `Identity Management → Users`, and add a new user.
- [Create an User Group](https://docs.instasafe.io/Zero%20Trust%20Application%20Access/004b-usergroup/):  
  Go to `Identity Management → User Groups`, and add the user to this group.
- [Auth Profile](https://docs.instasafe.io/Zero%20Trust%20Application%20Access/004b-usergroup/):  
  Add the created user or group to the Authentication Profile .
- **Bind User Group to LDAP Profile**:  
  In `Identity Management → LDAP Profile`, click **Add User Group** and link the relevant group.
    
    ![ ](../static/ztaa/LDAP-5_usergroup_to_ldap.png)

### 3. Configure LDAP Authentication in OpenVPN

#### 3.1 Set LDAP as the Default Auth System

- Log in to the **OpenVPN Admin Portal**.
- Go to `Authentication → Settings`.
- Set **LDAP** as the **Default Authentication System**.

    ![ ](../static/ztaa/LDAP-6_Authentication_in_openvpn.png)


#### 3.2 Enable and Configure LDAP

- Navigate to `Authentication → LDAP`.
- Enable the **LDAP Authentication** toggle.

    ![ ](../static/ztaa/LDAP-7_Ldap_authentication_in_openvpn.png)

- In the **Primary Server** field, enter:  
  `<Environment IP Address>:389`
- Enable the **Use These Credentials** option.
- Copy the **Bind DN** from the ZTAA LDAP Profile and paste it into the **Bind DN** field in OpenVPN.
- Enter the **Service Account Password** in the **Password** field.

    ![ ](../static/ztaa/LDAP-4_bind_value.png)
    
    ![ ](../static/ztaa/LDAP-8_LDAP_Authentication_Profile.png)

#### 3.3 User Permission and Profile

- Go to `User Management → User Permissions`.
- Add the **ZTAA User** under **Username**.

    ![ ](../static/ztaa/LDAP-9_User_Permission_Section_of_Openvpn.png)

- Navigate to **User Profile**, click **New Profile** for the user.

    ![ ](../static/ztaa/LDAP-10_User_Profile_Section_of_Openvpn.png)

- In the pop-up, click **Create Profile** to download the OpenVPN config file (`.ovpn`).

    ![ ](../static/ztaa/LDAP-11_Create_Profile.png)

### 4. Configure OpenVPN Client

#### For Windows & Mac

1. Download and install the **OpenVPN Client** from the [OpenVPN website](https://openvpn.net/client/).

    ![ ](../static/ztaa/LDAP-12_Download_OpenVPN_Client_for_Windows.png)


2. Launch the client and click the ➕ button.
3. Click **Browse**, select the downloaded `.ovpn` profile, and click **Connect**.

    ![ ](../static/ztaa/LDAP-13_import_profile_1_.png)

    ![ ](../static/ztaa/LDAP-14_upload_file.png)


4. Enter **Username**, **Password**, and **TOTP** (comma-separated, e.g., `password,123456`), then click **OK**.

    ![ ](../static/ztaa/LDAP-15_connect_1_.png)

    ![ ](../static/ztaa/LDAP-16_password_1_.png)



#### For Linux

##### Install and Connect
- Open Terminal in Linux OS
- Move to the File where you have saved the Open VPN File 
- Run the below command

>cd ~/Downloads

>sudo openvpn --config <profile_name>.ovpn

>sudo tail -f /var/log/syslog

##### View OpenVPN Logs

>sudo tail -f /var/log/syslog


