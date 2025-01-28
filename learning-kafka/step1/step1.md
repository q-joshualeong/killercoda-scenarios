# Step 1: Setting Up Kafka Environment

### What You’ll Learn
- Deploy a Kafka broker in KRaft mode using Helm.
- Set up local access to the Kafka broker using `kubectl port-forward`.

---

### Introduction
Kafka’s KRaft mode eliminates the need for Zookeeper by integrating metadata management into the Kafka broker itself. In this step, you’ll deploy a Kafka broker in KRaft mode using Helm on a Kubernetes cluster and set up local access via port forwarding.

---

### Hands-on Instructions

#### Step 1: Deploy Kafka using Helm
Run the following commands to deploy the Kafka broker in KRaft mode:

```bash
git clone https://github.com/q-joshualeong/kafka-single-broker-helm-chart.git
cd kafka-single-broker-helm-chart
helm install kafka kafka-single-broker/
```{{exec}}

#### Step 2: Port-forward the Kafka broker to localhost
Once the Kafka broker is running, forward port 9092 from the Kubernetes cluster to your local machine:

```bash
kubectl port-forward svc/kafka-broker 9092:9092
```{{exec}}

This will make the Kafka broker accessible on localhost:9092.


### Explanation
1. Deploy Kafka: The Helm chart deploys a Kafka broker configured to run in KRaft mode.
2. Port-forward Kafka: Port-forwarding allows you to connect to the Kafka broker from your local machine using the Kafka CLI tools.

Once the Kafka broker is running and accessible, proceed to {{Step 2: Installing Kafka CLI Tools}}
