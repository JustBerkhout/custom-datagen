This is the result of a small trial of using a custom avro schema to 
help generate test data using the Confluent https://github.com/confluentinc/kafka-connect-datagen


* Make sure your connect node/cluster has the kafka-connect-datagen installed 
(https://www.confluent.io/hub/confluentinc/kafka-connect-datagen)

* place the schema file `car-event-schema.avro` where your connect node/cluster can access it.
(e.g. `/path/to/schemafiles/car-event-schema.avro`).

* insepct and adjust the `car-event-connector.json`

* configure a connector on your connect cluster (adjust your URL), using you adjusted `car-event-connector.json`

```
curl -s -X POST -H "Content-type: application/json" http://localhost:8083/connectors --data @car-event-connector.json
```
