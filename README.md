# 📘 Spring Boot + Apache Kafka – Learn by Example  

## 🌍 What is Apache Kafka?  
Apache Kafka is a **distributed event streaming platform** capable of handling **millions of events per second**.  
It is widely used for **real-time data pipelines, event-driven architectures, and stream processing**.  

At its core, Kafka allows applications to:  
- **Publish (produce)** events to Kafka topics.  
- **Subscribe (consume)** events from Kafka topics.  
- Store events reliably and replay them when needed.  
- Scale horizontally with fault tolerance and replication.  

---

## ⚡ Why Kafka with Spring Boot?  
Spring Boot provides easy integration with Kafka, allowing developers to build **producers and consumers** with minimal configuration.  
This combination is widely used in **microservices** to enable **asynchronous communication** between services.  

---

## 🏗️ Core Kafka Concepts  
- **Producer** → Application that sends messages to a topic.  
- **Consumer** → Application that reads messages from a topic.  
- **Topic** → A logical channel where messages are published.  
- **Partition** → A topic is divided into partitions for scalability.  
- **Offset** → A unique ID assigned to each message within a partition.  
- **Broker** → A Kafka server that stores messages.  
- **Consumer Group** → A group of consumers sharing the load of reading from partitions.  

---

## 📦 What You’ll Learn in This Repo  
This repository demonstrates Kafka with Spring Boot through practical examples:  

1. 🔹 **Kafka Producer** → Sending messages to a topic.  
2. 🔹 **Kafka Consumer** → Listening to messages from a topic.  
3. 🔹 **Topic Configuration** → Creating and managing topics.  
4. 🔹 **Consumer Groups** → Load balancing consumers.  
5. 🔹 **Event-driven Microservice Example** → Order → Inventory → Notification flow.  

---

## ⚙️ Prerequisites  
Before running the project, make sure you have:  
- Java 17+  
- Maven/Gradle  
- Docker (for running Kafka locally) OR Kafka installed on your system  
- An IDE (IntelliJ, VS Code, Eclipse)  

---

## 🚀 Getting Started  

### 1️⃣ Clone the Repository  
```bash
git clone https://github.com/your-username/springboot-kafka-learn.git
cd springboot-kafka-learn
```

### 2️⃣ Run Kafka using Docker  
```yaml
version: '3.8'
services:
  zookeeper:
    image: wurstmeister/zookeeper
    ports:
      - "2181:2181"

  kafka:
    image: wurstmeister/kafka
    ports:
      - "9092:9092"
    environment:
      KAFKA_ADVERTISED_LISTENERS: PLAINTEXT://localhost:9092
      KAFKA_ZOOKEEPER_CONNECT: zookeeper:2181
```

Run with:  
```bash
docker-compose up -d
```

### 3️⃣ Run the Spring Boot Application  
```bash
mvn spring-boot:run
```

---

## 📂 Project Structure  
```
springboot-kafka-learn
 ┣ src/main/java/com/example/kafka
 ┃ ┣ config/         # Kafka configuration
 ┃ ┣ producer/       # Producer service
 ┃ ┣ consumer/       # Consumer service
 ┃ ┗ controller/     # REST endpoints to test producer
 ┣ src/main/resources
 ┃ ┗ application.yml # Kafka & Spring Boot configs
 ┗ README.md
```

---

## 🔎 Example Flow  
1. Send a message via REST endpoint → Producer publishes to Kafka topic.  
2. Kafka stores the event in a partition.  
3. Consumer listens and processes the event.  
4. Logs confirm message flow.  

---

## 🎯 Use Cases of Kafka  
- 🛒 **E-commerce** → Order, Payment, Inventory services communication  
- 💳 **Banking** → Fraud detection, transaction pipelines  
- 📡 **IoT** → Device data streaming  
- 📊 **Real-time Analytics** → Monitoring logs & metrics  

---

## 🤝 Contributing  
Feel free to fork this repo, add new examples, and submit a PR. Let’s make learning Kafka easier for everyone 🚀  

---

## 📌 License  
This project is open-source and available under the [MIT License](LICENSE).  
