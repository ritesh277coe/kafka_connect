## kafka_connect: Code insights, Good reads, etc.</br>
Kafka Connect has its own Connect Schema. It does NOT use AVRO schema for internal representation.

Reason to have own schema:</br>
https://stackoverflow.com/questions/46301329/what-is-the-reasoning-behind-kafka-connect-schemas

Source Code:</br>
connect-api-2.2.0-sources.jar!/org/apache/kafka/connect/data/Schema.java
connect-api-2.2.0-sources.jar!/org/apache/kafka/connect/data/SchemaBuilder.java
connect-api-2.0.1-sources.jar!/org/apache/kafka/connect/data/ConnectSchema.java
And other files under connect-api-2.2.0-sources.jar!/org/apache/kafka/connect/data folder

Testcase:</br>
https://github.com/apache/kafka/tree/trunk/connect/api/src/test/java/org/apache/kafka/connect/data


Connector status:</br>
curl -s "http://localhost:8083/connectors" | jq '.[]' | xargs -I{connector_name} curl -s "http://localhost:8083/connectors/{connector_name}/status" | jq -c -M '[.name,.connector.state,.tasks[].state]|join(":|:")' | column -s : -t| sed 's/\"//g'| sort
