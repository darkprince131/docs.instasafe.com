---
comments: true
---
# Google Authenticator

An organization may choose to increase their security posture with InstaSafe Secure Access’s (ISA) built-in Two Factor Authentication (TFA) that will prompt users for an OTP delivered to the registered email address and mobile number.

Further, ISA supports various authenticator apps to provide Time-based OTPs (TOTP) for Two-Factor Authentication. This would effectively eliminate the dependency on mobile networks for SMS OTPs and avoid deadlock scenarios where users can access corporate email for email OTPs only after the ISA User Agent is connected.

Google Authenticator supports TOTP-based authentication. The Authenticator supports iOS and Android devices.

This article provides a step-by-step guide on configuring the Google Authenticator app for Two-Factor Authentication (TFA) of ISA users.

**Opening the QR code on the ISA web portal**

- Open a web browser and log into the ISA web portal. 
- Enter the username and password of the user and click on sign in.

![](../static/ISA/GoogleAuth.jpg)

- When the user is prompted to select a method to receive the OTP, select OTP via SMS or OTP via Email.

![](../static/ISA/GoogleAuth1.jpg)

- Enter the OTP obtained in your email or via SMS and click on Verify OTP. 

![](../static/ISA/GoogleAuth2.jpg)

Once logged in, click the user profile on the top right side of the screen.

![](../static/ISA/GoogleAuth3.jpg)

Select QR Code. The QR code option will be listed only if Two-Factor Authentication is enabled for the user.

![](../static/ISA/GoogleAuth4.jpg)

The QR code is displayed. 

![](../static/ISA/GoogleAuth5.jpg)

**Installing the Google Authenticator app**

- Locate Google Authenticator in App Store or Play Store.
- Select the download icon.

![](../static/ISA/GoogleAuth6.jpg)

- Select Open.

![](../static/ISA/GoogleAuth7.jpg)

**Adding the ISA User by QR Code**

- You can login to the authenticator using your existing Google account or continue without logging in. On the Google Authenticator, select Get started.

![](../static/ISA/GoogleAuth8.jpg)

- On the Set up your first account screen, select Scan a QR code. 

![](../static/ISA/GoogleAuth9.jpg)

- Scan the QR code displayed on the web portal.

![](../static/ISA/GoogleAuth10.jpg)

- The user account is added to the authenticator. 

![](../static/ISA/GoogleAuth11.jpg)

- Once the user is successfully authenticated, the user is added to the app. The TOTP pin for the user is displayed. 

A new TOTP pin is generated every 30 seconds. Use the pin for secondary authentication when accessing the ISA web console or connecting the ISA User Agent. 

- Back on the QR code window of the ISA web portal, enter the TOTP in the field under the QR code and click Submit.

![](../static/ISA/GoogleAuth12.jpg)

_Note: The OTP shown on the screen for example purposes only._

- Once the OTP is verified, a message that the OTP is verified successfully is displayed at the bottom-left of the screen.

![](../static/ISA/GoogleAuth13.jpg)

- The QR code is now attached to the authenticator app and is not available for scanning by other authenticator apps. However, manually adding the user to an authenticator app using the username and password is still possible. To verify, click the QR code option again.

![](../static/ISA/GoogleAuth14.jpg)

_Note: To re-enable the QR code, contact the administrator of the ISA web portal._

**Adding the ISA user by adding the QR secret key**

Instead of scanning the QR key, adding a user account to an authenticator using its secret encoded in it, you must first decode the QR code. There are free decoders available on the Internet to decode the ISA QR code. The information required from a decoded QR code are the account name and secret key, which is a 64-bit hexadecimal string. For example, the account name and secret key of this user is the following:

Account name =jsmith01@isa-training.com

Secret key = GE2GKMTGGYZWGOBYGZSDSY3FGNSDMYLEMM3WMMRRGY3DKN3FMU2DOYRZHBSGINTE

- On the Set up your first account screen, select Enter a setup key. 

![](../static/ISA/GoogleAuth15.jpg)

- On the Enter account details screen, enter the account name and secret key.

![](../static/ISA/GoogleAuth16.jpg)

- Click on Add.

![](../static/ISA/GoogleAuth17.jpg)

- The account is added to the authenticator.

![](../static/ISA/GoogleAuth18.jpg)

**Testing**

- Open a web browser and go to the ISA web console login page. Enter the username and password of the user and sign in.

![](../static/ISA/GoogleAuth19.jpg)

- When the user is prompted to select a method to receive the OTP, select TOTP on Authenticator. 

![](../static/ISA/GoogleAuth20.jpg)

_Note: Do not select Approve Push Notification on Authenticator, it’s supported only on InstaSafe Authenticator._

- On the OTP prompt window, enter the OTP generated on the Google Authenticator app and select Verify OTP.

![](../static/ISA/GoogleAuth21.jpg)

- The user will be successfully logged in. 

![](../static/ISA/GoogleAuth22.jpg)

**Conclusion**

Google Authenticator enhances secondary authentication by way of Time-based One-Time Password (TOTP).

