---
comments: true
---
The Instasafe Agent is the primary way a user interacts with a Zero Trust Network. The Agent is available on all desktop operating systems as an electron application. The agent is designed to access both the InstaSafe ZTNA infrastructure and ZTNA infrastructure at the same time. The agent provides a simple one click interface to the consumer to open applications configured in their company’s Zero Trust infrastructure.
In the context of InstaSafe ZTNA, when the user clicks the application, the agent automates the entire process of communication between gateways and controllers and opens the respective application within the agent. To accommodate several application protocols, The agent has an inbuilt web browser, an open-source RDP client and a SSH client to access applications through the agent’s interface.
In the context of ZTNA, when the user starts the application, the agent establishes a wireguard tunnel between the consumer’s machine and the gateway configured. Once connected, the consumer will be able to access the applications on the configured network according to their privileges. Users will be able to access enterprise applications of their corporate network through the applications installed on their base machine.

The agent is available for download after logging into the InstaSafe ZTNA web application `Tenantname.app.instasafe.io`, and navigating to the downloads section.
The agent is configured to auto-update to the latest version available.
In addition to the desktop agents, Instasafe also offers mobile agents for users to access their Zero Trust Infrastructure.
Named, InstaSafe mZTNA it is available on both the Google Play Store and the iOS App Store.

## Supported Environment

The the console is supported across latest versions of all major browser like Google Chrome, Mozilla Firefox.

| Operating System Name | Operating System Version |
|-----------------------|--------------------------|
| **Android** | 7.0 Nougat and above |
| **iOS**| IOS 11 and above|
| **Windows** | Windows 8, 10 and 11 |
|**Mac**| Macos 10.14-Mojave and above |
| **Linux**| Ubuntu 18.04 and above|
