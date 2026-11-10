---
comments: true
---
# DNS and WINS

The **DNS & WINS configuration** allows administrators to define the Domain Name Server (DNS) and Windows Internet Name Server (WINS) settings used by connected endpoints. Proper configuration ensures seamless resolution of internal domain names and legacy NetBIOS resources.

This configuration is typically required in environments using:

- Active Directory (AD)
- On-premises applications
- Hybrid infrastructure (Cloud + Data Center)
- Legacy Windows environments using NetBIOS



## 1. Configuration Location

Navigate to:

**User Settings → DNS & WINS**

## 2. DNS Configuration

### 2.1 Primary DNS

**Field:** Primary DNS  
**Example:** `192.168.235.22`

**Description:**  
The primary DNS server used for resolving domain names.  
This is usually your internal Active Directory DNS server.



### 2.2 Secondary DNS

**Field:** Secondary DNS  
**Example:** `192.168.235.22`

**Description:**  
Backup DNS server used if the primary DNS is unavailable.



### 2.3 Best Practices for DNS Configuration

- Primary DNS should point to:
  - Internal AD DNS (for domain-joined environments)

- Secondary DNS can be:
  - Secondary AD DNS
  - Public DNS (if required)

- Avoid mixing internal and public DNS incorrectly in AD environments.



## 3. How It Works

Once configured:

- The Secure Access client/agent pushes DNS settings to the endpoint.
- The endpoint uses the configured DNS server for:
  - Internal domain resolution
  - Application FQDN resolution
  - AD authentication
- If Primary DNS fails, Secondary DNS is used.
- WINS is used only if NetBIOS resolution is required.



## 4. Save Configuration

After entering the values:

1. Click **Save**
2. The configuration will be applied to connected users/devices
3. New sessions will use updated DNS/WINS settings



## 5. Validation Steps (For Customers)

After configuration:

1. Connect to the Secure Access Agent
2. Open **Command Prompt**
3. Run:

```bash
ipconfig /all
```

Verify:
- DNS Server entries match configured values

Test DNS resolution:

```bash
nslookup your-internal-domain.local
```

## 6. Troubleshooting

| Issue                            | Possible Cause           | Resolution                |
|----------------------------------|--------------------------|---------------------------|
| Internal apps not resolving      | Incorrect DNS IP         | Verify AD DNS IP          |
| AD login failure                 | DNS not pointing to AD   | Update Primary DNS        |
| Legacy system name not resolving | WINS not configured      | Configure WINS if needed  |

---

## 7. Security Considerations

- Only authorized administrators should configure DNS/WINS.
- Incorrect DNS settings may cause:
  - AD authentication failures
  - Application access issues
  - Name resolution conflicts



