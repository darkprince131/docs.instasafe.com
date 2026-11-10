---
comments: true
---
# System Architecture Diagram

![](../static/ISA/ISA_Architecture.jpg)

# Key components

The InstaSafe Secure Access (ISA) Architecture consists of 3 components

1. Controller
1. Gateway
1. User Agent

**Controller**

InstaSafe Controller is one of the key modules in the InstaSafe Cloud infrastructure that enforces access control for network connectivity. It is also the central point to which InstaSafe User Agent and Gateway Agent establish independent DTLS tunnels. It enforces policies and accepts/denies application access based on the configured policies. 

The Controllers are provisioned in multiple cloud providers in various geo locations. The Controllers are strategically placed as close as possible to customer premises to ensure minimum latency Each tenant requires the provisioning of one or more Controllers. 

The Controller IP and the port number is pushed to the ISA Agent in the configuration file, after authentication and compliant checks are successfully completed.  In the context of ISA User Agents, the Controller's role commences after the User Agent successfully completes authentication, Geo Location check, Device Binding check, Device Check, and secondary authentication, such as 2FA/MFA. 

The Controller listens on the IP address and the TCP or UDP port for tunnel establishment requests. The ISA Agents initiates the connection to the Controller and the Controller identifies the organization based on the signature in the first UDP packet it receives and proceeds to establish the tunnel. 

The Controller is responsible for tasks such as: 
- Allocate IP addresses and routes to the ISA User Agent.
- Route data between the Agent and the private network
- Enforce security policies.

**Gateway**

InstaSafe Secure Access (ISA) Gateway Agent is a software that acts as the entry and exit point for user access. It is responsible for encrypting and decrypting data sent over the secure connection, as well as routing data between the ISA User Agent and the private network. The ISA Gateway Agent establishes a DTLS tunnel with the ISA Controller to route traffic between the User Agents and the private network. 

Gateways are deployed at the edge of a private network, and are used to connect remote clients or networks to the private network. It can also be used to connect two separate private networks together, such as in site-to-site configuration.

The Gateway Agent script or installation file contains the following relevant information:

- Client certificate 
- Client private key
- CA certificate to verify the server certificate 
- Static key for HMAC operation
- Domain name and port number of the Controller 

The ISA Gateway Agent connection establishment process:

- The Agent makes an outbound connection to the domain name of the Controller on the port number in the configuration file. 
- Agent establishes a DTLS tunnel with the Controller after mutual authentication using the certificates and static key in the configuration file.  
- Data traffic from the User Agents is routed through the tunnel via the Controller to the Gateway, decrypted, and forwarded to the corporate resource. 

**User Agent**

The ISA User Agent is a software that is installed on users’ devices, such as laptops or smartphones. The Agent connects to the ISA Cloud Delivery Platform for the authentication and authorisation process. 

Once successfully authenticated, the Agent establishes a DTLS tunnel with the ISA Controller to access the remote network. The Agent runs as a service in the user computer. The agent can be configured to auto-connect whenever the computer is turned on.
