---
comments: true
---
# Real-Time Log Streaming to External Systems

All logs the platform holds can be sent to an external collector - a SIEM, a log parser or
an aggregator - **in real time**, over syslog.

Events can alternatively be delivered as files on a schedule. The two are configured in the
same place and behave differently, which is worth being precise about.

## Streaming over syslog

An event stream profile set to **Syslog** sends events to the collector as they occur.
**There is no buffering interval on this path** - events leave the platform as they are
generated.

| Setting | Values |
|---|---|
| **Syslog Server Type** | **UDP** or **TCP** |
| **Syslog SSL Enabled** | True or False |
| **Syslog Facility** | KERN, USER, MAIL, DAEMON, AUTH, SYSLOG, LPR, NEWS, CRON, UUCP, AUTHPRIV, FTP, NTP, AUDIT, ALERT, CLOCK |
| **Syslog Server** | IP address or DNS name |
| **Syslog Server Port** | The collector's port |
| **Syslog Message Format** | **RFC 3164**, **RFC 5424** or **RFC 5425** |

Because the output is standard syslog in a selectable RFC format, any collector that speaks
syslog receives it - **rsyslog**, **syslog-ng**, a SIEM's syslog listener, or a log
aggregator. No integration particular to the collector is required, and none is assumed.

RFC 5425 is syslog over TLS; **Syslog SSL Enabled** secures the channel where the collector
supports it.

See [Event Stream](018-eventstream.md) for how a profile is created.

## File delivery over FTP or SFTP

The same profile can instead write events as files to an FTP, FTPS or SFTP server. This path
**does** carry an interval, and it is the only place one appears:

| Setting | |
|---|---|
| **Buffer Delay** | How many minutes events are buffered before upload |
| **FTP Hostname**, **Port**, **Username**, **Password**, **Directory** | The destination |
| **Protocol** | FTP, FTPS or SFTP |

Buffer Delay exists because file transfer is inherently batched - a file has to be closed
before it can be sent.

**Buffer Delay does not apply to the syslog path.** Choosing syslog gives continuous
delivery; choosing FTP or SFTP gives files at the interval set.

## Streaming is not the same as exporting

Two different operations are easy to confuse:

| | |
|---|---|
| **Streaming** | Events leave for the collector as they are generated. Continuous, no interval. |
| **Export or download from the console** | An administrator asks for a body of historic events. How long that takes depends on the period requested and the volume of records in it. |

The delay an administrator may notice when downloading a month of history from the console
is a property of that request, not of the live stream.

## Choosing between them

| Need | Use |
|---|---|
| Events in the collector as they happen | **Syslog**, TCP or UDP, with TLS if required |
| Periodic files for archival or an offline process | **FTP / FTPS / SFTP**, with Buffer Delay |
