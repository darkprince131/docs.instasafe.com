---
comments: true
---
# Supported Browsers

Clientless access and the administration console both run in a standard browser. No plug-in
or extension is installed, and no browser is required beyond the ones an organisation
already runs.

## Minimum versions

| Browser | Supported from |
|---|---|
| **Google Chrome** | version 39 and above |
| **Chromium-based browsers**, including **Microsoft Edge** | version 39 and above |
| **Mozilla Firefox** | version 33 and above |
| **Apple Safari** | version 5.5 and above |

These are minimums, not targets. The platform is built to modern web standards with
backward compatibility, so current releases of each browser are supported; the versions
above are the floor, which matters where an organisation standardises on an older build.

Because Microsoft Edge is Chromium-based, it is covered by the Chromium entry rather than
listed separately.

## What this covers

The same set applies to the clientless application portal, where users open their
applications, and to the administration console. Clientless access to RDP, SSH and file
shares is rendered in the browser too, so it inherits the same support - see
[Clientless Access to Web Applications](clientless-web-access.md) and
[Agentless Access](agentless.md).

## Restricting which browsers may be used

Support is one question; what an organisation permits is another. **Disallowed Browsers for
Users** on the User Settings page takes a comma-separated list of browser names, so an
organisation that standardises on two browsers can refuse the rest rather than relying on
instruction.

The browser a session actually used is recorded, so the policy is auditable rather than
assumed - the end-user dashboard shows the browser for the current and previous session, and
**Browser Switch** is available as a risk type, letting a change of browser trigger an alert
or a block. See
[Account Lockout, Idle Timeout and Forced Logout](session-controls.md).

Chrome additionally supports endpoint controls - blocking downloads, developer tools and
printing - see [Chrome Controls](chromecontrols.md).
