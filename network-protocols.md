# Network Protocols

- IP
  - Packet of bytes with header
  - Contains source IP address
- TCP
  - built on top of IP (adds own header to IP packet payload)
  - starts with handshake (3 messages; part of protocol) establishing connection
  - Adds resilency by guaranteeing packets being received and the order of the packets
  - Requires receiver to acknowledge receiving
  - allows to end the connection
- HTTP
 - built on top of TCP
 - protocol for request-response model handling
 - has its own headers followed by payload

