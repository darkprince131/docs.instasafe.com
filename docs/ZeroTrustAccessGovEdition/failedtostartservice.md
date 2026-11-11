---
comments: true
---
#### Failed to start service for InstaSafe ZTNA version

**Root cause**

 Helper component is responsible to start the InstaSafe ZTNA client by default after installing and opening it. When the process fails, we get the error “failed to start service”.

**Resolution**

1.	Click on windows & run services. MSc as administrator.
2.	Click on Instasafe ZTNA helper & restart it.
3.	 Refresh the the agent.
