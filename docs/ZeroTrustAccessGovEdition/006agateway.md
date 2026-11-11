---
comments: true
---
InstaSafe ZTNA Gateways are the components which enforce the policies set by the controllers. They verify the client's entitlements before granting them access to the resources.An InstaSafe Gateway needs to be provisioned at every datacenter i.e in the same network as the enterprise applications such as the application servers are accessible from the gateway.It is a lightweight software module that can be installed on a physical server/VM (which runs in the data center) or an instance ( in the cloud-hosted data center). 

InstaSafe ZTNA provides different types of gateways designed for specific functionalities. This is to ensure that the organisation can provision one specific to their needs with minimun access requirements.

Different types of gateway present in InstaSafe ZTNA along with their utility is described in the table below. 

| Type of Gateway | Description | Concurrent Connections Support per gateway*|
|-----------------------|--------------------------| --------------------------|
| **TCP Gateway** | Should be used when the objective is only to access  web applications or syncing of users from active directory with retricted access to clipboard and screensharing. | 1500 Users |
| **RDP Gateway**| Should be  used when the objective is to access an external  machine (via RDP or ssh) remotely from InstaSafe ZTNA client with retricted access to clipboard and screensharing. | NA |
| **Network Gateway** | Should be used when access to private applications hosted in private server/data center or cloud. [VPN profile](https://docs.instasafe.io/Zero%20Trust%20Application%20Access/010-VPNProfileSetup/) needs to be set up prior to installing a VPN gateway. | 1000 Users |
|**Agentess Gateway**| Should be used when the admin wants to allow user access to application directly from any browser without the need to install an  end user agent/client.| 1500 Users |
|**Unified Gateway**| A single gateway which will secure the access of VPN, TCP, RDP/SSH & Agentless applications.| 1500 Users |

*The data for **Concurrent Connection support** has been obtained by simulations carried out internally. The actual number may vary depending upon use case, bandwith consumed by the user and RAM of the VM on which the gateway is running 

In case the total number of Users exceed the mentioned amount, provisioning of additional gateways will be required to accomadate users exceeding capacity. For Example if 2000 users are to simultaneously access entriprise resources via InstaSafe ZTNA network gateway, 2 network gateway needs to be provisioned with 1000 users connecting via each gateway. *   


### Prerequisites

The  company admin must ensure that the following prerequesites are met prior to installation of InstaSafe ZTNA gateways. It is recommended to set up a backup InstaSafe Gateway,with the same configuration for the purpose of redundancy.



| Virtual Machine Parameter | Requirement  |
|-----------------------|--------------------------|
| **Operating System** |Ubuntu 22.04.2 LTS (server edition)  |
| **OS Type**|64-bit |
| **RAM** | Minimum 8 GB|
|**Hard Disk**|Minimum 30GB of free space  |
| **CPU**|4 Core CPU as minimun|

#### Network Parameter 

The following  ports should be opened for InstaSafe ZTNA gateways to function. 

**For TCP Gateways**

|Source | Destination  | Port | Direction |
|----------------------- |-------------------------- |---------------------- | -------------------------- |
| ANY | TCP Gateway  | TCP 443| Inbound |
| Instasafe Gateways | ANY (Private Network TCP 80, TCP 443-public internet) | ANY | Outbound |


**For RDP Gateways**

|Source | Destination  | Port | Direction |
|----------------------- |-------------------------- |---------------------- | -------------------------- |
| ANY | RDP Gateway  | TCP 8080 | Inbound |
| Instasafe Gateways | ANY (Private Network TCP 80, TCP 443-public internet) | ANY | Outbound |

**For Network Gateways**

|Source | Destination  | Port | Direction |
|----------------------- |-------------------------- |---------------------- | -------------------------- |
| ANY | Network Gateway | UDP 443 | Inbound |
| Instasafe Gateways | ANY (Private Network TCP 80, TCP 443-public internet) | ANY | Outbound |

**For Unified Gateway**

| Source | Application Type  | Port | Direction |
|-----------------------|--------------------------|--------------------------|--------------------------|
| any | Network  | UDP 8443 | Inbound |
| any | RDP & SSH  | TCP 8080 | Inbound |
| any | Web applications (Agentless)  | TCP 443 | Inbound |
| any | Web applications (via Agent)  | TCP 8082 | Inbound |
| InstaSafe Gateways | any (private/public internet)  | any | Outbound |

Use case of gateways and applications list that are compatible with our gateways:

|Gateways | Supported Application  |
|----------------------- |-------------------------- |
| TCP | Web applications |
| Network | Web applications, SSH, RDP, File share, Network share| 
| RDP/SSH | RDP, SSH, File share | 
| Agentless | Web applications | 
| Unified | Web applications, SSH, RDP, File share, Network share| 


**Unified Gateway**

To address the operational cost and maintenance overhead associated with InstaSafe ZTNA requiring separate instances for the set up of VPN, TCP, RDP/SSH & Agentless gateways respectively, optimization has been done with all the gateways bundled together as a single entity.
Named as Unified Gateway, a single gateway now will cater to secure the access of VPN, TCP, RDP/SSH & Agentless applications.

*Benefits:*
- Reduction of hardware cost without the need of separate instances for the VPN, TCP, RDP/SSH & Agentless gateways respectively.

- Perform feature and performance upgrades in a single gateway instead of having to perform on the respective VPN, TCP, RDP/SSH & Agentless gateways.

- Configure applications in a single gateway instead of having them to be performed in the individual gateways.

- The Unified gateway supports both IPv4 & IPv6 network and web applications in dual stack mode.


**Please Note**
```
1. InstaSafe ZTNA Gateways has inbuilt  firewall featurs and hence is equipped to 
handle incoming traffic from unknwon sources, even when the firewall allows traffic 
from any source.

2. If any proxy configuration is present , it must be ensured that direct connection 
from the firewall is allowed.
```

## Scaling, and how user connections are distributed

Distribution of user connections is a function of the platform, not a setting on the
endpoint. An agent holds no controller address: after the user has authenticated and passed
the device and contextual checks, the platform supplies the controller's address and port in
the agent's configuration, and the agent then establishes its tunnel to that controller.

Capacity is added horizontally - controllers deployed active-active in proportion to
concurrent users, and gateways in proportion to simultaneous connections, each with a
declared backup gateway. See
[Scaling and Connection Distribution](scaling-and-distribution.md).
