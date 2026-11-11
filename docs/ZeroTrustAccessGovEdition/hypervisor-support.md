---
comments: true
---
# Supported Hypervisors and the Deployment Package

The platform's components - controller, console, database and gateway - are supplied as a
**unified OVA template** and deployed as virtual machines on the organisation's own
virtualisation platform.

## Supported hypervisors

The OVA template for the solution components can be deployed on:

| Hypervisor | |
|---|---|
| **VMware ESXi** | |
| **Microsoft Hyper-V** | |
| **KVM** | Including **Red Hat KVM** and **Proxmox VE**, both open source |

KVM-based hypervisors are supported, so a deployment is not tied to a commercial
virtualisation platform.

The gateway prerequisites page carries a note reading "Supports Other Platforms like
Windows or Linux VM running on VMWare or Hyper-V". That note names examples of host
platforms for the gateway; it is not the full list of supported hypervisors, which is the
table above. See [Prerequisites](031-prerequisites.md).

## What is deployed

Each component runs on its own virtual machine. The gateway, as an example, is specified
as:

| Parameter | Requirement |
|---|---|
| **Operating System** | Ubuntu 22.04.2 LTS, server edition |
| **OS Type** | 64-bit |
| **RAM** | 8 GB minimum |
| **Hard Disk** | 50 GB free minimum |
| **CPU** | 4 cores minimum |

A backup gateway of the same specification is recommended for redundancy. The full
component prerequisites, network requirements and firewall rules are in
[Prerequisites](031-prerequisites.md), and the gateway's own configuration in
[Create Gateways](006-creatinggateways.md).

## Where the hypervisor matters, and where it does not

The hypervisor hosts the virtual machines. It is not part of the data path and has no role
in authentication, policy evaluation or tunnel termination, so the platform behaves
identically whichever of the supported hypervisors it is deployed on.

What the hypervisor does determine is the import mechanism and the virtual hardware
presented to each VM - which is why the supported list is stated explicitly rather than
left to inference.
