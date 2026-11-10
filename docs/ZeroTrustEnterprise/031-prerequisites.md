---
comments: true
---
# InstaSafe ZTAA Gateway

The InstaSafe ZTAA Gateway is responsible for securing and keeping private all applications and network resources in the data centre(s). It serves as the termination point for the mutual TLS tunnels, where traffic is decrypted and routed to the respective application servers.

An InstaSafe ZTAA Gateway must be provisioned on a physical server or VM/instance at each of the respective data centres as per the below mentioned configuration. For the purpose of redundancy, it is recommended to provision a backup InstaSafe Gateway as well, with the same configuration.

### VM Sizing

| Virtual Machine Parameter | Requirement  |
|-----------------------|--------------------------|
| **Operating System** | Ubuntu 22.04.2 LTS (server edition)  |
| **OS Type**| 64-bit |
| **RAM** | Minimum 8 GB|
|**Hard Disk**| Minimum 50 GB of free space  |
| **CPU**| 4 Core CPU as minimun |


## Network Requirements

Every InstaSafe ZTAA Gateway must have local network access to all the application servers in that data centre you wish to provide secure access to.

### Network Firewall Rules

| Source | Destination  | Port | Direction |
|-----------------------|--------------------------|--------------------------|--------------------------|
| any | InstaSafe Gateways  | TCP 443 and UDP 443 | Inbound |
| any | InstaSafe Gateways  | TCP 8080 | Inbound |
| InstaSafe Gateways | any (private/public internet)  | any | Outbound |


InstaSafe ZTAA Gateways has a host firewall which filters the network traffic coming in, so even if source is “any” in network firewall, InstaSafe ZTAA Gateway is equipped to handle unknown incoming traffic. 

### Proxy Configuration

In case of a proxy present, it must be ensured that the connection is allowed directly from the firewall.
