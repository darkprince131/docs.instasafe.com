---
comments: true
---

### Issue in creating users in Entra after federating domain with InstaSafe ZTNA 

Once you federate a given Microsoft 365 domain with an external identity provider, like InstaSafe ZTNA, you may no longer create new users in that domain from the Entra or Microsoft/Office 365 consoles. You will need to create the users in your source Active Directory and have Entra Connect sync them from the on-premises directory into the cloud. See additional explanation on this topic in the Microsoft troubleshooting article [You can't assign a federated domain to a user in the Microsoft 365 Admin Center](https://learn.microsoft.com/en-us/microsoft-365/troubleshoot/domain-management/cannot-assign-federated-domain-to-user).

Microsoft O365 Admininstrators can reach out to the InstaSafe Support team to manage the federation in case of any issues.
