---
comments: true
---
# Application Blocking

The **App-Blocking** feature empowers administrators to control system applications on end-user devices. Using this functionality, administrators can restrict one or more applications from running on end-user systems when InstaSafe is connected.

**Key Highlights:**

- Flexible Control: Administrators can enable app-blocking at both the User and Group levels.
- Enhanced Security: Prevents unauthorized or non-compliant applications from running during active connections, ensuring secure and policy-driven usage.

**Enabling the App-Blocking Feature:**

To activate this feature, administrators need to follow the steps below:

1.Go to the Device & Checks module in the InstaSafe Admin Console.

2.Select the Blocked Apps sub-module.

3.Click the Add button to create a new application profile.

![](../static/ISA/App%20Block/App_Block.jpg)

4.Enter a name for the application profile. Select Microsoft Windows for Windows-based applications. Specify the application name along with its extension (e.g., mspaint.exe).

5.Click Save and Add New to save the profile.

![](../static/ISA/App%20Block/App_Block1.jpg)

6.The newly created profile will appear in the Blocked Apps list.

![](../static/ISA/App%20Block/App_Block2.jpg)

**Assigning the Blocked Application:**

The blocked application can be assigned at either the User OR Group levels.

_User Level_

1.Navigate to the User and Group module in the InstaSafe Admin Console.

2.Select the User section and search for the user to whom the app-blocking feature should be applied.

![](../static/ISA/App%20Block/App_Block3.jpg)

3.Click on the user to enable Edit Mode.

![](../static/ISA/App%20Block/App_Block4.jpg)

4.Enable the following toggles:

- Device DLP and select the **Enable Block App Feature - Restart required**.

![](../static/ISA/App%20Block/App_Block5.jpg)

- Block Apps and select the previously created blocked application to prevent it from running on the user's system.

![](../static/ISA/App%20Block/App_Block6.jpg)

5.Click Update to apply the changes.

_Group Level_

1.Navigate to the User and Group module in the InstaSafe Admin Console.

2.Select the Group section and search for the group to which the app-blocking feature should be applied.

![](../static/ISA/App%20Block/App_Block7.jpg)

3.Click on the group to enable Edit Mode.

![](../static/ISA/App%20Block/App_Block8.jpg)

4.Enable the following toggles:

- Device DLP and select the **Enable Block App Feature - Restart required**.

![](../static/ISA/App%20Block/App_Block9.jpg)

- Block Apps and select the previously created blocked application to prevent it from running on the user's system.

![](../static/ISA/App%20Block/App_Block10.jpg)

5.Click Update to apply the changes.

**Disabling the App-Blocking Feature:**

_User Level_

1.Navigate to the User section and search for the user for whom app-blocking should be disabled.

![](../static/ISA/App%20Block/App_Block11.jpg)

2.Click on the user and enable Edit Mode.

3.Perform the following actions:

- Remove the **Enable Block App Feature - Restart required** from the Device DLP.

![](../static/ISA/App%20Block/App_Block12.jpg)

- Select **Disable Block App Feature - Restart required**. Also disable the **Block Apps** toggle

![](../static/ISA/App%20Block/App_Block13.jpg)

4.Click Update to save the changes.

_Group Level_

1.Navigate to the Group section and search for the group for which app-blocking should be disabled.

![](../static/ISA/App%20Block/App_Block14.jpg)

2.Click on the group and enable Edit Mode.

3.Perform the following actions:

- Remove the **Enable Block App Feature - Restart required** from the Device DLP.

![](../static/ISA/App%20Block/App_Block15.jpg)

- Select **Disable Block App Feature - Restart required**. Also disable the **Block Apps** toggle

![](../static/ISA/App%20Block/App_Block16.jpg)

4.Click Update to save the changes.

**Limitations of the App-Blocking Feature**

1. It is recommended to make changes to the app-blocking configuration during non-working hours or when the user is not connected to the InstaSafe Agent.
2. The admin can enable either the "Enable App Block" feature or the "Disable App Block" feature for a particular user at a time.
3. Enabling both simultaneously for the same user may cause the app-blocking feature to malfunction.
4. Enabling or disabling the app-blocking feature for a user requires a one-time system restart for the changes to take effect.
5. If an application is blocked through the InstaSafe App-Blocking feature, the user will not be able to use the application until the InstaSafe Agent is manually disconnected. The application will remain blocked as long as the agent is active, even if changes are made.
