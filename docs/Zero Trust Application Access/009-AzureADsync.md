---
comments: true
---

# Import Users from Azure AD

ZTAA supports user synchronization directly from **Azure Active Directory (Azure AD)**, enabling seamless onboarding and identity management. Azure AD acts as the **Identity Provider (IdP)**, while ZTAA functions as the **Service Provider (SP)**.



##  Steps to Import Users from Azure AD

### 1. Azure AD Preparation

- Log in to your [Azure Portal](https://portal.azure.com).
- Create a **Pure Azure user** (without a federated domain, only with a subdomain).
- Create a **Group** in Azure AD and add the users you want to sync.



### 2. Configure Azure AD Sync in ZTAA

- Log in to the **ZTAA Console** as an admin.
- Navigate to:  
  `Identity Management > Directory Sync Profile`

  ![ ](../static/ztaa/azure-ad-1_go_to_directory_sync.png)


- Click **Add New Profile (+)** and select **Azure AD**.
- Set a **Default Password** for imported users.

  ![ ](../static/ztaa/azure-ad-2_select_ad.png)

  ![ ](../static/ztaa/azure-ad-3_enter_password.png)

- You’ll be redirected to the Microsoft login page.
- Log in using your Azure AD admin credentials (e.g., `user@devinsta.onmicrosoft.com`).
- After successful authentication, the Azure AD profile will be created in ZTAA.

  ![ ](../static/ztaa/azure-ad-4_enter_email.png)

  ![ ](../static/ztaa/azure-ad-5_enter_password.png)


### 3. Sync Azure Group with ZTAA

- Open the created **Azure AD Profile** in ZTAA.
- Add the Azure Group (created earlier) to this profile.
- Click **Sync** to import users.
- Once synced, verify that **users and groups** are listed in ZTAA.

  ![ ](../static/ztaa/azure-ad-6_sync_user_.png)

  ![ ](../static/ztaa/azure-ad-7_user_listed_in_ztaa.png)


### 4. Testing Azure User Login

- Go to the **ZTAA login page**.
- Log in using the synced Azure AD user's credentials.
- Upon successful authentication, the user will be redirected to the **ZTAA Console**.

  ![ ](../static/ztaa/azure-ad-8_azure_user_login.png)

  ![ ](../static/ztaa/azure-ad-9_secondary_login.png)

  ![ ](../static/ztaa/azure-ad-10_loggedin_user.png)


##  Summary

| Component       | Role                  |
|----------------|-----------------------|
| **ZTAA**        | Service Provider (SP) |
| **Azure AD**    | Identity Provider (IdP) |
| **Users/Groups**| Synced via Directory Profile |


 



