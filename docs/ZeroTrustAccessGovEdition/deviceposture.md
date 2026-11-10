---
comments: true
---
The InstaSafe Zero Trust security framework verifies both users identify and device before enabling access to critical applications. Under the tenets of Zero Trust, only verified devices and users are granted access to assets, applications and systems.
Device posture is a measurement of how secure and compliant the device is. By monitoring and enforcing device posture, organizations can prevent malicious devices from accessing sensitive information and critical applications.

InstaSafe ZTAA empowers administrators to ensure that only devices that comply with predefined security policies can access the enterprise applications from the agent.

**Device posture attributes available in ZTAA**

* Application
* Application Access Time
* AntiVirus Enabled Name
* AntiVirus Installed Name
* AntiVirus Updated Name
* Certificate Thumbprints
* Country Code
* Disk Serial Number
* Geolocatoin
* IP Address
* Mac Address
* Motherboard ID
* OS Build Version
* OS Family
* OS Major Version
* OS Minor Version
* System Domain Name
* System MacAddress
* System Serial number
* Windows Hotfixes
* Browser ID
* UA Suffix

An organization has provisioned application access over the InstaSafe Zero Trust platform (ZTAA) and wants to **enforce a device posture check that AntiVirus should be available in the end user devices before application access**. A device compliance rule for AntiVirus check can be defined in the ZTAA platform.
Any user trying to connect to the InstaSafe ZTNA agent for application access will be restricted from connecting to the agent if they do not have AntiVirus installed in their device and will be presented with a message as shown in the below screenshot.

![](../static/ztaa/DC_Antivirus.gif)


An organization has defined a device compliance rule for **users to connect only from devices which has a Genuine Windows OS**. Any user trying to connect to the InstaSafe ZTNA agent for application access will be restricted from connecting to the agent and will be presented with a message as shown in the below screenshot if their Windows machine does not have a genuine licensed OS.

![](../static/ztaa/DC_GenuineOS.gif)


Implementation of Device posture check in ZTAA is a two step process:

1. Create a device posture profile dataset.
2. Add the device posture profile dataset in Access Policy.

**Create Device posture profile in ZTAA**

To create a device posture profile dataset in the ZTAA console follow the below steps:

1. Click on “Configuration” in the left menu.
2. Navigate to the “Data Management” tab.
3. Click on the “+” icon to create a new dataset.
4. Select the device posture attribute available in the “Select Variable” dropdown.
5. Enter the Dataset name and description click on “Add Dataset”.
6. Search for the created Dataset and click on Edit.
7. Click on the “Records” and add a record value.

**Apply Device posture profile in Access Policy**

To assign a device posture dataset to access policy perform the below steps:

1. Click on “Access Policy” in the left menu.
2. Search for the access policy to which you would like to add a device posture dataset.
3. Select the Access Policy and click on Edit.
4. Navigate to the “Manage Rules” tab.
5. Click on the “+Rule” and select the device posture attribute.
6. Select the device posture profile dataset and click on “Update Manage Rules”.

![](../static/ztaa/deviceposture.gif)

After the above configurations are performed, users when they login to the ZTAA agent will not have access to the applications to which they are granted access to if their device does not comply with the configured device posture profile.
