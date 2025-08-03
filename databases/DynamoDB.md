# 📘 Amazon DynamoDB – Fully Managed NoSQL Key-Value & Document Database

Amazon DynamoDB is a fully managed, serverless, NoSQL database designed for high-performance applications. 
DynamoDB provides single-digit millisecond latency at any scale, supporting key-value and document data models for a wide range of use cases. 
Its serverless architecture frees developers from provisioning or managing servers, allowing them to focus on application development rather than database maintenance.

---

## ✅ 1. Data Model and Access Patterns

- **Key-Value or Document-based (JSON)** data
- Each item is uniquely identified by a **Primary Key**:
  - **Partition Key** only
  - **Partition + Sort Key**
- No SQL JOINs or complex queries
- Designed for **single-table**, denormalized access

📌 **Exam Signal**:  
If scenario describes **schema-less**, **fast lookups**, **millisecond latency**, or **NoSQL patterns** → choose **DynamoDB**

---

## ✅ 2. Capacity Modes

- **On-Demand**: Auto-scales based on workload; billed per request
- **Provisioned**: Set read/write throughput manually; supports Auto Scaling

📌 **Exam Signal**:  
- **Spiky or unpredictable traffic** → use **On-Demand**  
- **Predictable, steady traffic** → use **Provisioned**

---

## ✅ 3. Indexing

- **Local Secondary Index (LSI)**: Same Partition Key, different Sort Key
- **Global Secondary Index (GSI)**: Different Partition + Sort Key
- Supports **eventual consistency** by default

📌 **Exam Signal**:  
If scenario mentions **alternate query patterns** or **sorting on non-primary key attributes** → use **GSI or LSI**

---

## ✅ 4. Data Consistency & Performance

- **Eventually Consistent Reads** by default
- **Strongly Consistent Reads** are optional
- **DAX (DynamoDB Accelerator)**: In-memory cache for microsecond read latency

📌 **Exam Signal**:  
If question emphasizes **read performance** or **caching**, especially **low latency** → use **DAX**

---

## ✅ 5. Security and Access Control

- Supports **encryption at rest** with **AWS KMS**
- **IAM-based** fine-grained access control
- **VPC access** using **VPC Endpoints (PrivateLink)**
- Integrates with **CloudTrail** for auditing

📌 **Exam Signal**:  
If scenario mentions **encryption**, **fine-grained access**, or **auditing**, highlight **KMS, IAM, CloudTrail**

---

## ✅ 6. Backups & Point-in-Time Recovery

- **On-demand backups** and **PITR** (last 35 days)
- Supports **cross-region replication** via **Global Tables**

📌 **Exam Signal**:  
- For **PITR**, **backups**, or **disaster recovery needs** → enable those respective options  
- For **multi-region high availability** → use **Global Tables**

---

## ✅ 7. Streams & Event-Driven Processing

- **DynamoDB Streams** capture item-level changes
- Can trigger **AWS Lambda** for real-time processing
- Common in **serverless data pipelines**

📌 **Exam Signal**:  
If scenario describes **capturing DB changes** for further processing → use **DynamoDB Streams + Lambda**

---

## ✅ 8. TTL, Auto Scaling, and Misc.

- **Time to Live (TTL)**: Auto-expire items
- **Auto Scaling** for provisioned mode
- **Transactions** supported for multi-item **ACID** operations
- **Import/Export to S3** supported
- Supports **PartiQL** (SQL-like querying) on NoSQL data

📌 **Exam Signal**:  
If **automated cleanup**, **transactional ops**, or **S3 import/export** is required → **DynamoDB** fits well

---

## ✅ 9. DynamoDB vs Alternatives

| Scenario                            | Choose DynamoDB                          | Choose Alternative                          |
|-------------------------------------|------------------------------------------|---------------------------------------------|
| Millisecond latency, key-value ops | ✅ DynamoDB                              | ❌ RDS not optimized for latency            |
| Unstructured / JSON document data  | ✅ DynamoDB                              | ❌ Redshift not for unstructured NoSQL      |
| Complex joins or analytics         | ❌ No JOINs                              | ✅ RDS / Redshift / Athena                  |
| Real-time updates, stream proc.    | ✅ Streams + Lambda                      | ❌ S3 lacks real-time capability            |
| Flexible scaling & HA              | ✅ Serverless + Global Tables           | ❌ Aurora/Redshift need more tuning         |

---

## 🧠 Summary Table

| Scenario / Keyword                | DynamoDB Feature / Concept             |
|----------------------------------|----------------------------------------|
| Serverless NoSQL with key-value  | DynamoDB                               |
| Predictable traffic              | Provisioned mode                       |
| Spiky, variable traffic          | On-Demand mode                         |
| Alternate access patterns        | Global Secondary Index (GSI)           |
| Low-latency read performance     | DAX (DynamoDB Accelerator)             |
| Change data capture              | DynamoDB Streams                       |
| Cross-region DR                  | Global Tables                          |
| Secure access                    | KMS, IAM, VPC Endpoints                |
| Automated TTL                    | Time to Live (TTL)                     |
| Point-in-time recovery           | PITR, Backups                          |
| SQL-like queries                 | PartiQL                                |
| Multi-item atomic ops            | DynamoDB Transactions                  |
| Import/export from S3            | DynamoDB Import/Export Utility         |

---

## 📚 Exam Focus

### ✅ When to Choose Amazon DynamoDB:

- If the scenario involves **schema-less**, **JSON**, or **key-value** access patterns
- If **millisecond latency** or **serverless NoSQL** is needed
- For **real-time data ingestion**, **event-driven pipelines**, or **change tracking**
- When **scaling needs** are unpredictable → use **On-Demand**
- For **globally distributed**, highly available NoSQL systems → use **Global Tables**
- When **low-latency caching** is required → use **DAX**
- For **automated cleanup**, **TTL**, **import/export**, or **transactions**

### ❌ When *Not* to Choose DynamoDB:

- When **JOINs**, **multi-table relationships**, or **complex querying** is required → use **RDS** or **Aurora**
- For **OLAP**, **aggregations**, or **data warehousing** → use **Redshift**
- For **ad hoc SQL queries on S3** → use **Athena**
- If **strict relational integrity** is needed over NoSQL flexibility

---
