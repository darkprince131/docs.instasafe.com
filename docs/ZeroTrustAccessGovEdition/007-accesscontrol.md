---
comments: true
---
# Role-Based Application Access Control

Access rules are how the InstaSafe console grants application access by role rather than
by individual. Users are grouped by their role in the organisation, the resources they
need are defined as an application group, and a single access rule binds the two. These
are identity-based rules that permit access on the basis of the role of the user in the
organisation, as opposed to parameters such as the source IP address.

Rules are defined on the **Access Rules** page, under the **ACCESS POLICIES** menu of the
web console.

## What an access rule is made of

| Field | What it holds |
|---|---|
| **Name** | A name for the rule. A–Z, a–z, 0–9, up to 50 characters. |
| **Source Type** | **User**, **User Group**, or **Application**. Choosing User Group is what makes the rule role-based. |
| **Source** | The user groups the rule applies to. More than one can be added. |
| **Destination Type** | **Application** or **Application Group**. |
| **Destination** | The application groups the rule grants or denies. More than one can be added. If Destination Type is Application, the application is defined in the rule by IP address or network plus one or more port numbers. |
| **Action** | **Allow** or **Deny**. |

## Granting access to a role in three steps

1. **Group the users by role.** Create the group on the
   [Local Groups](../i365customprivateedition/057-Configuring_Local_Groups.md) page, or import it from
   [Microsoft Active Directory](../i365customprivateedition/070-Configuring_Microsoft_Active_Directory__AD__Integration.md)
   so the directory group becomes the role.
2. **Define what that role reaches.** Pair the IP addresses or networks with their
   services on the [Application Groups](../i365customprivateedition/055-Configuring_Application_Groups.md) page.
   Services themselves are defined under
   [Application Services](../i365customprivateedition/056-Configuring_Application_Services.md).
3. **Bind them with one access rule.** Source Type **User Group** → Source *the role* →
   Destination Type **Application Group** → Destination *the resources* → Action
   **Allow**. Every member of the group inherits the entitlement, and a user who joins or
   leaves the group gains or loses it without the rule being touched.

A **Deny** rule is written the same way and is used to carve an exception out of a
broader allow.

## Configure Access Rules

The Access Rules page on the ISA web portal allows administrators to define rules to allow
or deny remote user access to corporate resources. The following types of access rules can
be created:

- Allow or deny access to an application or application group from one or more users. The application group must be pre-defined on the Application Group page. The application must be defined within the access rule by specifying an IP address or network with one or more port numbers separated by commas.

- Allow or deny access to an application or application group from one or more user groups.  The application group must be pre-defined on the Application Group page. The application must be defined within the access rule by specifying an IP address or network with one or more port numbers separated by commas.

- Allow or deny access to an application or application group from an IP address or network and one or more port numbers. The application group must be pre-defined on the Application Group page. The application must be defined within the access rule by specifying an IP address or network with one or more port numbers separated by commas.

**Features**

- When an allow rule is defined, the ISA controller will initiate a process to ensure proper route configuration. It involves two distinct steps:

    -  The controller will send the relevant route details to the ISA User Agent. These details are used to configure routes on the end-user device.
    -   Simultaneously, the controller will send route information, including port numbers, to the Gateway Agent for configuring routes on the designated gateway.

- Access rules are enforced based on the specificity of the rule. A more specific rule takes precedence over a less specific rule. 

**Examples**

- A rule that applies to an IP address has priority over a rule that applies to a network, all other parameters being equal. 
- A deny rule to an IP address takes precedence over an allow rule to a network, all other parameters being equal.
- Access rules are only applicable to remote users connecting using the ISA User Agent. Rules defined on the Access Rule page do not govern logging into the ISA web portal.

This user guide describes the various configuration options to manage access rules on the ISA web portal. 

**Add Access Rules**

- Login to the ISA web console using administrator credentials.

![](../static/ISA/accessrules.png)

- Navigate to the Access Rules page under the ACCESS POLICIES menu.

![](../static/ISA/accessrules1.png)

- Click the Add button at the top.

![](../static/ISA/accessrules2.png)

- On the Add access rule window, under Name, enter a name for the access rule. Characters A-Z, a-z, 0-9 are allowed in this field.  The maximum number of characters allowed is 50.

![](../static/ISA/accessrules3.png)

- Click the Source Type drop-down.

![](../static/ISA/accessrules4.png)

- Select User, User Group, or Application. In this example, we select User Group.

![](../static/ISA/accessrules5.png)

- Click the Source field.

![](../static/ISA/accessrules6.png)

- From the drop-down list, select the user group. Multiple user groups can be added to this field.

![](../static/ISA/accessrules7.png)

