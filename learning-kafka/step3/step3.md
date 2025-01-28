# Step 3: Creating Topics in Kafka

### What You’ll Learn
- Understand what Kafka topics are.
- Create a topic using Kafka CLI tools.

---

### Introduction
In Kafka, a **topic** is a stream of messages belonging to the same category. Topics are partitioned to allow scalability and parallelism. In this step, you’ll create a topic named `test-topic` where producers can send messages.

---

### Hands-on Instructions

Run the following command to create a topic named `test-topic` with 3 partitions and a replication factor of 1:

```bash
kafka-topics.sh --create --topic test-topic --bootstrap-server localhost:9092 --partitions 3 --replication-factor 1
```{{exec}}
After creating the topic, verify it by listing all topics:

```bash
kafka-topics.sh --list --bootstrap-server localhost:9092
```{{exec}}

### Explanation
1. Create a topic: The --create flag creates a new topic named test-topic. The --partitions argument specifies the number of partitions, and --replication-factor specifies the number of replicas (set to 1 for single-broker setups).
2. List topics: Verifies that the topic has been successfully created and is visible.
