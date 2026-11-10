---
comments: true
---
# SAML IDP

## InstaSafe – Freshworks SSO Configuration Guide (SAML 2.0)


This guide explains how to configure **Single Sign-On (SSO)** between **InstaSafe** (Identity Provider - IdP) and **Freshworks** (Service Provider - SP).

After configuration, users can securely access Freshworks applications without entering separate passwords.

This integration uses the **SAML 2.0** standard to establish trust between InstaSafe (IdP) and Freshworks (SP). Once enabled, InstaSafe becomes the authentication authority for Freshworks logins.



## Benefits

- Passwordless access to Freshworks applications  
- Centralized authentication through InstaSafe  
- Enforcement of MFA and access policies  
- Reduced risk of credential theft  
- Simplified user lifecycle management  

InstaSafe validates user identity and security posture before granting access to Freshworks.



## When to Enable Freshworks SSO

Enable SSO if:

- You want centralized authentication using InstaSafe  
- You need to enforce MFA before Freshworks access  
- You want unified visibility of user access  
- You aim to reduce password-related security risks  
- Your organization uses Freshworks as a customer engagement platform  

---

## Prerequisites

Before configuring SSO, ensure:

- Administrator access to the **Freshworks Admin Console**
- Administrator access to the **InstaSafe Admin Portal**
- A verified domain in Freshworks
- SAML configuration access in both platforms
- Freshworks **ACS URL (Assertion Consumer Service URL)**
- Freshworks **SP Entity ID**
- InstaSafe **IdP Entity ID**
- InstaSafe **SAML Login URL**
- InstaSafe **IdP Certificate**

---

## Step-by-Step Configuration


## Configuration in Freshworks

### Step 1: Login
Log in to Freshworks using **administrator credentials**.



### Step 2: Navigate to SSO Settings
- Go to **Security Settings**
- Navigate to **SSO**
- Click **Edit Configuration**



### Step 3: Select Default Login Methods
Click **Default Login Methods**.



### Step 4: Enable SSO
Enable the **SSO toggle**.



### Step 5: Select SAML
Choose **SAML** for SAML-based SSO configuration.



### Step 6: Copy SP Details
From Freshworks, copy:

- **ACS URL**
- **SP Entity ID**

You will need these details in the InstaSafe configuration.



### Step 7: Enter Tenant Details

Provide the following details from InstaSafe:

- Enter the **Entity ID** (http://<tenant>.instasafe.com)

- Enter the **SAML SSO Url** (https://<tenant>.instasafe.com/signin)

### Step 8: Upload IdP Certificate

After configuring the SAML IdP in InstaSafe and downloading the certificate:

1. Copy the **IdP Certificate**

2. Paste it into the **Certificate field** in Freshworks  
 (Setup SSO with SAML → Certificate)

> **Note:** The certificate is downloaded from InstaSafe under Settings → SAML IdP Configuration.



### Step 9: Complete Setup
Click **Configure SSO** to finish the Freshworks configuration.



# Configuration in InstaSafe (ISA)



### Step 1: Login
Log in to the **i365 Admin Portal** using administrator credentials.



### Step 2: Navigate to SAML IdP
- Go to **IDAM**
- Click **SAML IdP**
- Click **Add**



### Step 3: Enter Basic Details

Fill in the required fields:

| Field     | Detail |
|------------|----------|
| Name | The name of the SAML configuration (for internal identification in ISA) |
| SP Type | Select appropriate type |

#### SP Type Options

- **Google** – For Google Workspace  
- **Azure** – For Microsoft Azure / Office 365  
- **Custom** – For any other SAML-supported application (such as Freshworks)

For Freshworks, select **Custom**.



### Step 4: Enter SP Details

Paste the following details (copied from Freshworks):

- **ACS URL**
- **SP Entity ID**

Enter them in the respective fields in the InstaSafe console.



### Step 5: Save Configuration
Click **Save** to create the SAML IdP configuration.



### Step 6: Download IdP Certificate

After saving:

- Select the created configuration
- Click **Download IdP Certificate**
- Use this certificate in the Freshworks configuration



# Verification & Testing

After completing configuration on both platforms:

1. Log out of Freshworks.
2. Attempt login again.
3. Verify redirection to InstaSafe for authentication.
4. Confirm successful login post-authentication.



# Configuration Flow Summary

1. Enable SAML SSO in Freshworks.
2. Copy ACS URL and SP Entity ID.
3. Create SAML IdP configuration in InstaSafe.
4. Download InstaSafe IdP Certificate.
5. Upload certificate and IdP details in Freshworks.
6. Save and test SSO.



# Security Best Practices

- Enforce MFA policies in InstaSafe before granting access.
- Periodically rotate certificates.
- Validate domain ownership in Freshworks.
- Monitor SSO login logs for suspicious activity.
- Restrict admin access to SAML configuration settings.



# Conclusion

Once configured, InstaSafe acts as the trusted authentication authority for Freshworks.  
All user logins are validated through InstaSafe, ensuring secure, centralized, and policy-driven access control.

