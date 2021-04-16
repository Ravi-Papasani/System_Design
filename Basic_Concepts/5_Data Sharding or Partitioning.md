# Data Sharding or Partitioning
Simply put, it is to split a large database into several small databases to achieve the purpose of improving manageability, performance, and possible use.

## Partition method
- **Horizontal partitioning-Data Sharding**
  - Put different rows into different tables. For example, according to age, those younger than 10 years old are listed in Table 1, and those older than 10 years old and younger than 20 are listed in Table 2. . . . . .
  - The problem is that if the partition key is incorrectly selected, for example, there are particularly many people aged 10-20, it will lead to unbalanced services.
  - AWS Data sharding https://aws.amazon.com/blogs/database/sharding-with-amazon-relational-database-service/
- **Vertical partitioning**
  - Partition by function, for example, the data of function 1 is placed in table1, and the data of function 2 is placed in table2. . . . .
  - The problem is that if a feature request is particularly large, it needs to be further partitioned.
- **Directory-Based Partitioning**
  - Maintain a catalog Table, each time you want to access the database, first go to the catalog DB to query which shard the data you want is in, and then go to specify the shard to query

## Partitioning Criteria
- key or Hash-based
  - hash(partition_key)%number of DB server
  - If you add or rape a server, use Consistent Hashing.
- List partition
  - Each partition is assigned a list, and there are several keys on the list
  - When inserting new data, see which partition has our key in the list and store it in which partition
- Round-robin partitioning
- Compound partition
  - Combine any of the above partitioning methods
    - Consistent Hashing is a combination of list partition and hash partition
      - Key -> reduced keyspace through hash -> list -> partition.

## Common Problem
- **Joins**
  - Before sharding, it was easy to join a table on a DB server, but after sharding, it became more complicated.
  - The usual solution is to [de-normalize] the table that needs to be joined (https://blog.csdn.net/qq_33290787/article/details/51956532?depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromBaidu -1&utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromBaidu-1), that is, put all the columns that need to be joined into a table. Simply put, it is to reduce the join operation
  - The problem is that there will be data inconsistencies.
- **Foreign keys**
  - Foreign keys are not supported between databases. That is to say, the data integrity check after sharding should be placed at the coding level, or SQL job to clean up the dangling reference (non-existent reference).
- **Change partition**
  - Uneven in a certain area (in the above example, there are many people in a certain age group)
  - A certain partition is requested a lot of times. For example, after a vertical partition, function 1 is extremely popular
  - _Solution_: Directory-Based Partitioning or create more partitions, and need to move data
  
