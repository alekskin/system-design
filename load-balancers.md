# Load Balancers

Clients issuing more requests than a server can handler create a problem: overloading
Solution: vertical scaling or horizontal scaling.

Horizontal scaling requires routing.
The answer is Load Balancer (a proxy).

- Load Balancer work is balancing (distributing) or routing work between known number of instances of an application
- nginx is also can be used as LB

2 types:
- software balancers
- hardware balancers

How balancer know where to route?
- Configuration

Strategies:
- Random
- Round robin
- Weighted (some get more by the weight; e.g. more powerful server)
- Load-based (healthcheck; timing)
- IP-based (users on same IP go to the same instance)
   - helpful for in-memory caches
- Path-based
   - separate servers by use-case

There could be more than 1 LB in the system:
- IP-based first
- Then for DB