- Click the Destination Type drop-down. 

![](../static/ISA/accessrules8.png)

- Select Application or Application Group. 

![](../static/ISA/accessrules9.png)

- Select the application groups. Multiple application groups can be added to the field. 

![](../static/ISA/accessrules10.png)

- Click Action. 

![](../static/ISA/accessrules11.png)

- Select either Allow or Deny.

![](../static/ISA/accessrules12.png)

- Click Save and Add new.

![](../static/ISA/accessrules13.png)

- The new access rule is listed on the page. 

![](../static/ISA/accessrules14.png)

**Edit Access Rule**

- On the Access Rule page, click the name of the access rule you want to edit.

![](../static/ISA/accessrules15.png)

- In the ACL details window, click the Edit button.

![](../static/ISA/accessrules16.png)

- In the Update access rule window, you can edit the Destination, Destination Type, Source, and Source Type fields. You can add or delete the user, user group, application, or application group by clicking the “x” icon. 

![](../static/ISA/accessrules17.png)

- Click Update to save the change.

![](../static/ISA/accessrules18.png)

**Add Access Rules in Bulk**

This option allows the administrator to add a large number of access rules at once. 

Supported fields in the file are:

- **Name** – A name for the access rule.
- **Source Type** – Either user or user group.
- **Source** – Enter the name of the users or user groups separated by commas. 
- **Destination Type** – Either application or application group.
- **Destination** – If Destination Type is set to Application Group, enter the name of the application groups separated by commas.. If Destination Type is set to Application, leave the field blank. 
- **IP Address** – If Destination Type is set to Application, enter the IP addresses of remote resources separated by commas. If Destination Type is set to Application Group, leave the field blank. 
- **Services** - If Destination Type is set to Application, enter the port numbers of remote resources separated by commas. If Destination Type is set to Application Group, leave the field blank.

- On the Access Rules page, click the Add button.
    
![](../static/ISA/accessrules19.png)

- Under Bulk upload Access Rule, click Download Sample CSV.

![](../static/ISA/accessrules20.png)

- Open the file using a spreadsheet application.

![](../static/ISA/accessrules21.png)

- The sample CSV file is filled with sample values. Enter your information as per the samples provided.

![](../static/ISA/accessrules22.png)

- Enter the information in their respective fields and save it.

![](../static/ISA/accessrules23.png)

- Under Upload the file, click Choose File and select the file from the saved location.

![](../static/ISA/accessrules24.png)

- Click Upload.

![](../static/ISA/accessrules25.png)

- In the Uploaded Access Rules window, review the information and click Save ACLs.

![](../static/ISA/accessrules26.png)

- The newly created access rules are listed on the page.

![](../static/ISA/accessrules27.png)

**Download Access Rules List** 

ISA web portal administrators can download the complete list of access rules by clicking on the CSV button on the Access Rules page. An email with the link to download the file in CSV format is sent to the logged-in administrator’s email address. The file has the following information:

- **Name** – Names of the access rule.
- **Source Type** – Either user or user group.
- **Source** –Name of the users or user groups. 
- **Destination Type** – Either application or application group.
- **Destination** – If Destination Type is Application Group, the names of the application groups. If Destination Type is set to Application, the IP addresses and service names of the applications separated by hyphens.

- On the Access Rules page, click the CSV button at the top.

![](../static/ISA/accessrules28.png)

- A message that an email is scheduled to be sent to the administrator’s email address is displayed.

![](../static/ISA/accessrules29.png)

- Click the download link within the email.

![](../static/ISA/accessrules30.png)

- View the file in a spreadsheet application.

![](../static/ISA/accessrules31.png)

**Delete Access Rules**

On the Access Rules page, enable the check box alongside the access rules you want to delete. 

![](../static/ISA/accessrules32.png)

- Click the Delete button at the top.

![](../static/ISA/accessrules33.png)

- On the pop-up window, click Yes, Delete it!.

![](../static/ISA/accessrules34.png)

- On the bottom left of the page, the message ACLs have been scheduled to be deleted is displayed. 

![](../static/ISA/accessrules35.png)

**Navigating the Access Rule List**

The Access Rules page allows easy pagination for viewing a large number of access rules. You can view the access rules by using the navigation control bar at the top right of the page.

Click the drop-down box to select the number of rules to be displayed on the Access Rules page. By default, it is set to display 10 rules. You can change it to display either 30 or 50 rules. 

![](../static/ISA/sessionlog6.png)

Click the Next button to view the next page of rules. Click the Prev button to view the previous page. 

![](../static/ISA/sessionlog7.png)

You can search access rules by name by entering it in the search box. 

![](../static/ISA/accessrules36.png)

