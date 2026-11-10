---
comments: true
---
# Create Sub-Admins

**Admins**

The ISA web console administrator has full access within the web console. The ISA web console administrator’s roles and rights are created by InstaSafe. This user has the following rights:

- Maintain Users, Applications, and Access Control List
- Provision and Deprovision Controller and Gateways
- Enable/Disable features inside Tenants.
- Create Sub-Admin Roles and define their access rights.
- Monitoring

**Sub-Admins**

The sub-admin role is created by the ISA web console administrator or admin. Sub-admins are configured to do a particular activity and have limited access. The administrator defines the rights and roles of the sub-admins and can further control them by authorizing read or write permission to any feature within the ISA web console like User, Application, ACL, Controller, Gateway. When a sub-admin is given read-only access, all configuration options, such as add, edit, delete, and save, will not be visible.   

## **How to Create a Sub-Admin Role?**

Note:

- There is no defined limit to the number of roles that can be created on this page. 
- Each role can be assigned to more than one user.

Before creating a sub-admin, its role must be defined.

- Login to the ISA web portal with administrator credentials that have the rights to create sub-admins.
- Navigate to the SUB ADMINS & ROLES > Sub Admin Roles page

![](../static/ISA/CreatingSub-Admins/CreatingSub-Admins1.png)

-  Click the Add button

![](../static/ISA/CreatingSub-Admins/CreatingSub-Admins2.png)

- In the Edit Sub Admin Role window, under Role Name, enter a name for the role.

![](../static/ISA/CreatingSub-Admins/CreatingSub-Admins3.png)

- Select the checkboxes next to the features that should be assigned read or write permissions for this sub-admin.
- Click Save and Add new to create the sub-admin role.

![](../static/ISA/CreatingSub-Admins/CreatingSub-Admins4.png)

- The newly created role will be listed on the page.

![](../static/ISA/CreatingSub-Admins/CreatingSub-Admins5.png)

- Similarly, created another role.

![](../static/ISA/CreatingSub-Admins/CreatingSub-Admins6.png)

- The newly created role will be listed on the page. 

![](../static/ISA/CreatingSub-Admins/CreatingSub-Admins7.png)

**Create a Sub-Admin**

    - The number of sub-admins that can be created on this page is limited to the number of users 
    - Each sub-admin can be assigned only one sub-admin role. 
    - Once a sub-admin is assigned a role, the user will not be listed when creating a new sub-admin.

- Navigate to the SUB ADMINS & ROLES > Sub Admins page

![](../static/ISA/CreatingSub-Admins/CreatingSub-Admins8.png)

- Click the Add button at the top.

![](../static/ISA/CreatingSub-Admins/CreatingSub-Admins9.png)

- In the Sub Admin window, click on the drop-down to view users.
- From the drop-down list, select a user that needs to be assigned the sub-admin role.
- Under the Select Type drop-down, select Sub Admin.

![](../static/ISA/CreatingSub-Admins/CreatingSub-Admins10.png)

- Under Select Role, select the object that has the roles defined for this sub-admin.

![](../static/ISA/CreatingSub-Admins/CreatingSub-Admins11.png)

- Click Save and Add new.

![](../static/ISA/CreatingSub-Admins/CreatingSub-Admins12.png)

- The new sub-admin will be listed on the page.   

![](../static/ISA/CreatingSub-Admins/CreatingSub-Admins13.png)

- Create a new sub-admin and assign the object that has the roles defined for this sub-admin. 
- Click Save and Add new.   

![](../static/ISA/CreatingSub-Admins/CreatingSub-Admins14.png)

**Conclusion**

Sub-admin roles allow administrators to grant restricted access to users of the ISA web portal by assigning read/write permissions to specific features within the portal.

## **Manage Sub-admins Roles**

<!-- **Sub-Admins**

