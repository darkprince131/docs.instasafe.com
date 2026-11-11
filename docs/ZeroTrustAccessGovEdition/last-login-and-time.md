---
comments: true
---
# Last Login, and Access by Day and Time

## Seeing the last login

The last successful sign-in is visible to the administrator and to the user, in different
places and for different reasons.

**To the administrator.** The **User Last Login Report** lists every user with the timestamp
of their most recent successful connection, and gateways with theirs. It is filterable,
searchable and exported to CSV like any other report - see
[Reporting, Dashboards and Export](reporting-and-export.md).

The audit section also carries a **Never Logged In** view, which is the same question asked
the other way: accounts that exist and have never been used. Dormant accounts are a standing
risk, and this is how they are found.

**To the user.** The end-user dashboard shows the user their own **current session** and
their **previous session** side by side - login time, public IP, country, operating system
and browser for each. A user who did not make that previous sign-in can see as much
immediately, which is the point of showing it.

**In the record.** Every session is held in the **Session Log** with login time, logout time,
public IP, country, tunnel address, data volumes and the serving gateway. The last login is
therefore verifiable from the record, not only from a summary view.

## Acting on a dormant account

**Long Inactivity Login** is a risk type: an account that has not been used for a long period
and is then used again trips the profile, and the action is the administrator's choice -
alert, deny, suspend or disconnect. See
[Account Lockout, Idle Timeout and Forced Logout](session-controls.md).

The User Settings page separately carries **Inactive Users** actions - Warning, Suspend and
Delete - which act on accounts that have gone unused.

## Restricting access by day and time

Access can be limited to particular days and hours, as a contextual condition on the access
policy rather than a property of the account.

An **Application Access Time** dataset is created and populated with the days of the week
access is permitted, and a **Start Time** and **End Time** for those days. The dataset is
then attached to the policy, so the restriction applies to the users and applications that
policy covers.

Typical uses are allowing a business application only during working hours, and refusing
sensitive applications outside them or at weekends.

The full steps are in [Application Access Time](applicationaccesstime.md).

Because the restriction is evaluated at access time, a session that is active when the
window closes is governed by the same policy, and access outside the window is refused
rather than silently narrowed.
