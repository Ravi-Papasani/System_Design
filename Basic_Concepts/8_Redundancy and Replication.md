# Redundancy and Replication

## Redundancy
- Standby machine, once the machine fails, the standby machine is used instead. Eliminate single points of failure
- Improve system reliability

## Replication
- Real-time sharing of resources with redundant machines to maintain data consistency
- The most common is used in DB: Master-Slave mode. The master machine is mainly responsible for writing data, and then synchronize it to the slave machine. The Slave machine is mainly responsible for reading data. Once the master machine is down, select one of the slave machines to be the master

## Difference
The biggest difference between Redundancy and Replication is that Replication is synchronized with host data in real-time, while Redundancy is not necessarily real-time

![](../img/Redundancy_and_Replication.png)
