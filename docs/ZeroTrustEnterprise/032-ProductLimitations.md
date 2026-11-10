---
comments: true
---
_Last Update Date: 24th Dec’2022_

**Overview**

This section is used to report InstaSafe Product Known Issues. 

**How Often the List is Updated**

The InstaSafe ZTAA Product Known Issue list is updated whenever any new issues is identified or fixed. However, we also review and update the list on monthly basis.
 
**Contact**

For any question regarding the below reported issues or the recommendation for the work around, please reach out to InstaSafe Support Team [support@instasafe.com](support@instasafe.com)

## Product Name: InstaSafe Zero Trust Access (ZTA) ##

**The end users will not able to access the applications in few of the below mention scenarios. The application will show as Unstable if any of the below scenarios applicable.**
 
Issue Description: User access gets disconnected and not able to access applications.
 
•	Dynamic IP at User End Point: if the IP address keeps changing at the end point, user might face uncertainty of application access.

•	Customer firewall at gateway; Misconfiguration: if the firewall at customer gateway is misconfigured.

•	Change VMs: if an existing Gateway is migrated o new VM after the complete setup is done. 

Component(s) : ZTA Agent, Gateway

Severity: Medium
 
Workarounds or Recommendations: Users are recommended to disconnect from VPN and reconnect the same. This will allow user to establish the connection again hence will able to access the application.
In case of firewall misconfiguration, Admin are requested to make the necessary changes to allow the traffic.
In case of customer want to change the VM where the gateway is installed, we recommend reaching out to InstaSafe Support team for assistance.
 


**Application shows unstable if one gateways is down in case of multiple gateways configured.**
 
Issue Description: 
If customer have multiple gateways deployed for accessing multiple applications through each of the gateways, then in some situation where one of the gateways goes down for some reason, the Applications that are accessed through the other gateways will also show unstable. Hence the users will not able to access any applications.
 
Product Version: ZTA

Component(s) : Agent

Severity: Medium

Workarounds or Recommendations: This is recommended to make all gateways running up all the time.
 
**User not able to access applications if the proxy is changed or modified.**
 
Issue Description: 
Proxy installed at customer site should not be changed or modified after configurations are made. In case this is changed,  Instasafe Certificate will be impacted hence, user will not able to access the applications.
 
Product Version: ZTA

Component(s) : Agent

Severity: Low

Workarounds or Recommendations: this is recommended that the Proxy should be changed or modified after the configurations were made. In case of any such needs, please reach out to Instasafe Support team.
 
**ZTAA Background Report Request slow or fail sometime**

Issue Description: 
If Admin tries to schedule a report in background mode from InstaSafe ZTA Console (Audit Section -> Export -> Schedule), its observed that in some cases the report iss either delayed or fails. 
 
Product Version: ZTA

Component(s) : Admin Console

Severity: Medium

Workarounds or Recommendations: We recommend admins to retry if the scheduled report fail to deliver.
 
**User DELETED from Azure AD portal ONLY, NOT getting removed from Azure group and remain active in the ZTAA console**
 
Issue Description: 
In some cases, it was observed that if a user is deleted from Azure AD Portal and not from the On-Premise AD, and after the Azure AD Sync the users are not getting removed from the Group and stay active in ZTAA Console instead of the users should be removed from the Azure Group and should be in Inactive State.
 
Product Version: ZTA

Component(s) : Console 

Severity : High

Workarounds or Recommendations: InstaSafe Product Team is currently doing the investigation to find out the root cause. 
 
**Applications not accessed if the application not added to IDP in Console**
 
Issue Description: 
If the applications are not added to the IDP, in some scenarios the browser gets stuck and does not show any error messages. This impact users in accessing the applications.
 
Product Version: ZTA

Component(s) : Console 

Severity : Low

Workarounds or Recommendations:  We recommend adding the applications to IDP.
 
**Admins Logout from the console if trying to delete the report generated in "On Demand" Section.**

Issue Description: 
In some case this was noticed that if the Admin tries to delete the report from "On Demand" section, the Admin automatically gets logged out from the console. While clicking on Delete Option shown in Report generated page of "On Demand", User Automatically logout from the environment.
 
Component(s): Console

Severity: Low

Workarounds or Recommendations: InstaSafe Product Team is currently doing the investigation to find out the root cause. 

**ZTAA Agent needs to be restarted for New network applications added to Access policy to show Online in the Agent**

Issue Description: On clicking the Refresh button in the agent, the newly added network application to the access policy does NOT show online even though the application is accessible via the gateway. 

Product Version: ZTA

Component(s): Agent

Severity: Medium

Workaround or Recommendations: Only after closing and re-opening the agent OR on doing a Stop and Start of the network toggle available in the agent, the newly added applications are shown online in the agent.

**mac OS users on ZTNA 4.13.0.0 will need to do a system restart to upgrade to the latest version**

Issue Description: MAC users who are on the ZTNA version 4.13.0.0 will not get upgraded to the latest ZTNA version automatically.

Component(s): Agent

Severity: Medium

Workaround or Recommendations: A system restart needs to be done for the latest ZTNA version to be upgraded.

**Network application access in Windows 8.1 Pro 32 bit & 64 bit**

Issue Description: Network applications are showing unstable and are not accessible when a user logs into the ZTAA agent from a Windows 8.1 Pro 32 bit or 64 bit machine.

Component(s): Agent

Severity: Low

Workaround or Recommendations: Network applications are accessible only after clicking on the Refresh button in the agent.


**Disclaimer:**

_InstaSafe Product Team given their best analysis to report the known issues. However, there will be some scenarios which might missed out in the section. InstaSafe Product Team had provided the workarounds or recommendations to their best knowledge, however InstaSafe doesn’t take the guarantee if the workarounds or recommendations will work all the time._ 

