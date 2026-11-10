---
comments: true
---
#### ZTAA showing offline with network access failed.

![](../static/ztaa/appaccess1.png)

**Root Cause**

1.	ZTAA might show offline due to weak internet connection at end user machine.
2.	user might be enabled with the ipv6 address.

**Resolution**

1.	Go to Network and Sharing centre within the Control Panel.

![](../static/ztaa/nwsc.png)

2.	Go to adapter settings.

![](../static/ztaa/adapter.png)

3.	Right-click on the network that is being used, it will ask for admin privilege, we need to enter that.

4.	Go to properties & right-click on it.

![](../static/ztaa/nwsc.png)

5.	Disable IPV 6 if enabled.

![](../static/ztaa/ipv6.png)

6.	Refresh/restart the ZTAA client.


#### Applications showing unstable

![](../static/ztaa/appunstable.png)

**Root Cause**  
1.	User system might be facing fluctuations in ip-address.

2.	Due to a poor internet connectivity.

3.	Windows-defender firewall must be blocking agent from accessing network.

4.	This could be related to gateway in case multiple users are facing the issue simultaneously.

**Resolution**
1.	In most cases refreshing/restarting the agent should solve the issue.

2.	In case issue is not resolved by restarting the agent, please try changing your internet connection.

3.	The may connect with the ISP to provide a static IP

4.	In case of gateway issue restarting of gateway should solve the issue.

