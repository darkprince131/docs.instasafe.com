---
comments: true
---
# Scaling and Connection Distribution

Capacity is added by deploying more of the same components rather than by making one of them
bigger, and user connections are distributed across them by the platform itself.

## The agent does not choose its controller

An endpoint is not configured with a controller address. The sequence is:

1. The agent connects to the platform's web service and the user authenticates - identity,
   geo check, device binding, device checks and the second factor.
2. **Only after that** does the platform append the controller's domain name and port to the
   agent's configuration file.
3. The agent then opens a DTLS tunnel to that controller.

See [ISA Components](002-architecture.md).

Two things follow. The controller a user lands on is decided by the platform at sign-in, so
distribution is a platform function rather than an endpoint setting or a client-side
failover list. And a controller is only reachable by an endpoint that has already
authenticated.

## Controllers

More controllers are deployed as the user count grows - an active-active deployment, with
each controller carrying part of the load. Deployments above a thousand users are sized this
way, adding controllers in proportion to users rather than enlarging one.

A controller can also be held in **active-passive** standby: a second controller configured
with the same network range and port, on separate infrastructure, ready to take over.

## Gateways

A gateway has a published concurrent-connection capacity, which differs by gateway type -
see [Gateways](006agateway.md). When the number of simultaneous users exceeds what one
gateway supports, further gateways are provisioned and users are served across them.

Each gateway profile also names a **Backup Gateway**, so a gateway has a declared successor
if it becomes unavailable - see [Create Gateways](006-creatinggateways.md).

Because applications are attached to gateways, where an application is published also
determines which gateway carries its traffic - see
[Add Application to Gateway](006b-addapptogateway.md) and
[What Traffic Goes Through the Tunnel](tunnel-scope.md).

## Sizing

Capacity planning is therefore a count of components: controllers in proportion to
concurrent users, gateways in proportion to simultaneous connections per gateway type, with
a backup declared for each. The published per-gateway figures come from internal simulation
and vary with the traffic a deployment actually carries, so they are a starting point for
sizing rather than a guarantee.
