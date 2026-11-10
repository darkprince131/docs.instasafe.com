---
comments: true
---
# How to disable NAT on the ISA Gateway (Linux)

When the ISA Gateway is deployed, the ISA Gateway Agent performs network address translation (NAT) to translate the source IP address of incoming traffic from the outside to the IP address of its physical interface, such as eth0, enp0s3, before forwarding the packet to the destination. The agent uses IP Masquerading to perform NAT and is implemented using the following command in the Gateway Agent script:

**_iptables -t nat -A POSTROUTING -o $intf -j MASQUERADE_**

The command is executed by running the script during installation of the agent and when the Gateway is restarted. This command will translate the source IP address of traffic coming from the outside, invariably from the ISA Controller, to the IP address of the physical adapter and then is forwarded to the destination, which is invariably a corporate resource.

However, there are instances when the source IP address must remain unchanged, for example, for VoIP traffic. In such cases, NAT should be disabled. To disable NAT, enter the following command:

**_iptables -t nat -F_**

This command will forward traffic to its destination without changing the source IP address. Appropriate routes must be configured for the return traffic.