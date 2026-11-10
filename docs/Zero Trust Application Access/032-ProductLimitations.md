---
comments: true
---
_Last Update Date: 19th Nov 2024_

**Overview**

This section is used to report InstaSafe ZTAA platform's known issues. 

**How often the list is updated**

The InstaSafe ZTAA product known issue list is updated whenever any new issue is identified or an existing issue is fixed. However, we also review and update the list on a monthly basis.
 
**Contact**

For any question regarding the below reported issues or the recommendation for the work around, please reach out to InstaSafe Support Team [support@instasafe.com](support@instasafe.com)

## Product Name: InstaSafe Authenticator app (iOS) ##

**Issue Description:** Push notifications are not received on the InstaSafe Authenticator app on iOS devices. Push notifications stopped working in the Authenticator app on iOS devices due to recent changes in Apple's policy. We will have to upgrade the Authenticator app in iOS to address the issue and we are working on the same. Users can continue to make use of the Time based OTP from the Authenticator app in iOS devices to login to the InstaSafe platform.

Push notifications continue to work on the InstaSafe Authenticator app on Android devices. 

## Product Name: InstaSafe Zero Trust Access (ZTA) ##

**The end users will not be able to access the applications in few of the below mentioned scenarios. The application will show as unstable if any of the below scenarios are applicable.**
 
**Issue Description:** User access gets disconnected and not able to access applications.
 
•	Dynamic IP at User End Point: if the IP address keeps changing in the user device, users might face instability in application access.

•	Misconfiguration in firewall at gateway: if the firewall at customer gateway is misconfigured.

•	Change VMs: if an existing Gateway is migrated to a new VM after the complete setup is done. 

Component(s) : ZTA Agent, Gateway

Severity: Medium
 
**Workarounds or Recommendations:** Users are recommended to disconnect from VPN and reconnect the same. This will allow users to establish the VPN connection again and they will be able to access the applications.
In case of firewall misconfiguration, Admin are requested to make the necessary changes to allow the traffic.
If a customer wants to change the VM where the gateway is installed, we recommend reaching out to the InstaSafe Support team for assistance.
 


**Application shows unstable if one gateways is down in case of multiple gateways configured.**
 
**Issue Description: **
If customer have multiple gateways deployed for accessing multiple applications through each of the gateways, then in some situation where one of the gateways goes down for some reason, the applications that are accessed through the other gateways will also show unstable. Hence the users will not be able to access any applications.
 
Product Version: ZTA

Component(s) : Agent

Severity: Medium

**Workarounds or Recommendations:** It is recommended to have all gateways running up and running all the time.
 
**User not able to access applications if the proxy is changed or modified.**
 
**Issue Description:** 
Proxy installed at customer sites should not be changed or modified after configurations are made. In case this is changed,  the InstaSafe certificate will be impacted hence, the user will not be able to access the applications.
 
Product Version: ZTA

Component(s) : Agent

Severity: Low

**Workarounds or Recommendations:** It is recommended that the Proxy should not be changed or modified after the configurations were made. In case of any such needs, please reach out to the Instasafe Support team.
 
**ZTAA Scheduled Audit Report get delayed in generating**

**Issue Description:** 
If Admin tries to schedule a report in background mode from InstaSafe ZTA Console (Audit Section -> Export -> Schedule), it is observed that in some cases the report is either delayed or fails. 
 
Product Version: ZTA

Component(s) : Admin Console

Severity: Medium

Workarounds or Recommendations: We recommend admins to retry if the scheduled report fails to deliver.
 
**User DELETED from Azure AD portal ONLY, NOT getting removed from Azure group and remain active in the ZTAA console**
 
Issue Description: 
In some cases, it was observed that if a user is deleted from Azure Portal and not from the On-Premise AD, after the Azure Sync the users are not getting removed from the Group and stay active in ZTAA Console instead of getting removed from the Azure Group and the user status updated as Disabled.
 
Product Version: ZTA

Component(s) : Console 

Severity : High

**Workarounds or Recommendations:** InstaSafe Product Team is currently doing the investigation to find out the root cause. 
 
**Applications not accessed if the application is not added to IDP in Console**
 
**Issue Description:** 
If the applications are not added to the IDP, in some scenarios the browser gets stuck and does not show any error messages. This impacts users in accessing the applications.
 
Product Version: ZTA

Component(s) : Console 

Severity : Low

**Workarounds or Recommendations:**  We recommend adding the applications to IDP.
 

**ZTAA Agent needs to be restarted for new network applications added to Access policy to show Online in the Agent**

**Issue Description:** On clicking the Refresh button in the agent, the newly added network application to the access policy does NOT show online even though the application is accessible via the gateway. 

Product Version: ZTA

Component(s): Agent

Severity: Medium

**Workaround or Recommendations:** Only after closing and re-opening the agent OR on doing a Stop and Start of the network toggle available in the agent, the newly added applications are shown online in the agent.


**Network application access in Windows 8.1 Pro 32 bit & 64 bit**

**Issue Description:** Network applications are showing unstable and are not accessible when a user logs into the ZTAA agent from a Windows 8.1 Pro 32 bit or 64 bit machine.

Component(s): Agent

Severity: Low

**Workaround or Recommendations:** Network applications are accessible only after clicking on the Refresh button in the agent.


**Disclaimer:**

_InstaSafe Product Team have given their best analysis to report the known issues. However, there will be some scenarios which might be missed out in the section. InstaSafe Product Team has provided the workarounds or recommendations to their best knowledge, however InstaSafe doesn’t make the guarantee if the workarounds or recommendations will work all the time._ 