The sub-admin role is created by the ISA web console administrator or admin. Sub-admins are configured to do a particular activity and have limited access. The administrator defines the rights and roles of the sub-admins and can further control them by authorizing read or write permission to any feature within the ISA web console like User, Application, ACL, Controller, Gateway. -->

**Edit a Sub-Admin Role**

- Log into the ISA web portal with administrator credentials with rights to create sub-admins, such as the Company Admin. 
- Navigate to the SUB ADMINS & ROLES > Sub Admin Roles page.
- On the Sub Admin Roles page, click on the name of the sub-admin role.

![](../static/ISA/Editing,Disabling,andDeletingSub-admins/Editing_Disabling_andDeletingSub-admins1.png)

- On the Sub Admin Role Details window, click the Edit button.

![](../static/ISA/Editing,Disabling,andDeletingSub-admins/Editing_Disabling_andDeletingSub-admins2.png)

- Select the checkboxes next to the features to enable or disable the read or write permissions for this sub-admin.
- Click Save and Add new to update the change.
![](../static/ISA/Editing,Disabling,andDeletingSub-admins/Editing_Disabling_andDeletingSub-admins3.png)

**Delete a Sub-Admin Role**

- On the Sub Admin Roles page, click on the name of the sub-admin role.

![](../static/ISA/Editing,Disabling,andDeletingSub-admins/Editing_Disabling_andDeletingSub-admins4.png)

- On the Sub Admin Role Details window, click the Delete button.

![](../static/ISA/Editing,Disabling,andDeletingSub-admins/Editing_Disabling_andDeletingSub-admins5.png)

- In the pop-up window, click the Yes, Delete it button.

![](../static/ISA/Editing,Disabling,andDeletingSub-admins/Editing_Disabling_andDeletingSub-admins6.png)

**Edit a Sub-Admin**

- Navigate to the Sub Admins page.
- On the Sub Admins page, click on the username of the sub-admin.

![](../static/ISA/Editing,Disabling,andDeletingSub-admins/Editing_Disabling_andDeletingSub-admins7.png)

- In the Edit Admin Details window, click the Edit button at the top.

![](../static/ISA/Editing,Disabling,andDeletingSub-admins/Editing_Disabling_andDeletingSub-admins8.png)

- In the Edit Sub Admin window, click the Role drop-down and select the object that has the roles defined for this sub-admin.

![](../static/ISA/Editing,Disabling,andDeletingSub-admins/Editing_Disabling_andDeletingSub-admins9.png)

- Click Update to save the change.

![](../static/ISA/Editing,Disabling,andDeletingSub-admins/Editing_Disabling_andDeletingSub-admins10.png)

- Alternatively, click Reset to set the fields to its default settings.

![](../static/ISA/Editing,Disabling,andDeletingSub-admins/Editing_Disabling_andDeletingSub-admins11.png)

**Disable a Sub-Admin**

- On the Sub Admins page, click on the username of the sub-admin.
- In the Edit Admin Details window, click the Disable button at the top.

![](../static/ISA/Editing,Disabling,andDeletingSub-admins/Editing_Disabling_andDeletingSub-admins12.png)

- In the pop-up window, click the Yes, Disable it button.

![](../static/ISA/Editing,Disabling,andDeletingSub-admins/Editing_Disabling_andDeletingSub-admins13.png)

_Disabling a user will return the user to end-user role with only Agent Download and Profile Settings options accessible._

**Delete a Sub-Admin**

- On the Sub Admins page, click on the username of the sub-admin.
- In the Edit Admin Details window, click the Delete button at the top.

![](../static/ISA/Editing,Disabling,andDeletingSub-admins/Editing_Disabling_andDeletingSub-admins14.png)

- In the pop-up window, click the Yes, Delete it button.

_Deleting a user will not delete the user from the Users page. Instead, it will return the user to end-user role with only Agent Download and Profile Settings options accessible._

**Conclusion**

Sub-admin roles allow administrators to grant restricted access to users of the ISA web portal by assigning read/write permissions to specific features within the portal.
