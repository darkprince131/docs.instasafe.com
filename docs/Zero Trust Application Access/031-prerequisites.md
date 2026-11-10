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
| **Operating System** | Ubuntu 24.04.3 LTS |
| **OS Type**| 64-bit |
| **RAM** | Minimum 8 GB|
|**Hard Disk**| Minimum 100 GB of free space (in root partition)  |
| **CPU**| 1 x Quad Core processor (x64 based) |

* The ZTA Gateway in each data center must have network access to the internal applications to which you wish to provide secure remote access
* Static Public IPs need to be assigned to the VM, with a 1:1 NAT, and inbound access allowed from the internet over specific ports as per the Nework Requirements (below section).
* Sudo user SSH access to the VM is required at the time of installation
* The ZTA Gateways must be able to resolve the FQDNs of Internal Applications to their respective Private IP addresses
* Full internet access must be provided during installation to download relevant packages and repositories. It is recommended to provide direct internet access instead of via proxy





## Network Requirements

Every InstaSafe ZTAA Gateway must have local network access to all the application servers in that data centre you wish to provide secure access to.

### Network Firewall Rules

| Source            | Destination                                      | Protocol/Port              | Direction | Purpose / Comments                                              | Necessary / Optional |
|-------------------|--------------------------------------------------|----------------------------|-----------|------------------------------------------------------------------|----------------------|
| ANY               | ZTA Gateway(s)*                                  | TCP 443                    | Inbound   | Required so that users can connect to ZTA Gateways to access Apps from the ZTNA Agent and ZTA Portal (browser based clientless access)                     | Necessary for this use case. Else, Optional |
| ANY               | ZTA Gateway(s)*                                  | UDP 8443                   | Inbound   | Required so that users can connect to Gateways for VPN access via ZTNA Client               | Necessary for this use case. Else, Optional |
| ZTA Gateway(s)*   | 3.7.192.120, 13.233.31.177, 13.234.197.59, 15.207.0.228, 15.207.2.32                        | TCP 443, 4317, 4318, 8080 | Outbound | Required for ZTA Gateways to contact the platform                    | Necessary |
| ZTA Gateway(s)**  | Applications that needs to be accessed                              | Based on requirement       | Outbound | Target applications would be accessible to end-users only if they are reachable from the ZTA Gateway Server itself                           | Necessary |
| ZTA Gateway(s)*   | archive.ubuntu.com, security.ubuntu.com, extras.ubuntu.com, keyserver.ubuntu.com, github.com, \*.instasafe.com, \*.app.instasafe.com, cr.instasafe.io, storage.googleapis.com, checkip.safehats.com | TCP 80, 443       | Outbound | Installation and update of the ZTA Gateway                 | Necessary during installation/update. Else, Optional |
| 54.169.225.217 | ZTA Gateway(s)*              | TCP 22                     | Inbound   | InstaSafe Tech team to Troubleshoot critical issues and provide assistance with updates                    | Optional |

\* Public IP Address(es) allocated by the customer					

** Private IP Address(es) allocated by the customer					

**Note:** If the above mentioned ports are already being utilized in your network for different purpose then there is customization available for the gateways to listen on different port numbers.


InstaSafe ZTAA Gateways has a host firewall which filters the network traffic coming in, so even if source is “any” in network firewall, InstaSafe ZTAA Gateway is equipped to handle unknown incoming traffic. 

### Proxy Configuration

In case of a proxy present, it must be ensured that the connection is allowed directly from the firewall.
