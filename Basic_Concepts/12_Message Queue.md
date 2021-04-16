# Message Queue

## Kafka
- Exact once delivery
- Support producer-consumer and Publish-Subscribe 
- High throughput, the best support for large amounts of data
- Automatically support distributed, use Zookeeper for load balancing.

## Redis
- At most once delivery
- Support producer-consumer and Publish-Subscribe
- Lightweight Message Queue
- in-memory, so data processing is fast

## AWS SQS
- At least once delivery
- Only supports Producer-consumer mode, SNS is Publish-Subscribe mode is
- The last unprocessed message can be automatically put into the queue for processing

