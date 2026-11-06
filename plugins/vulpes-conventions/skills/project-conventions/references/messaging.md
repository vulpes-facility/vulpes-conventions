# Messages and events

Select the broker by the kind of message.

| Kind | Default | Use it for |
| --- | --- | --- |
| Work queue | RabbitMQ | A task for one consumer, routing, retries with a delay |
| Event stream | Kafka | Events for many consumers, replay, order by key, retention |

1. Write each message contract in an AsyncAPI document.\
   For Kafka, you MAY keep the schemas in a schema registry (Avro, Protobuf, or JSON Schema) with a compatibility check.
2. Give each message the CloudEvents attributes: `id`, `source`, `type`, `specversion`, and `time` in UTC.
3. Publish through a transactional outbox.\
   Write the message to the outbox table or collection in the same transaction as the change.\
   A relay sends it after the commit.
4. Delivery is at least once.\
   Consumers MUST be idempotent.\
   Keep the `source` and the `id` of each processed message.\
   Write that record in the same transaction as the changes of the consumer.
5. Retry with a backoff.\
   After the last attempt, move the message to a dead-letter queue or topic.

- The domain raises domain events.\
  The application changes them to integration events, and writes them to the outbox.
- Publishers and consumers are in `infrastructure`.\
  A consumer calls one use case in `application`.
- RabbitMQ: use quorum queues.\
  Turn on publisher confirms.\
  Publish with `mandatory`, or set an alternate exchange, so that a message with no route is not lost.
- RabbitMQ: acknowledge a message only after its work commits.\
  Set a prefetch limit.\
  Set the dead-letter strategy of quorum queues to `at-least-once`, with `overflow` set to `reject-publish`.
- Kafka: use KRaft mode.\
  Turn off automatic offset commits (`enable.auto.commit=false`).\
  Commit the offset only after the work commits.
- Kafka keeps order only in one partition of one topic.\
  Put all events of one aggregate in one topic, with the aggregate id as the key.\
  Name the topic `<domain>.<aggregate>.v<n>`, and put the event name in the CloudEvents `type`.
- Kafka: give each service its own consumer group.
- Kafka in production: set the replication factor to 3, `min.insync.replicas` to 2, and `acks=all` with an idempotent producer.
