---
comments: true
---
# Directory Queries and the Login Identifier

A directory profile does not simply point at a server. It carries the query used to find
users in that directory, and the attribute those users sign in with. Both are set by the
administrator, per profile.

![Adding an Active Directory profile](../static/directory/ad-profile.png)

## The query

| Field | What it does |
|---|---|
| **Base DN** | Where the search begins, for example `CN=Users, DC=example, DC=com`. It can be the domain, or a container inside it. |
| **Filter** | An LDAP search filter, written by the administrator, that decides which directory entries this profile covers. |

The filter is an ordinary LDAP filter expression, so it can be as narrow as required. The
form's own example restricts the profile to members of one group:

```
(&(objectClass=user)(memberOf=CN=GROUP,CN=Users,dc=example,dc=com))
```

Any valid filter works - object class, group membership, organisational unit, a custom
attribute, or a combination. Users the filter does not match are not provisioned by that
profile and are not validated against it.

## The login identifier

**Username Attribute** sets the attribute a user authenticates with.

| Profile type | Options |
|---|---|
| **Active Directory** | **Username** (the sAMAccountName) or **User Principal Name (UPN)** |
| **OpenLDAP** | **UID** |

## More than one directory profile

Several Active Directory and OpenLDAP profiles can exist side by side, each with its own
server pair, Base DN, filter and username attribute. A directory can therefore be covered by
more than one profile - for example a profile scoped by filter to one organisational unit
using UPN, and another scoped to a different unit using sAMAccountName.

## The rest of the profile

| Field | |
|---|---|
| **Primary / Backup AD Server IP** | The directory servers, with a fallback |
| **Bind User** | The account used to bind. An ordinary account is sufficient |
| **Authentication Type** | Certificate, or Password + Certs |
| **Primary / Secondary DNS and WINS Server IP** | Name resolution pushed to connected users |
| **Require SSL/TLS secure connection** | Binds to the directory over LDAPS |
| **Enable Kerberos Authentication** | Authenticates users with Kerberos rather than a simple bind |

Users found by the profile are imported and kept in step with the directory - see
[Import Users from AD/LDAP](008-importADusers.md). For the second factors available to
directory-authenticated users, see
[Directory Authentication and MFA](directory-mfa.md).
