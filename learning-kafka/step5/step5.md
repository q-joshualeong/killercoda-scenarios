# Step 5: Consuming Messages from a Topic

### What You’ll Learn
- How to consume messages from a Kafka topic using a consumer.

---

### Introduction
In Kafka, **consumers** are clients that retrieve messages from topics. Consumers can read all messages (starting from the beginning) or only new messages. In this step, you’ll use the Kafka Console Consumer to read messages from the `test-topic`.

---

### Hands-on Instructions

#### Step 1: Start the Kafka Console Consumer
Run the following command to start the Kafka Console Consumer for the `test-topic`:

```bash
kafka-console-consumer.sh --topic test-topic --bootstrap-server localhost:9092 --from-beginning
```

### Explanation
1. Start the consumer: Launches the Kafka Console Consumer, which connects to the Kafka broker and retrieves messages from the test-topic starting from the beginning.
2. View messages: Displays all the messages previously sent to the topic, such as:

```text
Hello Kafka!
Welcome to Kafka hands-on training!
```
