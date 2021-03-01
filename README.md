## kafka_connect: Code insights, Good reads, etc.

Kafka Connect has its own Connect Schema. It does NOT use AVRO schema for internal representation.

Source Code:
connect-api-2.2.0-sources.jar!/org/apache/kafka/connect/data/Schema.java
connect-api-2.2.0-sources.jar!/org/apache/kafka/connect/data/SchemaBuilder.java
connect-api-2.0.1-sources.jar!/org/apache/kafka/connect/data/ConnectSchema.java
And other files under connect-api-2.2.0-sources.jar!/org/apache/kafka/connect/data folder

Testcase:
https://github.com/apache/kafka/tree/trunk/connect/api/src/test/java/org/apache/kafka/connect/data
