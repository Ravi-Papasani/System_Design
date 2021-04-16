# Key Characteristics of Distributed Systems

## Scalability
- **Horizontal Scaling**: Add multiple machines horizontally, such as Autoscaling group and Cassandra and MongoDB in AWS.
- **Vertical Scaling**: Increase the performance of an existing machine, such as CPU, memory RAM, Storage, etc. For example, MySQL is easy to perform Vertical Scaling, but this kind of expansion has Downtime.

## Reliability
- Simply put, reliability means that when a certain node in the system or a certain machine suddenly fails to work, the system needs to have the ability to automatically recover and continue to provide services. The most important thing is to eliminate single points of failure. Redundancy is the most common solution to improve reliability.

## Availability
- Reliable systems are available, but available systems are not necessarily reliable. Because the availability is only for the general situation (no malicious attacks), and the availability within a certain period. For example, AWS S3 Standard provides 99.99% availability

## Efficiency
- **Latency**: Response time. How much information can be sent (regardless of message size)?
- **Bandwidth**: swallow measure. At a specified time, how much volume of data can be sent
- **Application**：
  - Multiple AZ, CloudFront (CDN), Route53 (DNS), Direct Connect (VPN), VPN endpoints, etc. in AWS, and
  - High-performance computing in AWS, optimized storage can improve efficiency

## Serviceability or Manageability
- How easy the system can be repaired or maintained.
- The higher the maintainability, the shorter the time it takes to maintain the machine, and the higher the availability.
