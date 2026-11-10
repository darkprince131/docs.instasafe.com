---
comments: true
---
The Package Deployer feature gives the ability to Administrators to remotely push files and deploy software on end user machines who are connected to the ZTNA service.The feature can be used to install or update or uninstall software packages.
This feature gives Administrators the ability to utilize InstaSafe capabilities to deliver software updates, hotfixes, etc. to end-users instead of utilizing other 3 party tools (or Windows utilities) to achieve the same.
Currently the feature can distribute msi packages to end user machines.

Making use of the feature is a two-step process:

1.	Define the MSI package which needs to be deployed.

2.	Configure the users, user groups or devices where the package needs to be deployed.


## Step 1: Define the MSI package

1.	Click on Perimeter Management and then click on the Package Deployment tab.

2.	Click on the MSI Packages tab.

3.	Click on the ‘+’ icon to create a new MSI package which needs to be deployed on end user machines.

4.	Click on the ‘Choose file’ button and select the .msi file which needs to deployed.

5.	In the ‘File Path’ specify the location where the .msi file needs to be deployed.

6.	In the ‘Enter Description’ field give a name for the package deployment.

7.	Click on the ‘Upload’ button.

## Step 2: Deployment of the MSI package

1.	Click on the Deploy tab.

2.	Click on the ‘+’ icon to create a new deployment task.

3.	From the ‘Select Software’ dropdown select a MSI package which was defined in Step 1.

4.	Click on the ‘Next’ button.

5.	Select the Users, User Groups, Devices of the end user machine where the package needs to be installed. Either one or all of the three options can be selected for effective identification & deployment of the software package.

6.	Click on the ‘Next’ button.

7.	From the ‘Deployment Task’ dropdown, select whether you would like to Install, Update or Uninstall the software package.

8.	Review that the path populated in the ‘Enter a valid path’ textbox contains the correct path in the end user machine where the package needs to be deployed.

9.	Click on the ‘Deploy’ button.

10.	The deployment task is created successfully.

11.	Click on the created deployment task and the Status tab displays the Success, In Progress and Failure statistics of the deployment package

The below video illustrates the steps to define a package and to configure it for deployment in end user machines.


![Package Deployer](../static/ztaa/packagedeployer.gif)
