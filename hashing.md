# Hashing

Hashing -- operation to deterministicly transform arbitrary data to a fixed side data (string, integer).
In distributed systems usually used along with modulo.

- IP-Based (or any other ID of a user) balancing:
   - Allows to cache result of some heavy operation in-memory and serve it for the same user

- Good hashing function gives uniformity (less collisions):
   - sha-256, md5

Main problem in hashed routing:
- Scaling/dying instances break the bound between user and server

Solution:

## Consistent hashing.

Imagine a circle, which reprecents some amount of numbers (1-100, 1-360, etc)
Servers are put on that circle in the position that is a hash of their name (or any other ID).
When request come, we hash it (by user's ID of some sort), put it on a circle, and move clockwise (or another) until we reach a server.
For better uniformity, servers could be hashed several times and put on the circle again.
For balancing by weight, a particular function could be put several times.

## Rendezvous hashing.

For each user calculate (through hashing) the score for available servers.
