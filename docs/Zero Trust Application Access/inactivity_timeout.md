---
comments: true
---
### Inactivity Timeout 

The Inactivity Timeout feature helps Admins to enhance security by automatically disconnecting the ZTNA agent when a user is inactive. This prevents idle users from maintaining unnecessary or potentially risky VPN sessions.

This control monitors data transfer through the ZTNA agent. If the data transferred is below a configured threshold within a specified time interval, the agent disconnects the session automatically.


### Supported Platforms
- Windows
- Linux
- Darwin (macOS)

### How It Works

Admins define:
- Interval (in seconds) – The period over which activity is monitored.
- Threshold (in KB) – The minimum data transfer expected within the interval.

If the transferred data is less than the threshold in the specified interval, the ZTNA agent disconnects the user session.


### Steps to Configure Inactivity Timeout Endpoint Control

1. Go to Access Policy → Endpoint Policy.

2. Click on the “+” (Add New Policy) button.

3. Define: Provide a Policy Name, Description, and Expiry date.

4. Select Inactivity Timeout

5. Set Timeout Parameters

   - Enter the Interval (in seconds) – e.g., 300 seconds (5 minutes).

   - Enter the Threshold (in KB) – e.g., 50 KB.

   - Select action - Disconnect or Logout

   - Select Operating Systems (Windows, Linux, Darwin) where this policy should apply.

- Example: If less than 50 KB of data is transferred within 5 minutes, the session will be terminated.
6. Assign Users/User Groups

7. Save the Policy and click “Submit” to apply the policy.


### Step-by-step on How to configure and apply an Inactivity Timeout policy

1. Launch the ZTNA UI Client
2. Enter the InstaSafe Workspace URL
3. Authenticate via the redirected InstaSafe login page
4. When prompted, click "Open InstaSafe ZTNA Agent."
5. The ZTNA Agent will launch — click Connect
6. Upon connection(if applied On VPN is connected), the Chrome control policy is applied.
7. Go to the Agent & try to check whether the agent disconnects after the set parameters correctly.





