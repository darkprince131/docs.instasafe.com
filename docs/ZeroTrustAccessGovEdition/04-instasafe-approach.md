---
comments: true
---
# InstaSafe Zero Trust Access(ZTA)

ZTA follows the Client Initiated ZTNA Architecture. InstaSafe offers two different Zero Trust based remote access solutions merged in to one solution called Zero Trust Access. Zero Trust based Network access enable the access at IP/Network level, where as the Zero Trust Application Access enables the application access. Both of the implementation can co-exist in an installation in order to support L3/L4 network layer access (SSH/RDP/File folder access ...) and specific application access.

Both of the methods adopts the seperate plane of data traffic for authentication and the application/server data. The user authentication and the device authictication will be carried out in terms of credentials, MFA and the security posture checks. Only the Aunthorised devices and users can send the traffic to the data plane and access the organisation's assets such as servers and Applications.

The architecture also follows the SPA and drop-all-firewall principles in order to hide the IT infrastructure completely from the internet. Any network request from an unknown client will be dropped off (not deny) by the firewall rules. Hence the presence of the ZT infrastructure and the organisation's assets are hidden from the internet. Not even the tools such as nmap can identify them.

## InstaSafe Zero Trust Application Access (InstaSafe ZTNA)

Instasafe’s InstaSafe ZTNA is based on the Client-Gateway model in Software Defined Perimeter specification as proposed by the  Cloud Security Alliance (CSA) . The design follows the rules put forward by NIST as well. It is a client-initiated ZTNA solution which creates a secure tunnel between the client and the server with additional  features like Multi-Factor Authentication, SSO and integration with SAML for third party applications. 

Each access to the application will be seperately taken out via an independent tunnel ensuring that the user access is contained and controlled with in the application access, completely eleminating the insider threats.

Why InstaSafe ZTNA : https://instasafe.com/zero-trust-application-access/



## InstaSafe Zero Trust Network Access (ZTNA)

InstaSafe’s ZTNA is also a client-initiated Zero Trust Network Access solution which instead of connecting a client to an application connects the client to a network via a fast and secure tunnel. It also includes features like Multi-Factor Authentication and device profiling and authentication mechanism similar to InstaSafe ZTNA.

The implementation can limit the user access to a server or a perticular port. Each access to the asset will be through a seperate tunnel, where the user user access is limited to what is shared.

Why ZTNA : https://instasafe.com/zero-trust-network-access/
