# Apache Kafka and Zookeeper Setup Using Docker Compose

This project provides a simple Docker Compose configuration to run Apache
Kafka and Zookeeper locally. It is useful for learning Kafka basics, testing
producers and consumers, and setting up a local development environment.

---

## Project Description

Apache Kafka requires Zookeeper for managing broker metadata and coordination.
This project uses Docker Compose to run both Kafka and Zookeeper as containers.
The setup runs a single Kafka broker and exposes the required ports for local
development.

---

## Services Included

### Zookeeper
- Image: confluentinc/cp-zookeeper:7.5.0
- Port: 2181
- Used for Kafka coordination and metadata management

### Kafka
- Image: confluentinc/cp-kafka:7.5.0
- Ports:
  - 9092 (internal Docker network)
  - 29092 (local host access)
- Single broker setup
- Depends on Zookeeper

---

## Tools and Technologies Used

- Docker
- Docker Compose
- Apache Kafka
- Apache Zookeeper
- Confluent Platform Images

---

## Docker Compose Configuration

- Kafka broker is configured with advertised listeners for:
  - Internal container communication
  - Local host access
- Zookeeper is exposed on port 2181
- Suitable for single-node local development

---

## How to Run the Project

### Prerequisites
- Docker installed
- Docker Compose installed

### Steps

1. Clone or download the repository
2. Navigate to the project directory
3. Start Kafka and Zookeeper
   ```bash
   docker-compose up -d
