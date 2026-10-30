# Caching

- Purpose a cache to improve Latency or ease load
    - By storing data in another location so it's faster to access
    - Usually used for "expensive" operations: either network related, or requiring a lot of CPU work
    - Info of high demand is put in cache to remove load from database

- Caching could be done on:
    - Client, so client does not have to go to the server for the data, e.g.:
        - DNS cache in browser
        - JS bundle in the browser
        - Proxie's list in the app
        - Data with low volatility (or static) in general
    - Server, so server does not have to go to the DB, e.g.:
        - Low volatile data which is highly accessible: user details
        - Google's pre-loading of user account
    - Database (or in front of the Database), so critical data is accessed faster, e.g.:
        - Low volatile data which is highly accessible
    - Hardware
        - CPU has it's own caches


- Main problem of cache: cache invalidation
    - In-memory cache is hard to update, but okay for low volatile data
    - "Centralized" cache is recommended for data that is being updated
- Another problem: cache eviction: cache size is limited, how do we get rid of data?
    - LRU (least recently used): delete the oldest piece of data 
    - LFU (least frequently used): delete the least used piece of data
    - FIFO (first in, first out).
    - Or randomly


- Popular strategies:
    - Write-through. Write to DB and Cache within same operation
        - Requires to always keep 2 or more places in sync
    - Write-back. Write the cache directly. DB is updated in async manner
