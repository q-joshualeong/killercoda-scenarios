# Step 4: Producing Messages to a Topic

### What You’ll Learn
- How to produce messages to a Kafka topic using a producer.

---

### Introduction
In Kafka, **producers** are clients that send records (messages) to specific topics. Each message is stored in Kafka for consumers to retrieve later. In this step, you’ll use the Kafka Console Producer to send messages to the `test-topic`.

---

### Hands-on Instructions

#### Step 1: Start the Kafka Console Producer
Run the following command to start the Kafka Console Producer for the `test-topic`:

```bash
kafka-console-producer.sh --topic test-topic --bootstrap-server localhost:9092
```

#### Step 2: Send messages to the topic
Inside the producer terminal, type the following messages one by one and press Enter after each:

```text
Hello Kafka!
Welcome to Kafka hands-on training!
```
### Explanation
1. Start the producer: Launches the Kafka Console Producer, which connects to the broker and allows you to send messages to the specified topic.
2. Send messages: Messages entered in the producer terminal are sent to the test-topic and stored in Kafka for consumers to retrieve.


Once messages are produced, proceed to Step 5: Consuming Messages from a Topic.






