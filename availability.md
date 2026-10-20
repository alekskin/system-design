# Availability

How resistant a system is to failures.

- SLO/SLA/SLI
- "Nines"
- Redundancy

- Some systems tolerate bad availability, some are not, e.g.
   - Website of local school, personal webpage -- several hours of downtime is not a big deal
   - Yuotube, cloud provider -- downtime is unacceptible

- Availability is measured as % of uptime within a year
   - In practice, measured in "nines" -- number of "nines", e.g. 99.9999% is 6 "nines"
   - High Availability -- 5 nines (99.999%, 5.3 mins/year)

- SLA (Service Level Agreement) -- guaranteed availability of a system, declared publicly
   - Explicitly declared availability of the service made by owner of the service (provider)

- SLO (Service Level Objective) -- the target to aim for the SLI over time window. Usually internal one
   - Number of 2xx vs 5XX over 30 days -- 99.99%

- SLI (Service Level Indicator) -- the exact parameter, metric, measured. "Raw data" of availability
   - Number of 2XX requests vs. number of 5XX
   - Uptime measured

- SLO usually higher than SLA to have a room.

- Error budget -- the difference between SLA and actual uptime.
   - Gives room for system upgrades involving downtime, or experimenting
   - Counted as 100% - SLO

- High availability comes with a cost. Usually it's trade-off between being responsive and have high availability

- Some parts of a system should be more available than the other

- **Redundancy** is a technique for high availability which ensures there is no single point of failure in the system
   - Passive redundancy -- increasing number of instances of a part of the system, so load distributed among them
   - Active redundancy -- check "Leader Election". Several instances of a part of the system, but only one of them is "Master" one

## Availabilities

| Nines | Availability % | Downtime per year | Downtime per month | Downtime per week | Downtime per day |
|---:|---:|---:|---:|---:|---:|
| 1 | 90% | 37 days | 73 hours | 17 hours | 2.4 hours |
| 2 | 99% | 3.7 days | 7.3 hours | 1.7 hours | 14 minutes |
| 3 | 99.9% | 9 hours | 44 minutes | 10 minutes | 1.4 minutes |
| 4 | 99.99% | 53 minutes | 4.4 minutes | 1 minute | 8.6 s |
| 5 | 99.999% | 5.3 minutes | 26 s | 6 s | 860 ms |
| 6 | 99.9999% | 32 s | 2.6 s | 600 ms | 86 ms |
| 7 | 99.99999% | 3.2 s | 260 ms | 60 ms | 8.6 ms |
| 8 | 99.999999% | 320 ms | 26 ms | 6 ms | 860 μs |
| 9 | 99.9999999% | 32 ms | 2.6 ms | 600 μs | 86 μs |
| 10 | 99.99999999% | 3.2 ms | 260 μs | 60 μs | 8.6 μs |
