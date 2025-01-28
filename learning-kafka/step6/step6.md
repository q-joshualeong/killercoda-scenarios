# Step 6: Consumer Groups and Offsets

### What You’ll Learn
- How consumer groups work in Kafka.
- How offsets allow replaying or resuming messages.

---

### Introduction
Kafka uses **consumer groups** to manage multiple consumers working together to read messages from topics. Each partition in a topic is assigned to a single consumer in the group, allowing for parallelism. Offsets track a consumer’s progress and enable replaying or resuming messages.

---

### Hands-on Instructions

#### Step 1: Start consumers in the same group
Open two separate terminals and start Kafka Console Consumers with the same consumer group ID (`group1`):

```bash
kafka-console-consumer.sh --topic test-topic --bootstrap-server localhost:9092 --group group1
```

#### Step 2: Produce new messages
In a third terminal, start the Kafka Console Producer and send messages to the test-topic:

```bash
kafka-console-producer.sh --topic test-topic --bootstrap-server localhost:9092
```

Type the following messages and press Enter after each:

```text
Message 1 from producer!
Message 2 from producer!
```

#### Step 3: Check consumer group offsets
Run the following command to view the offsets for the group1 consumer group:
```bash
kafka-consumer-groups.sh --bootstrap-server localhost:9092 --describe --group group1
```


#### Step 4: Reset offsets
Replay all messages by resetting the offset for group1:

```bash
kafka-consumer-groups.sh --bootstrap-server localhost:9092 --group group1 --reset-offsets --to-earliest --execute --topic test-topic
```

### Explanation
1. Consumer groups: Multiple consumers in the same group share the load of consuming messages from partitions in a topic.
2. Offsets: Kafka tracks the position of each consumer in a topic using offsets, which allows consumers to resume or replay messages as needed.
3. Resetting offsets: Resetting offsets lets you replay all messages from the beginning of the topic for a specific consumer group.
