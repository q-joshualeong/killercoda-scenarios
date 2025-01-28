# Step 2: Installing Kafka CLI Tools

### What You’ll Learn
- Download and set up Kafka CLI tools locally.
- Verify the connection to the Kafka broker.

---

### Introduction
In this step, you’ll download and set up Kafka CLI tools on your local machine. These tools will be used to interact with the Kafka broker running in your Kubernetes cluster.

---

### Hands-on Instructions

Before starting, open a new tab as your first tab is now blocked running the port forwarding.

#### Step 1: Download Kafka CLI tools
Run the following command to download Kafka:

```bash
sudo apt install -y openjdk-11-jdk
sudo mkdir -p /usr/local/kafka
cd /usr/local/kafka
sudo wget https://dlcdn.apache.org/kafka/3.9.0/kafka_2.13-3.9.0.tgz
sudo tar -xzf kafka_2.13-3.9.0.tgz --strip-components=1
```{{exec}}

#### Step 2: Add Kafka bin to your PATH
Add the Kafka `bin` directory to your system’s `PATH` so you can run CLI tools globally:

```bash
echo 'export PATH=$PATH:/usr/local/kafka/bin' >> ~/.bashrc
source ~/.bashrc
```{{exec}}

#### Step 3: Verify the installation
Run the following command to ensure the Kafka CLI tools are working and can connect to the broker:

```bash
kafka-topics.sh --bootstrap-server localhost:9092 --list
```{{exec}}

If the setup is correct, this will list all existing topics (initially, there won’t be any topics).

### Explanation
1. Download Kafka: Downloads and extracts Kafka CLI tools to /usr/local/kafka for consistent usage across your system.
2. Update PATH: Configures your shell to include Kafka’s bin directory in the PATH, making commands like kafka-topics.sh available globally.
3. Verify installation: Ensures the Kafka CLI tools are correctly installed and can connect to your Kafka broker running on localhost:9092.