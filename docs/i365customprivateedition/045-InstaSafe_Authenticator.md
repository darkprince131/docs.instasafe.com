---
comments: true
---
# Installing and Configuring the InstaSafe Authenticator App

An organization may choose to increase their security posture with InstaSafe Secure Access’s (ISA) built-in Two Factor Authentication (TFA) that will prompt users for an OTP delivered to the registered email address and mobile number. 

Further, ISA supports various authenticator apps to provide Time-based OTPs (TOTP) for Two-Factor Authentication. This would effectively eliminate the dependency on mobile networks for SMS OTPs and avoid deadlock scenarios where users can access corporate email for email OTPs only after the ISA User Agent is connected.

InstaSafe Authenticator supports TOTP and push notification-based approval. The Authenticator supports iOS and Android devices; however, the MFA push notification menu is not displayed for MacOS and Linux users. Instead, the OTP field is displayed without giving the option to the user to choose the method to receive the OTP. 

This article provides guidance on how to configure the InstaSafe Authenticator app for Two-Factor Authentication (TFA).

## **Install InstaSafe Authenticator app**

- Locate InstaSafe Authenticator in App Store or Play Store.
- Select the download icon.

![](../static/ISA/Authenticator.jpg)

- Select Open

![](../static/ISA/Authenticator1.jpg)

**Setting mPin**

- In the pop-up window, select **Allow**.

![](../static/ISA/Authenticator2.jpg)

- When the app opens, select **Authenticate** on the home screen.

![](../static/ISA/Authenticator3.jpg)

On the **Setup mPin**, enter a pin to login to the app and confirm it.

![](../static/ISA/Authenticator4.jpg)

- Select **Save**.

![](../static/ISA/Authenticator5.jpg)

- On the home screen, select **Login with mPin**.

![](../static/ISA/Authenticator6.jpg)

- Enter the login pin created earlier.

![](../static/ISA/Authenticator7.jpg)

- Select **Verify**.

![](../static/ISA/Authenticator8.jpg)

## **How to Add ISA Profile ?**

- Select the plus (**+**) icon.

![](../static/ISA/Authenticator9.jpg)

Select **Add Profile**.

![](../static/ISA/Authenticator10.jpg)

- Select **ISA**.

![](../static/ISA/Authenticator11.jpg)

- Enter the sub-domain provisioned to your organisation by InstaSafe. 

![](../static/ISA/Authenticator12.jpg)

- Select **Submit**.

![](../static/ISA/Authenticator13.jpg)

- You will be redirected to the ISA authentication page. Enter the username and password of the user. 

![](../static/ISA/Authenticator14.jpg)

- Select Sign In.

![](../static/ISA/Authenticator15.jpg)

_Note: If Two-Factor Authentication is enabled for the user, a menu is displayed with methods to obtain the OTP. Select SMS or email to receive the OTP. The MFA push notification menu is not displayed for macOS and Linux users. Instead, the OTP field is displayed without giving the option to the user to choose the method to receive the OTP._

- Once the user is successfully authenticated, the user is added to the app. The TOTP pin for the user is displayed. A new TOTP pin is generated every 30 seconds. Use the pin for secondary authentication when accessing the ISA web console or connecting the ISA User Agent. 

![](../static/ISA/Authenticator16.jpg)

**Testing**

- Open a web browser and log into the ISA web console. 
- Enter the username and password of the user and sign in.

![](../static/ISA/Authenticator17.jpg)

- When the user is prompted to select a method to receive the OTP, select TOTP on Authenticator. 

![](../static/ISA/Authenticator18.png)

- On the OTP prompt window, enter the OTP received via the **InstaSafe Authenticator App**.

![](../static/ISA/Authenticator19.png)

- Click **Submit** to the submit the OTP. 

![](../static/ISA/Authenticator20.png)

- If the option **Approve Push Notification on Authenticator** was selected, select **Approve** on the push notification received on the **InstaSafe Authenticator App**.

![](../static/ISA/Authenticator21.jpg)

**Authenticator Devices on the ISA Web Console**

When an authenticator device is installed and a user profile added manually to it, as opposed using the QR code, the ISA web console administrator can view the device and the users added to it under the **DEVICES & CHECKS > Authenticator Devices** page.

![](../static/ISA/Authenticator22.jpg)

_Note: Users with the authenticator app installed and authenticated are displayed on this page only if the user is authenticated manually. If authentication is using the QR code, the user is not displayed on this page. _

The administrator can choose to delete a user. To delete a user:

- Select the user by clicking the checkbox against the user. 

![](../static/ISA/Authenticator23.jpg)

- Click the **Delete** button at the top.

![](../static/ISA/Authenticator24.jpg)

- Click **Yes, Delete it!** on the confirm pop-up.

![](../static/ISA/Authenticator25.jpg)

Administrators can download the user list by clicking the **CSV** button at the top.

- Click the **CSV** button at the top.

![](../static/ISA/Authenticator26.jpg)

- An email will be sent to the email address configured in the user profile of the logged in administrator. The administrator will receive the following message at the bottom left of the page:

![](../static/ISA/Authenticator27.jpg)

- The logged in administrator will receive an email as under

![](../static/ISA/Authenticator28.png)

- Click the **Download File** button or click the link below and open the file in a spreadsheet application

![](../static/ISA/Authenticator29.png)

**Conclusion**

InstaSafe Authenticator enhances secondary authentication by way of Time-based One-Time Password (TOTP) and push notification-based approval. 
