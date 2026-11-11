---
comments: true
---
#### Failed to register device/ error:- connect timed out 13.234.197.59:443:-

Possible cause
1.	If user is trying to connect to InstaSafe ZTNA with multiple device simultaneously.
2.	Device-binding would be enabled by the admin, but user might be login in with a different device).
3.	User would be enabled with the ipv6-address.
4.	Windows defender firewall must be blocking it.
5.	Due to poor/up-down in internet connectivity & user reattempting to login & open InstaSafe ZTNA.

**Resolution**
Go to control panel.
1.	Click on network & sharing center.
2.	Click on adapter settings and right click on network we are using.
3.	Enter the admin credentials if it asks for.
4.	Click on properties and Check if ipv6 address is enabled, 
5.	Disable it and click on ok.
6.	Restart the system once and then try opening InstaSafe ZTNA client.
If the issue still persists then, windows defender firewall must be blocking the InstaSafe ZTNA.
**Resolution**
1.	Go to control panel.
2.	Open the windows defender firewall.
3.	Go to advanced settings & enter the admin credentials.
4.	Click on the “inbound rules” & check if zero trust is allowed in these rule-set.
5.	If not then click on “add new rule”.
6.	Click on programs & browse for the ZTNA file.
7.	Enter the ZTNA folder path by browsing for files or entering it Manually.
8.	 Allow the above folder path by clicking on ok.
9.	Refresh/restart the InstaSafe ZTNA client.


