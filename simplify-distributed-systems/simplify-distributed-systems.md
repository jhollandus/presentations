# Simplifying Distributed Systems Using Apache Kafka

## Description

With the rising popularity of micro service architectures and typical scaling patterns used at enterprises, distributed
systems are becoming more common and complex.  What was once a simple web server connected to a database now can entail
multiple databases, caches and integrations to other services/systems.  By using Apache Kafka one can take much of the
integration complexity out of the system, reduce coupling between different parts of the system, easily expand functionality
without disruption and scale horizontally.

This presentation will cover patter concepts that can be used to achieve all of the above.  Apache Kafka will play
a central role in it's design.

## Outline

### Background

- what I do
- how long
- tech interests

### problem description

- how did we get There
  - growth over time
  - deliberate via microservice architectures
- distributed anti-patterns
  - distributed transactions
  - multi dispatch updates
  - point-to-point communication
  - integration at database
- Difficulty expanding system
  - API coupling (microservice turned monolith)

### brief kafka introduction

- Design
  - distributed append only log
  - streaming, ordered
  - topics and partitions
  - consumers
  - producers
- scaling
  - consumers
  - brokers
- log compaction
- comparison to typical pub/sub brokers
  - message destroyed on consume
  - inbox per consumer
  - unordered


### ways to solve problems

- kafka as event hub
  - decouple consumers
- kafka replication
  - across DCs
  - between subsystems
- stream processing
  - data enrichment
- stream import/export
  - data consistency
    - databases, caches, file systems
- compacted log as permanent record store
  - refresh databases
  - refresh caches
- Add new features easily
 - just another consumer group
- message replay
- zero downtime changes
  - expand then contract

### Gotchas

- Data formats
 - prepare for evolution
 - compact well defined (schema)
 - options, avro, protobuf
 - JSON good/Bad
   - good, easily serialized/deserialized
   - good, human readable by default
   - bad, no real schema standard
   - bad, serialization/deserialization expensive
   - bad, very verbose, requires compression (more CPU)
- Bad Consumers
  - not idempotent
    - cannot replay messages
- Misconfigured kafka/zookeper
 - understand availability v. consistency
  - ACKs
  - min ISR
  - unclean leader election
 - zookeeper timeouts
 - topics mis-partitioned for load
  - over provisioning preferred
- Dead lettering / Retry
  - standard methods may not apply
  - kill and fix versus dead lettering
- Monitoring
 - false positives on lag
  - use burrow or other windowing solution

### Questions
