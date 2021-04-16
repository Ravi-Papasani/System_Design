# SQL vs NoSQL

## When to use SQL databases - MySQL, Oracle, Postgres, MariaDB...
- Need to process ACID
- Schema will not change, will rarely change
- Need to join different tables
- SQL can only be vertical scaling, plus memory, hard disk, and CPU
- Can be extended with Master-Slave architecture
- SQL chose C and P in CAP, which means that this data will maintain a strong consistency at any time, but sometimes it is not available

## When to use NoSQL databases - MongoDB, Cassandra, HBase...
- Data has no fixed schema
- Need to make full use of cloud computing and storage, because NoSQL can be a very convenient horizontal scaling
- Often used to store logs
- NoSQL chose A and P in the CAP, which means that the availability is high consistency, but the data may be temporarily inconsistent

## NoSQL database classification
1. Key-Value
   - Redis，Memcached
   - Cache, suitable for high access load
   - Find fast
      - eg: key = userID, val = {name, dob, gender, address, phone ....}
2. Columnar (distributed file system):
   - Cassandra (eventual consistency, high availability), HBase (strong consistency, low availability)
   - Fast search speed, high scalability
   - The key can be used to scan the value of multiple rows
      - eg: key = userID, val = {followID, followID,followID,followID .....}
3. documents: MongoDB
   - Query performance is not high
   - Stored in a JSON-like object
   - ACID at document level
