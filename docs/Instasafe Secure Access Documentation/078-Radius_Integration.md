---
comments: true
---
# InstaSafe AD Integration for Radius

The following are the steps to use AD authentication with InstaSafe Secure Access 

**1. Create a security group**

Create a security group in Active Directory Users and Computers called VPNusers. Everyone could have access but it's a good policy to identify the VPN Users and have granular access control.

![](../static/ISA/Radius/Radius.jpg)

**2.Add Users to Security Group**

Add user accounts that use the InstaSafe VPN to this group. 

![](../static/ISA/Radius/Radius1.jpg)

**3.Add “Network Policy and Access Service” Role**

On the Active Directory Check if the “Network Policy and Access Services” role exists under Roles in Server Manager. 
Otherwise, click right-click Roles and select Add Role.

Click Next to add role in the wizard

Select “ Network Policy and Access Services” under the Roles to be added and click Next

![](../static/ISA/Radius/Radius2.jpg)

![](../static/ISA/Radius/Radius4.jpg)

Under Role Services, select Network Policy Server and Click Next

Once the Role is added, it appears under Roles in the Server Manager

**4. Add Radius Client**

Expand the **Network Policy and Access Services** node, go to **NPS (Local) > RADIUS Clients and Servers**, right-click **RADIUS Clients** and choose **New**

![](../static/ISA/Radius/Radius5.jpg)

Fill in the below fields

**Friendly name:** Enter InstaSafe VPN or anything deemed appropriate 

**Address (IP or DNS):** Enter the LAN IP address of the InstaSafe Gateway. 
For example: 192.168.1.77. 
Please confirm the IP address from the InstaSafe Support Team 

**Shared Secret:** Select Manual, set a password and save the shared secret. 

This secret is required to be configured later on the my.instasafe.net portal.

![](../static/ISA/Radius/Radius6.jpg)

**5. Add Network Policy** 

Under **NPS (Local) > Policies** right-click **Network Policies** and select **New** 

![](../static/ISA/Radius/Radius7.jpg)

In the **Policy name field**, enter **Allow InstaSafe**. 

Type of network access server: **Unspecified** 

Click Next

![](../static/ISA/Radius/Radius8.jpg)

In the **Specify Conditions** window, click **Add**

![](../static/ISA/Radius/Radius9.jpg)

Select Windows Groups and click Add

![](../static/ISA/Radius/Radius10.jpg)

Click **Add Groups** and add the group **VPNusers** (or whatever group is needed)

![](../static/ISA/Radius/Radius11.jpg)

Back in the **Specify Conditions** window, click **Next**

![](../static/ISA/Radius/Radius12.jpg)

Select **Access granted**

![](../static/ISA/Radius/Radius13.jpg)

Put the new policy before policies preventing the connection. Please note the Processing Order should be high for **“Allow InstaSafe”** Policy.

![](../static/ISA/Radius/Radius14.jpg)

**6. Configure Authentication Methods** 

In the Configure Authentication Methods window, check **Unencrypted authentication (PAP, SPAP)**

![](../static/ISA/Radius/Radius15.jpg)

Skip the next wizard window (Constraints) and click Next, Next, Finish until the end.

**7. Configuring RADIUS Authentication Profile on the ISA Web Console**

- Log in to the ISA web console using administrator credentials.  

- Click on AUTHENTICATION PROFILES in the left-hand menu.

![](../static/ISA/Radius/Radius16.jpg)

- Under AUTHENTICATION PROFILES click on RADIUS.  

- On the RADIUS page, under RADIUS Profile, click on the Add button. 

![](../static/ISA/Radius/Radius17.jpg)

- In the Create RADIUS Profile window, enter the following information under each field:  

    - **Profile Name:** Enter a descriptive name for this profile. The name must not contain spaces. This field is mandatory. 
    - **Gateway to reach RADIUS:** Select the Gateway name through which the OpenLDAP server can be accessed. For example, "Gateway BLR-Data-Centre." This field must be selected from the available options
    - **RADIUS Server IP:** Enter the private IP address of the RADIUS server. This field must be filled-in
    - **Backup RADIUS Server IP:** Enter the private IP address of the backup RADIUS server
    - **Port:** Enter the port number Open LDAP server for example Radius server port : 1812
    - **Radius Secret:** Enter the shared secret configured manually while adding the radius client in the “Network Policy and Access Service”

![](../static/ISA/Radius/Radius18.jpg)

- Click on **Save** to create this profile. This will create a RADIUS profile and the new profile will be displayed on the page.

- Open the user profile And Assign the Authentication Profile to the user profile.

![](../static/ISA/Radius/Radius19.jpg)

To verify that InstaSafe Secure Access is using AD authentication, please start the InstaSafe Agent and enter the AD username in the email format (username@domain) and the AD password for the user. If the connection is successful, the AD integration is complete. If the connection is unsuccessful, please contact support@instasafe.com or call InstaSafe Support for assistance.

