# Data Management with Avro, Schema Registry and Apache Atlas


## A parable on what happens when data management is not done


## Why we need data management

### Understanding the data

### Understanding how it's transformed

### Auditing / Tracing / Troubleshooting

### Security / PII

### Downstream integration


## Why use avro

### well defined schema

### schema evolution included

### Automatic compatibility resolution

### Bindings Galore


## Avro best practices for compatibility

### Data type usage and default values

### Enforce constraints at build time

### Enforce compatibility checks at build and release time

### Use a schema registry

### Share common schemas

### Keep it simple

### Careful of Avro JSON


## Kafka with Avro

### Use the schema registry

### One schema per topic

### Always backwards compatible

### New topic for compatibility breakages


## Kafka Connect Avro to S3/HDFS

### Large files

### Works on stream time

### Will alter schema


## Apache Atlas for Management

 * Write demo of how I integrated a CDC and stream app.  Then look at KSQL if time permits. Finally ponder API.
### What is it

### How it can integrate with kafka

### Integration with Streams

### Integration with KSQL

### Integration with Kafka Connect

### ??? API Integration ???


## Conclusion
