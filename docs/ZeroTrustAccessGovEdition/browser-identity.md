---
comments: true
---
# Identifying the Browser and the Device

The platform identifies what a user is connecting from, not only who they are. Two
mechanisms do this, and they apply to different access modes.

## Device posture attributes

Device posture is evaluated against attributes collected from the endpoint. The set
includes, among others:

| | |
|---|---|
| **Browser ID** | Identifies the browser the session is using |
| **UA Suffix** | The user-agent suffix |
| OS Family, OS Build Version, OS Major and Minor Version | The operating system |
| System Serial Number, Disk Serial Number, Motherboard ID, Mac Address | Hardware identity |
| Certificate Thumbprints | Certificates present on the device |
| System Domain Name | Domain membership |
| AntiVirus Installed / Enabled / Updated Name, Windows Hotfixes | Security state |
| IP Address, Geolocation, Country Code | Where the device is |
| Application, Application Access Time | What is being reached, and when |

A posture profile is built as a dataset and attached to an access policy, so the check is
applied to the users and applications that policy covers rather than globally. See
[Based on Device Posture](deviceposture.md).

In the console, device checks are configured as individual check types - antivirus and its
status and last update, antispyware, firewall and its status, BitLocker, domain membership,
hotfixes, service pack, OS and OS version, MDM enrolment, a named process running or not
running, a file present or absent, a registry key, and browser identity among them.

## Which mode each applies to

Posture enforcement as described on the posture page gates **agent-based** access: a device
that fails a compliance rule is prevented from connecting through the agent.

**Clientless access performs fewer posture validations than agent-based access** - stated
plainly in [Architecture](002-architecture.md) - because a browser cannot inspect the host
the way an installed agent can. What the platform does identify for a browser session is
recorded regardless:

- the **browser** and the **platform** used for the session, shown to the user on their own
  dashboard for both the current and previous session, and held in the session record
- the **public IP** and **country** the session came from - see
  [Restricting Access by Public IP](wan-ip-restriction.md)

## Acting on a change

Identification is only useful if something happens when it changes. **Browser Switch** and
**Platform Switch** are risk types: if the browser or operating system differs from what was
seen before, the risk profile's action runs - an administrator alert, denial, suspension, or
disconnection. **Device Bind Failure** and **Device Check Failure** are risk types in the
same way.

So a browser identity that changes unexpectedly is not merely logged; it can refuse the
session. See
[Account Lockout, Idle Timeout and Forced Logout](session-controls.md) for the risk types
and their actions.

The User Settings page also carries a **Device Compliance for Web Access** setting, which
brings device compliance to bear on browser-based access.
