---
comments: true
---
# Real-Time Log Streaming to External Systems

Events can be streamed to an external collector as they happen, or delivered as files on a
schedule. The two are configured in the same place and behave differently, so it is worth
being precise about which is which.

## Streaming over syslog

An event stream profile set to **Syslog** sends events to the collector as they occur. There
is no buffering interval on this path - events leave the platform as they are generated.

| Setting | Values |
|---|---|
| **Syslog Server Type** | **UDP** or **TCP** |
| **Syslog SSL Enabled** | True or False |
| **Syslog Facility** | KERN, USER, MAIL, DAEMON, AUTH, SYSLOG, LPR, NEWS, CRON, UUCP, AUTHPRIV, FTP, NTP, AUDIT, ALERT, CLOCK |
| **Syslog Server** | IP address or DNS name |
| **Syslog Server Port** | The collector's port |
| **Syslog Message Format** | **RFC 3164**, **RFC 5424** or **RFC 5425** |

Because the output is standard syslog in a selectable RFC format, any collector that speaks
syslog receives it - rsyslog, syslog-ng, a SIEM's syslog listener, or a log aggregator.
RFC 5425 is syslog over TLS, and **Syslog SSL Enabled** secures the channel where the
collector supports it.

## File delivery over FTP or SFTP

The same profile can instead write events as files to an FTP, FTPS or SFTP server. This path
**does** have an interval, and it is the only place one appears:

| Setting | |
|---|---|
| **Buffer Delay** | How many minutes events are buffered before upload |
| **FTP Hostname**, **Port**, **Username**, **Password**, **Directory** | The destination |
| **Protocol** | FTP, FTPS or SFTP |

Buffer Delay exists because file transfer is inherently batched - a file has to be closed
before it can be sent. **It does not apply to the syslog path.** Choosing syslog gives
continuous delivery; choosing FTP or SFTP gives files at the interval you set.

See [Event Stream](018-eventstream.md) for how a profile is created.

## Named SIEM formats

Alongside the event stream profile, an export log profile targets a collector by name -
**QRadar**, **ArcSight**, **Splunk**, plain **Syslog**, **SCP**, **SFTP** or **email** - over
TCP or UDP, with a primary and backup server. Records arrive parsed rather than as
unstructured text. See [Reporting, Dashboards and Export](reporting-and-export.md).

## Choosing between them

| Need | Use |
|---|---|
| Events in the collector as they happen | **Syslog**, TCP or UDP, with TLS if required |
| Parsed records in a named SIEM | An export log profile for that SIEM |
| Periodic files for archival or an offline process | **FTP / FTPS / SFTP**, with Buffer Delay |
