---
comments: true
---
# Protecting the Sign-In Page

Automated attacks on the sign-in page - credential stuffing, password spraying, brute force
- are answered by three controls working together. None of them asks a legitimate user to
do anything.

## Bot detection on the sign-in page

The sign-in page carries a bot check that runs in the background and scores the request
rather than presenting a puzzle. A user signing in normally sees nothing and is not asked to
identify traffic lights or transcribe distorted text; automated submissions are scored and
refused.

This is the modern form of CAPTCHA, and it is deliberately not a challenge: challenge-based
CAPTCHA is both solvable by current automation and an accessibility burden on the people it
does not stop.

## Lockout after repeated failures

Repeated failed attempts block the account and the source address. The block is listed with
the time it was applied and the time it lifts, and an administrator can release it early.
The number of attempts permitted and the length of the block are set per tenant.

See [Account Lockout, Idle Timeout and Forced Logout](session-controls.md).

## A policy response to failed attempts

A risk profile turns repeated failures into an action chosen by the administrator rather
than a fixed behaviour. **Login Failure** and **MFA Failure** are both risk types, and the
action can be **Deny Access**, **Suspend User**, **Disconnect User** or **Email Admin**.

Applied to a user group, this makes the response to a credential attack specific to the
population under attack - an administrator alert for ordinary staff, suspension for
privileged accounts.

See [Email Alerts and Scheduled Reports](email-alerts.md).

## Phishing resistance

Bot detection stops automation; it does not stop a user being deceived into authenticating
on an attacker's page. That is answered by the authentication method itself - a WebAuthn
credential is bound to the origin it was registered for and will not be presented to any
other site.

See [Phishing-Resistant MFA](mfa-phishing-resistant.md) and
[WebAuthn MFA](webauthn-fido2-mfa.md).

## What is recorded

Failed attempts appear in the authentication record, and blocked accounts and addresses on
the Blocked Users page with the address they came from. See
[Audit Logs](017-auditlog.md) and
[Restricting Access by Public IP](wan-ip-restriction.md).
