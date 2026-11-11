---
comments: true
---
# Multi-Tenancy

A tenant is a complete, self-contained instance of the platform. Departments or
organisations that must not see each other's users, applications or policies are kept apart
as separate tenants rather than as groups inside one.

## What a tenant owns

Each tenant has its own URL - `https://<tenant>.instasafe.com` - and, behind it, its own:

| | |
|---|---|
| **Users and user groups** | Provisioned locally or synced from that tenant's own directory |
| **Applications and application groups** | Including their icons, landing pages and session controls |
| **Gateways and controllers** | Declared in that tenant, with their own protected networks |
| **Access policies** | Written against that tenant's users and applications |
| **Authentication profiles** | That tenant's own directories and identity providers |
| **Administrators** | A tenant administrator, and sub-admins with scoped rights |
| **Logs and reports** | Sessions, access, events and audit records, held per tenant |

Nothing in that list is shared. An administrator signs in to a tenant and sees only that
tenant.

## Each tenant brings its own identity source

Authentication is configured per tenant, not centrally. A tenant creates its own Active
Directory, OpenLDAP, RADIUS, SAML, OAuth or OpenID profiles pointing at the servers that
department runs - see
[Directory Queries and the Login Identifier](directory-query.md) and
[OAuth 2.0 and OpenID Connect Single Sign-On](oidc-sso.md).

Users are then authenticated by the identity infrastructure configured for their own tenant.
A department with its own Active Directory keeps using it; a department with a different
identity provider uses that one. Two departments on the same platform need not share a
directory, a provider, or a password policy.

The same applies to second factors: the MFA methods, risk profiles and session timeouts are
tenant-level settings - see [Configure MFA](mfa-configure.md).

## Administration is delegated, not pooled

Each tenant has its own administrator. Within a tenant, **Sub Admins and Roles** create
further administrators with limited rights - a role is defined by what it may read or write
across Users, Applications, ACLs, Controllers and Gateways, and a sub-admin is assigned that
role.

So a department can administer its own users and applications without being given rights
over another department's, and without rights over the tenant's own configuration.

## Where tenant scoping shows up

Tenant identity is explicit in the platform's interfaces, not implied. When a gateway is
registered it is given the tenant name taken from the tenant URL - see
[Create Gateways](006-creatinggateways.md). The platform's API endpoints are addressed per
tenant, as `https://<tenant url>/console/...` - see [API based SSO](apibasedsso.md). Where
the platform publishes an LDAP interface, the tenant appears in the base DN as
`o=<tenant name>` - see [LDAP Authentication](ldap-authentication.md).
