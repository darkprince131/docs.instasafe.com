---
comments: true
---
ZTAA supports integration with  different IAM services such as [Open-LDAP](https://www.openldap.org/), LDAP. Using this multiple users can be onboarded rapidly via syncing from organisations identity managment services. ZTAA can also be used to configure AD as a Primary mode for authentication. 

For  provisioning users through Open LDAP , a gateway  must be installed in the same subnet as the LDAP server.

P.S- Before syncing users from AD it must be ensured that the LDAP server is reachable via gateway.

##  Steps to add users via AD authentication Profile sync 

1. Go to **Directory Sync Profile** tab under the **Identity Management** section and Click on ‘Add New’ button.

![ImportingADusers](../static/ztaa/openldap1.png)

2. Enter Details in the form that appears and click on create  OpenLDAP profile. 

![ImportingADusers](../static/ztaa/openldap1.png)

| Terminologies |  |
| ------ | ------ |
| **Profile name**      | The bind DN DN is basically the credential you are using to authenticate against a LDAP. When using a bindDN it usually comes with a password associated with it.In other words when you specify a bindDN you are using that object security access to go through the LDAP tree. Bind distinguished name :CN=Administrator, CN=Users, DC=instalocal, DC=in" |
| **Bind distinguished name**      | The bind DN DN is basically the credential you are using to authenticate against a LDAP. When using a bindDN it usually comes with a password associated with it.In other words when you specify a bindDN you are using that object security access to go through the LDAP tree. Bind distinguished name :CN=Administrator, CN=Users, DC=instalocal, DC=in" |
| **Bind password** | Bind passwords are the login/password of an LDAP user that can access base DN.|
| **Base DN for search**  | "A base dn is the point from where a server will search for users.Base DN for search: DC=instalocal,DC=in"|
| **Email attribute name** | Each object in Active Directory Domain Services contains a set of attributes that define the characteristics of the object.We can user Email attribute name as a mail  |
| **Mobile attribute name** | Each object in Active Directory Domain Services contains a set of attributes that define the characteristics of the object.We can user mobile attribute name as a mobile or telephoneNumber. Mobile attribute name: mobile|
| **LDAP Groups**  | Groups are used to collect user accounts, computer accounts, and other groups into manageable units.CN=Demogroup,OU=Techteam,DC=instalocal,DC=in" |
| **LDAP url**   | An LDAP URL is a string that can be used to encapsulate the address and port of a directory server, the DN of an entry within that server, or the criteria for performing a search within that server.Here LDAP URL:ldap://10.2.0.05"|


    
** PS- All LDAP entities such as Bind User, Group name are to be refered by distinguihed name ** 




