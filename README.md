This is the result of a small trial of using a custom avro schema to 
help generate test data using the Confluent https://github.com/confluentinc/kafka-connect-datagen


* Make sure your Connect node/cluster has the kafka-connect-datagen installed 
(https://www.confluent.io/hub/confluentinc/kafka-connect-datagen)

* Place the schema file `car-event-schema.avro` where your connect node/cluster can access it.
(e.g. `/path/to/schemafiles/car-event-schema.avro`).

* Insepct and adjust the `car-event-connector.json`

* Configure a connector on your connect cluster (adjust your URL), using your adjusted `car-event-connector.json`

```
curl -s -X POST -H "Content-type: application/json" \
  --data @car-event-connector.json \
  http://localhost:8083/connectors

```
