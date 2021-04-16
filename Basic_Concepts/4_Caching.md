# Caching

## Application server cache
### Benefits of Caching
- Reduce network calls (network calls to DB)
- Reduce repeated calculations (store commonly used calculation results in Cache)
- Reduce DB load
- The ultimate goal is to reduce system response time and improve user experience

In a distributed system, although each machine can have its own Cache if the same request is allocated to different machines, the cache hit rate will be greatly reduced. There are two ways to solve the single-machine cache miss

## Global Cache vs Distributed Cache
- **Global Cache**
  - If a server fails, it will not affect the Cache
  - Cache server can be extended independently.
    ![](../img/Global_Cache.jpg)
- **Distributed Cache**
  - Multiple Cache servers form a cluster, and each machine stores part of Cache data
  - The advantage is that it can be unlimited Vertical Scaling (plus machines)
  - If a cache node is hung up, or an additional node is added, it may cause the cluster cache to become invalid-Consistent Hashing can solve this problem
  - ref: https://xta0.me/2016/06/22/System-Design-Cache.html

## Memcache and Redis
_Similarities_: All data are stored in memory and belong to a NoSQL database based on key-value

|  #  |  Memcache | Redis | 
| ---- | ----- | ---- |
| data structure |   Support simple key-value |   In addition to key-value, it also supports list, set, hash, etc. | 
| Persistence | Not supported, once the data is suspended, the data cannot be recovered| Supported, can save the data in the memory to the disk|
| Cluster | Consistency Hash | Master-Slave |  
| Expansion | Supports multi-threading, easy to expand | Support single thread, but can be expanded through Master-Slave cluster| 

Unless you have been doing Memcache for a long time, Redis must be a better choice, because Redis supports more data structures, supports data backup, supports things with optimistic locking, and can do PubSub

## CDN
- _Store static files_: pictures, JS, CSS, etc.
- CDN is distributed all over the world, and the system will automatically obtain data from the CDN edge closest to the user
- If the system is not large enough to require CDN, you can use subdomain + Nginx instead, for example, https://static.domain.com

## Cache Invalidation
The main point is that the cached data must be consistent with the database data, that is, data consistency (data consistency), there are three options
- **Write-through cache**
  - Data is written to Cache and DB at the same time
  - The advantage is to ensure strong consistency and reduce the risk of data loss
  - The disadvantage is that the latency is high because two data write (cache and DB) are required each time
  - Applicable to critical data, such as financial information, transaction information, passwords, etc.
- **Write-around cache**
  - Data bypasses Cache and directly writes to DB
  - The next time the data is read, the DB is read first, and then updated to the Cache
  - If it is read immediately after writing, it will cause Cache miss or data inconsistency
  - Applicable to data that will not be read immediately after being written or updated.
- **Write-back cache**
  - Data is only written to the cache, not to the DB temporarily. After some time, such as 10s, the 20s, the batch is written to the DB
  - The advantage is low latency
  - The disadvantage is that if Cache crashes, it will cause data loss
  - Applicable to non-critical data
  
