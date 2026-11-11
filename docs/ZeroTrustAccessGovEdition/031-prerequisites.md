---
comments: true
---
# InstaSafe ZTNA Gateway

The InstaSafe ZTNA Gateway is responsible for securing and keeping private all applications and network resources in the data centre(s). It serves as the termination point for the mutual TLS tunnels, where traffic is decrypted and routed to the respective application servers.

VPN, TCP, RDP/SSH & Agentless applications can be configured in a single InstaSafe ZTNA Gateway.

An InstaSafe ZTNA Gateway must be provisioned on a physical server or VM/instance at each of the respective data centres as per the below mentioned configuration. For the purpose of redundancy, it is recommended to provision a backup InstaSafe Gateway as well, with the same configuration.


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

Every InstaSafe ZTNA Gateway must have local network access to all the application servers in that data centre you wish to provide secure access to.

### Network Firewall Rules

| Source | Application Type  | Port | Direction |
|-----------------------|--------------------------|--------------------------|--------------------------|
| any | Network  | UDP 8443 | Inbound |
| any | RDP & SSH  | TCP 8080 | Inbound |
| any | Web applications (Agentless)  | TCP 443 | Inbound |
| any | Web applications (via Agent)  | TCP 8082 | Inbound |
| InstaSafe Gateways | any (private/public internet)  | any | Outbound |

**Note:** If the above mentioned ports are already being utilized in your network for different purpose then there is customization available for the gateways to listen on different port numbers.


InstaSafe ZTNA Gateways has a host firewall which filters the network traffic coming in, so even if source is “any” in network firewall, InstaSafe ZTNA Gateway is equipped to handle unknown incoming traffic. 

### Proxy Configuration

In case of a proxy present, it must be ensured that the connection is allowed directly from the firewall.

## Supported hypervisors

The note above names examples of host platforms for the gateway. It is not the list of
supported hypervisors, which is:

| Hypervisor | |
|---|---|
| **VMware ESXi** | |
| **Microsoft Hyper-V** | |
| **KVM** | including **Red Hat KVM** and **Proxmox VE**, both open source |

The solution components are supplied as a unified OVA template and deployed as virtual
machines, one per component. KVM-based hypervisors are supported, so a deployment is not tied
to a commercial virtualisation platform. The hypervisor hosts the virtual machines and plays
no part in authentication, policy evaluation or tunnel termination, so the platform behaves
identically on any supported hypervisor. See
[Supported Hypervisors and the Deployment Package](hypervisor-support.md).
