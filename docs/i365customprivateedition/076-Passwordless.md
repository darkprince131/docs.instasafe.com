---
comments: true
---
# Configuring Passwordless Authentication

- Login to the instasafe console as an admin
- Click on AUTHENTICATION PROFILE >> Passwordless
- Click on Add Button

![](../static/ISA/Passwordless%20Authentication/Passwordless.jpg)

- Enter a Profile name and Select primary Auth as Hardware key  and Fallback Passwordles Auth option as password.

- Click on the **Save and Add New** button

![](../static/ISA/Passwordless%20Authentication/Passwordless1.jpg)

- Now the profile will list over the passwordless page 

![](../static/ISA/Passwordless%20Authentication/Passwordless2.jpg)

- After the successful creation of a passwordless Profile that can be used for a single user or a User Group.
- To assign that passwordless in the user profile click on USERS & GROUPS >> Users
- Search for the user and select the user which will be assigned to a passwordless profile
- Click on the Edit button

![](../static/ISA/Passwordless%20Authentication/Passwordless3.jpg)

- Click on the Authentication Profile and select the passwordless profile which was created earlier.

![](../static/ISA/Passwordless%20Authentication/Passwordless4.jpg)

- Click on the Update button to save the Authentication profile of the User as passwordless.

![](../static/ISA/Passwordless%20Authentication/Passwordless5.jpg)

- To assign that passwordless in the UserGroup profile click on USERS & GROUPS >> Users
- Search for UserGroup and select the UserGroup which will assign to a passwordless profile.
- Click on the Edit button

![](../static/ISA/Passwordless%20Authentication/Passwordless6.jpg)

- Click on the Authentication Profile and select the passwordless profile which was created earlier.
- Click on the Update button to save the Authentication profile of UserGroup as passwordless which will apply to all the members of the group as passwordless authentication

![](../static/ISA/Passwordless%20Authentication/Passwordless7.jpg)

- Login to the instance console with the user which enabled passwordless Authentication
- Click on the profile icon. Then click on the MFA option

![](../static/ISA/Passwordless%20Authentication/Passwordless8.jpg)

- Now click on the Resister key under FIDO Keys

![](../static/ISA/Passwordless%20Authentication/Passwordless9.jpg)

- For Windows hello option will display user can choose either the hello option or the Hardware key by clicking on the use another device option

![](../static/ISA/Passwordless%20Authentication/Passwordless10.jpg)

After verifying/adding the hello it will save and allow the user to login via passwordless

![](../static/ISA/Passwordless%20Authentication/Passwordless11.jpg)

- After the successful registration of the hardware key, _Hardware key registered successfully_ message will display

![](../static/ISA/Passwordless%20Authentication/Passwordless12.jpg)

**Console Login Through The Passwordless Hardware Key**

- After successfully registering the hardware key, when the User logs in Next time, it will directly ask for the Hardware key instead of the password

![](../static/ISA/Passwordless%20Authentication/Passwordless14.jpg)

- The user will log in to instasafe after verification of the Hardware Key

![](../static/ISA/Passwordless%20Authentication/Passwordless15.jpg)

**Configuring Passwordless Authentication with Digital Certificate**

- Login to the instasafe console as an admin credential
- Click on AUTHENTICATION PROFILE >> Passwordless
- Now click on Add Button

![](../static/ISA/Passwordless%20Authentication/Passwordless.jpg)

- Enter a Profile name and Select primary Auth as Digital Certificate  and Fallback Auth option as password
- Now click on the Save and AddNew button

![](../static/ISA/Passwordless%20Authentication/Passwordless16.jpg)

- Now the profile will list over the Passwordless page 

![](../static/ISA/Passwordless%20Authentication/Passwordless17.jpg)

- After the successful creation of a passwordless profile, it can be used for a single user or a User Group.
- To assign that passwordless in the user profile, click on USERS & GROUPS >> Users
- Search for the user and select the user which will be assigned to a passwordless profile
- Now click on the Edit button

![](../static/ISA/Passwordless%20Authentication/Passwordless18.jpg)

- Now choose the passwordless profile with a digital certificate.

![](../static/ISA/Passwordless%20Authentication/Passwordless19.jpg)

**Installation Process of Digital Certificate** 

- Login to the instasafe console with the user for which the passwordless digital certificate authentication is configured.

![](../static/ISA/Passwordless%20Authentication/Passwordless20.jpg)

- Enter the password and  click on sign in

![](../static/ISA/Passwordless%20Authentication/Passwordless21.jpg)

- After Successful login Navigate to the Download section in the Dashboard Menu
- Download the instasafe web  agent 

![](../static/ISA/Passwordless%20Authentication/Passwordless22.jpg)

- Install the web agent to set up  the digital certificate

![](../static/ISA/Passwordless%20Authentication/Passwordless23.jpg)

- Enter the credential of a user for  which the digital certificate is configured and click on login

![](../static/ISA/Passwordless%20Authentication/Passwordless24.jpg)

- After the Successful installation of the agent installation, a success message will appear
- Then click on the ok button of the pop-up message

![](../static/ISA/Passwordless%20Authentication/Passwordless25.jpg)

**Instasafe Agent access with Digital certificate**

- After the agent is installed, the digital certificate will be installed on the computer.
- Enter the URL in the browser 
- A certificate prompt will open for Digital certificate passwordless authentication click on ok

![](../static/ISA/Passwordless%20Authentication/Passwordless26.jpg)

- After clicking on the ok, the login page will appear.

![](../static/ISA/Passwordless%20Authentication/Passwordless27.jpg)

- Now enter your username and click on sign in.

![](../static/ISA/Passwordless%20Authentication/Passwordless28.jpg)

- The user will be directly redirected to the dashboard page without asking for any password

![](../static/ISA/Passwordless%20Authentication/Passwordless29.jpg)

**Instasafe Agent access with Digital certificate**

- After the installation of the agent when the user tries to log in next time Then the certificate will appear
- Select the certificate and click on ok for passwordless digital certificate-based login

![](../static/ISA/Passwordless%20Authentication/Passwordless30.jpg)

- Now enter the username which is configured for passwordless and click on sign in

![](../static/ISA/Passwordless%20Authentication/Passwordless31.jpg)

- After sign-in, the user will connect to the agent successfully without asking for the Password

![](../static/ISA/Passwordless%20Authentication/Passwordless32.jpg)


