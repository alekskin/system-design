# Client-Server

- Client requests something
- Server listens for requests and responds

## Server

Server is basically a machine somewhere that listens for requests.

- Server that connected to the internet has its own address -- IP address
    - All machines connected to network have one
    - IP address is local to the current network (Internet is being global does not change that)
    - Some ranges of IP addresses are standardized:
        - `10.0.0.0–10.255.255.255` -- Company networks, VPNs, and some home networks
        - `172.16.0.0–172.31.255.255` -- Company networks and container networks
        - `192.168.0.0–192.168.255.255` -- Very common on home networks
    - IPv4 addresses are limited, so we have NAT (Network Address Translation)
    - IPv6 addresses have a capacity for all machines in the world, but it's not adopted much. Usually on private networks.
- Server accepts incoming requests on certain specified ports
    - HTTP is typically on port :80 by convention
    - HTTP(S) -- :443
    - DNS -- :53
    - try `netcat`
- On Linux a single machine could listen to 65536 _(2^16 - 1)_ ports maximum
- IP address -- an address of the server in network, by which client requests something
- Port -- is just an address on the machine itself. Server gets the incoming request, and then routes the traffic to a process that listens on that port

## Client

- Resolves host to IP by making DNS request
    - try `dig` command for DNS responses
- Makes HTTP request to resolved IP
    - HTTP is a protocol on top of TCP/IP (checkout the [Protocol Stack](https://en.wikipedia.org/wiki/Protocol_stack) to know more about network protocols layers)
    - Request contains client's IP address to response could be returned (part of IP protocol, not HTTP)
- Client can make any other requests on top of UDP/TCP
