---
comments: true
---

### Network Filter Endpoint Control

The Network Filter Endpoint Control feature allows Admins to block specific Domains or IP addresses on end-user devices. This policy-based control helps enforce secure browsing and access restrictions at the device level.

This feature supports devices running on the following operating systems:

- Windows

- Linux
- Darwin (macOS)


Admins can choose when to enforce the network filtering:

- During ZTNA agent VPN connectivity, or

- Immediately on device boot, regardless of VPN connection.


### Steps to Configure Network Filter Endpoint Control

- Create a Dataset of type FQDN

- Define the list of Domains and/or IP addresses that need to be blocked.
	- Example entries:
		- facebook.com
		- 192.168.1.100

### Create a Network Filter Endpoint Control Policy

- Link the previously created FQDN dataset.

- Select the target Operating Systems (Windows, Linux, Darwin) where the filter should be applied.

- Assign the Policy to Users or User Groups

- Choose the Users or User Groups to whom the policy will be enforced.

Once configured, the selected domains/IPs will be blocked on the target devices as per the enforcement mode chosen (on VPN connection or on device boot).



