---
comments: true
---
# Integrating Microsoft Authenticator for ISA Authentication

An organization may choose to increase their security posture with InstaSafe Secure Access’s (ISA) built-in Two Factor Authentication (TFA) that will prompt users for an OTP delivered to the registered email address and mobile number.

Further, ISA supports various authenticator apps to provide Time-based OTPs (TOTP) for Two-Factor Authentication. This would effectively eliminate the dependency on mobile networks for SMS OTPs and avoid deadlock scenarios where users can access corporate email for email OTPs only after the ISA User Agent is connected.

Microsoft Authenticator supports TOTP-based authentication. The Authenticator supports iOS and Android devices.

This article provides a step-by-step guide on configuring the Microsoft Authenticator app for Two-Factor Authentication (TFA) of ISA users.

**Opening the QR code on the ISA web portal**

- Open a web browser and open the ISA web console login page. 
- Enter the username and password of the user.

![](../static/ISA/MSAuth.jpg)

- Click Sign In.

![](../static/ISA/MSAuth1.jpg)

- When the user is prompted to select a method to receive the OTP, select OTP via SMS or OTP via Email.

![](../static/ISA/MSAuth2.jpg)

- Enter the OTP obtained in your email or via SMS.

![](../static/ISA/MSAuth3.jpg)

- Select Verify OTP. 

![](../static/ISA/MSAuth4.jpg)

- Once logged in, click the user profile on the top right side of the screen.

![](../static/ISA/MSAuth5.jpg)

- Select QR Code. The QR code option will be listed only if Two-Factor Authentication is enabled for the user.

![](../static/ISA/MSAuth6.jpg)

The QR code is displayed. 

![](../static/ISA/MSAuth7.jpg)

**Installing the Microsoft Authenticator app**

- Locate Microsoft Authenticator in App Store or Play Store.
- Select the download icon.

![](../static/ISA/MSAuth8.jpg)

- Select Open.

![](../static/ISA/MSAuth9.jpg)

- Select Accept.

![](../static/ISA/MSAuth10.jpg)

- Select Continue.

![](../static/ISA/MSAuth11.jpg)

- Select Scan a QR code.

![](../static/ISA/MSAuth12.jpg)

- Allow camera access.

![](../static/ISA/MSAuth13.jpg)

- Scan the QR code displayed on the web portal. 

![](../static/ISA/MSAuth14.jpg)

- Once the QR code is verified, the user is added to the app. The TOTP for the user is displayed.

![](../static/ISA/MSAuth15.jpg)

A new TOTP pin is generated every 30 seconds. Use the pin for secondary authentication when accessing the ISA web console or connecting the ISA User Agent. 

**Testing**

- Open a web browser and go to the ISA web console login page. Enter the username and password of the user and sign in.

![](../static/ISA/MSAuth16.jpg)

- When the user is prompted to select a method to receive the OTP, select TOTP on Authenticator. 

![](../static/ISA/MSAuth17.jpg)

- On the Microsoft Authenticator, copy the OTP generated. 

![](../static/ISA/MSAuth18.jpg)

- On the OTP prompt window, enter the OTP generated on the Microsoft Authenticator app.

![](../static/ISA/MSAuth19.jpg)

- Select Verify OTP.

![](../static/ISA/MSAuth20.jpg)

- The user is successfully logged into the ISA web console. 

![](../static/ISA/MSAuth21.jpg)

**Conclusion**

Microsoft Authenticator enhances secondary authentication by way of Time-based One-Time Password (TOTP). 
