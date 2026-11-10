---
comments: true
---
# InstaSafe ZTAA Gateway

The InstaSafe ZTAA Gateway is responsible for securing and keeping private all applications and network resources in the data centre(s). It serves as the termination point for the mutual TLS tunnels, where traffic is decrypted and routed to the respective application servers.

VPN, TCP, RDP/SSH & Agentless applications can be configured in a single InstaSafe ZTAA Gateway.

An InstaSafe ZTAA Gateway must be provisioned on a physical server or VM/instance at each of the respective data centres as per the below mentioned configuration. For the purpose of redundancy, it is recommended to provision a backup InstaSafe Gateway as well, with the same configuration.


### VM Sizing

<style>
table, th, td {
  border: 0.1px black ;
}
</style>

| Virtual Machine Parameter | Requirement  |
|-----------------------|--------------------------|
| **Operating System** | Ubuntu 22.04.2 LTS (server edition)  |
| **OS Type**| 64-bit |
| **RAM** | Minimum 8 GB|
|**Hard Disk**| Minimum 50 GB of free space  |
| **CPU**| 4 Core CPU as minimun |


Note : Supports Other Platforms like Windows or Linux VM running on VMWare or Hyper-V.

## Network Requirements

Every InstaSafe ZTAA Gateway must have local network access to all the application servers in that data centre you wish to provide secure access to.

### Network Firewall Rules

| Source | Application Type  | Port | Direction |
|-----------------------|--------------------------|--------------------------|--------------------------|
| any | Network  | UDP 8443 | Inbound |
| any | RDP & SSH  | TCP 8080 | Inbound |
| any | Web applications (Agentless)  | TCP 443 | Inbound |
| any | Web applications (via Agent)  | TCP 8082 | Inbound |
| InstaSafe Gateways | any (private/public internet)  | any | Outbound |

**Note:** If the above mentioned ports are already being utilized in your network for different purpose then there is customization available for the gateways to listen on different port numbers.


InstaSafe ZTAA Gateways has a host firewall which filters the network traffic coming in, so even if source is “any” in network firewall, InstaSafe ZTAA Gateway is equipped to handle unknown incoming traffic. 

### Proxy Configuration

In case of a proxy present, it must be ensured that the connection is allowed directly from the firewall.
