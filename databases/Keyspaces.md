# 📘 Amazon Keyspaces – Serverless Cassandra-Compatible NoSQL Database

**Amazon Keyspaces** is a **fully managed, serverless, wide-column database** compatible with Apache Cassandra. It’s built for **high-write throughput, time-series workloads**, and **IoT/telemetry data**, offering **CQL (Cassandra Query Language)** support without managing clusters.

---

## ✅ 1. Use Case: Cassandra-Compatible, Wide-Column Store

- Designed for apps using **Apache Cassandra**
- Uses **CQL**, not SQL or PartiQL
- Ideal for **IoT, telemetry, time-series,** and **real-time recommendation engines**
- Schema includes: **partition key, clustering columns, and static columns**

📌 **Exam Signal:**  
If the question mentions **CQL**, **wide-column data models**, or **migrating Cassandra workloads**, pick **Amazon Keyspaces**.

---

## ✅ 2. Serverless and Scalable by Default

- No infrastructure to manage
- **Auto-scales** read/write throughput
- **On-demand pricing** (based on RCU/WCU and storage)
- **Multi-AZ replication** for high availability

📌 **Exam Signal:**  
Choose Keyspaces when **zero management**, **scaling**, or **serverless NoSQL** is emphasized—**especially for Cassandra-based workloads**.

---

## ✅ 3. Schema and Query Design

- Uses **primary keys**, **clustering keys**, and **partition keys**
- No **secondary indexes**
- Query patterns must be designed around **partition key + clustering column**
- Poor partitioning = **hot partitions** and performance issues

📌 **Exam Signal:**  
Look for hints like **time-series queries**, **partition-heavy designs**, or **custom query modeling** → Keyspaces fits best.

---

## ✅ 4. Performance and Throughput Modes

- **On-Demand mode (default):** Scales based on actual traffic
- **Provisioned mode:** Set RCUs/WCUs manually for cost control
- Supports **client-side caching** (e.g., app-side logic or use with Amazon DAX indirectly)

📌 **Exam Signal:**  
- Predictable workloads → **Provisioned**
- Variable/unpredictable workloads → **On-Demand**

---

## ✅ 5. Security and Access Control

- **IAM-based access control** (not user/password-based)
- Encrypted **in transit (TLS)** and **at rest (KMS)**
- Works well for regulated environments needing strict IAM control

📌 **Exam Signal:**  
Choose Keyspaces when **security via IAM**, **no manual password configs**, or **encryption at rest/in transit** is required.

---

## ✅ 6. Monitoring and Integration

- Monitored via **CloudWatch**
- Integration with:
  - **AWS Glue** (ETL)
  - **Amazon MSK / Kinesis / Flink / Spark** for streaming ingestion
- Works as a **sink** for streaming analytics tools

📌 **Exam Signal:**  
Scenario mentions **data streaming into Cassandra-compatible store** → Choose Keyspaces.

---

## ✅ 7. Keyspaces vs DynamoDB

| Feature                  | Amazon Keyspaces           | DynamoDB                   |
|--------------------------|-----------------------------|-----------------------------|
| Query Language           | **CQL (Cassandra)**          | PartiQL / SDK               |
| Data Model               | **Wide-column**             | Key-value / Document        |
| Secondary Indexes        | ❌ Not supported             | ✅ Supported                 |
| Global Replication       | ❌ No (multi-AZ only)        | ✅ Global Tables             |
| TTL                      | ✅ Yes                      | ✅ Yes                      |
| Streams                  | ❌ No                        | ✅ Yes                      |
| Serverless               | ✅ Yes                      | ✅ Yes                      |

📌 **Exam Signal:**  
- **Keyspaces** = Use **CQL**, Cassandra model  
- **DynamoDB** = Advanced AWS-native NoSQL (with TTL, Streams, GSI/LSI)

---

## 🧠 Summary Table

| Scenario / Keyword                         | Keyspaces Feature / Concept             |
|--------------------------------------------|------------------------------------------|
| Cassandra compatibility, CQL               | Native CQL support (drop-in replacement) |
| Wide-column data model                     | Partition + clustering key modeling      |
| No server management                       | Fully managed & serverless               |
| High write throughput, time-series         | Optimized for telemetry & IoT            |
| Secure with IAM policies                   | IAM-based access, KMS encryption         |
| On-Demand or fixed throughput modes        | Choose between auto-scale vs predictable |
| Streaming ingest from Kafka/Spark/Flink    | Supports Glue, MSK, Kinesis pipelines    |
| Need Cassandra, but no ops overhead        | Amazon Keyspaces                         |

---

## 📚 Exam Focus

### ✅ When to Choose Amazon Keyspaces:
- When the scenario demands **Apache Cassandra compatibility** or **CQL**
- For **serverless, auto-scaling NoSQL** without managing nodes
- In use cases with **high-write, time-series, or telemetry workloads**
- If **security with IAM policies** and **encryption** is a priority
- For **streaming data pipelines** (Kafka, Flink, Glue → Keyspaces)

### ❌ When *Not* to Choose Keyspaces:
- If you need **global tables** → use **DynamoDB**
- If you want **secondary indexes or Streams** → DynamoDB is better
- If your team prefers **PartiQL or AWS SDKs** → DynamoDB again
- If **low-latency single-key reads** dominate and you don't need Cassandra compatibility

---
