---
comments: true
---
# Configuring Device Updates

The device update feature enables the ISA web portal administrator to remotely install software updates, upgrades, or hotfixes for individual users or user groups. Within the D**EVICES & CHECKS** menu on the ISA web portal, administrators can create a device update profile on the **Device Updates** page. This profile includes the hotfix or software upgrade file, along with parameters specifying how to apply the updates. These updates are generally delivered in MSI or EXE file formats and typically consist of bug fixes or security enhancements aimed at improving the overall functionality and security of the ISA User Agents.

**Create Device Updates**

- Login to the ISA web console using administrator credentials and navigate to the **Device Updates** page under the **DEVICES & CHECKS** menu.

![](../static/ISA/Configuring_Device_Update.jpg)

- Click the **Add** button at the top.

![](../static/ISA/Configuring_Device_Update1.jpg)

- On the **Add Update** window, under **Name**, enter a name for the update profile. **The name must be unique and must not be the same as another device update profile.** Characters A-Z, a-z, 0-9 are allowed in this field.  The maximum number of characters allowed is 50. All fields with an asterisk require to be filled-in.

![](../static/ISA/Configuring_Device_Update2.jpg)

- Click Upload file.

![](../static/ISA/Configuring_Device_Update3.jpg)

- Select the MSI or EXE file from the local drive. **The filename must be unique and must not be the same as the name of a file in another device update profile.**

![](../static/ISA/Configuring_Device_Update4.jpg)

- In the **Argument** field, enter the argument to be passed to the executable file for command land installation. If the update file format has EXE extension, the typical argument is “/S”. If the update file format has MSI extension, no argument is required, instead enter “0”.  

![](../static/ISA/Configuring_Device_Update5.jpg)

- Click the drop-down under **Install Schedule**.

![](../static/ISA/Configuring_Device_Update6.jpg)

- There are two options, **Immediate** and **After-Reboot**. Selecting **Immediate** will begin the installation process at once. The first cron job will create a temp folder with the executable file in it. The second cron job will execute the file. Selecting **After-Reboot** will install the update after the device is rebooted. The first cron job will create a temp folder with the executable file in it. The second cron job will execute the file after the device is rebooted.

![](../static/ISA/Configuring_Device_Update7.jpg)

- Click the drop-down under the **Post Validation Check**. Post validation check will verify whether a registry entry or file is present at a given location in the user’s device. 

![](../static/ISA/Configuring_Device_Update8.jpg)

- There are two options here, **Registry Key present** and **File present**. If **Registry Key present** is selected, enter the registry subkey or path to verify. For example, _HKLM\Software\WOW6432Node\InstaSafe\Hotfix31_. If the **File present** option is selected, enter the path of the file in the format C:\Program Files (x86)\InstaSafe\bin.

![](../static/ISA/Configuring_Device_Update9.jpg)

- Click the drop-down under **State**.

![](../static/ISA/Configuring_Device_Update10.jpg)

- Select either **Enabled** or **Disabled**. **Enabled** will install the update, and **Disabled** will not install the update. 

![](../static/ISA/Configuring_Device_Update11.jpg)

- Click **Save and Add new**.

![](../static/ISA/Configuring_Device_Update12.jpg)

- The device update profile is listed on the page. 

![](../static/ISA/Configuring_Device_Update13.jpg)

**Assign Device Update to User Group**

- Navigate to the **User Groups** page under the **USERS & GROUPS** menu.

![](../static/ISA/Configuring_Device_Update14.jpg)

- Click the name of the user group you want to assign the device update profile.

![](../static/ISA/Configuring_Device_Update15.jpg)

- In the **Group details** window, click **Edit**.

![](../static/ISA/Configuring_Device_Update16.jpg)

- Enable the **Device updates** toggle button.

![](../static/ISA/Configuring_Device_Update17.jpg)

- Click the **Select device updates** drop-down.

![](../static/ISA/Configuring_Device_Update18.jpg)

- Select the update profile. 

![](../static/ISA/Configuring_Device_Update19.jpg)

- Click **Update** to save.

![](../static/ISA/Configuring_Device_Update20.jpg)

**Assign Device Update to User** 

- Navigate to the **Users** page under the **USERS & GROUPS** menu.

![](../static/ISA/Configuring_Device_Update21.jpg)

- Click the name of the user you want to assign the device update profile.

![](../static/ISA/Configuring_Device_Update22.jpg)

- In the **User details** window, click **Edit**.

![](../static/ISA/Configuring_Device_Update23.jpg)

- Scroll down the window.

![](../static/ISA/Configuring_Device_Update24.jpg)

- Enable the **Device updates** toggle button.

![](../static/ISA/Configuring_Device_Update25.jpg)

- Click the **Select device updates** and select the update profile.

![](../static/ISA/Configuring_Device_Update26.jpg)

- Click **Update** to save.

![](../static/ISA/Configuring_Device_Update27.jpg)

**Edit Device Update**

- On the **Device Updates** page, click the name of the update profile you want to edit.

![](../static/ISA/Configuring_Device_Update28.jpg)

- In the window, click the **Edit** button.

![](../static/ISA/Configuring_Device_Update29.jpg)

- In the **Edit device update** window, make the necessary edits and click on **Save**.

![](../static/ISA/Configuring_Device_Update30.jpg)

**Delete Device Update**

- On the **Device Updates** page, enable the check box alongside the update profile you want to delete.

![](../static/ISA/Configuring_Device_Update32.jpg)

- Click the **Delete** button at the top.

![](../static/ISA/Configuring_Device_Update33.jpg)

- On the pop-up window, click **Yes, Delete it!**.

![](../static/ISA/Configuring_Device_Update34.jpg)

- On the bottom left of the page, the message **Successfully deleted device updates** is displayed. 

![](../static/ISA/Configuring_Device_Update35.jpg)

**Navigating the Device Updates list**

The **Device Updates** page allows easy pagination for viewing a large number of device update profiles. You can view the profiles by using the navigation control bar at the top right of the page.

Click the drop-down box to select the number of profiles to be displayed on the page. By default, it is set to display 10 profiles. You can change it to display either 30 or 50 profiles. 

![](../static/ISA/Configuring_Device_Update36.jpg)

Click the **Next** button to view the next page of device update profiles. Click the **Prev** button to view the previous page.

![](../static/ISA/Configuring_Device_Update37.jpg)

You can search device update profiles by name by entering it in the search box.

![](../static/ISA/Configuring_Device_Update38.jpg)

**Conclusion**

The device update feature allows the ISA web portal administrators to remotely install software updates, upgrades, or hotfixes for individual users or user groups.