# How to Run

------------------------

### 1. Run this command from cloned location:

```bash
docker-compose up -d
```

### 2. If any update, down the server:

```bash
docker-compose down -v
```

---

# Test the Kafka Cluster

------------------------

## 1. Produce messages:

### Step 1: Exec into Kafka container:

```bash
docker exec -it kafka bash
```

### Step 2: Produce a message using kafka-console-producer:

```bash
kafka-console-producer --broker-list localhost:9092 --topic orders
```

You'll get a prompt. Type a message like:

```json
{"order_id":456, "item":"phone", "qty":2}
```

Then press **Enter** to send it.  
Press `Ctrl+C` to exit.

---

## 2. Consume messages:

### Step 1: Exec into Kafka container:

```bash
docker exec -it kafka bash
```

### Step 2: Consume messages using kafka-console-consumer:

```bash
kafka-console-consumer --bootstrap-server localhost:9092 --topic orders --from-beginning
```

This command will print all messages from the beginning of the topic.  
Press `Ctrl+C` to stop consuming.

