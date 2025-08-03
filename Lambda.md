# 📘 AWS Lambda – Serverless Compute

AWS Lambda is a **serverless, event-driven compute service** that runs your code without provisioning or managing servers. It’s ideal for short-lived, reactive workloads triggered by events.

---

## ✅ 1. Event-Driven Architecture

* Lambda is triggered by **events** from 200+ AWS sources:

  * **S3:** On object upload/delete
  * **DynamoDB Streams:** On table changes
  * **Kinesis / MSK:** For real-time streaming ingestion
  * **EventBridge / CloudWatch Events**: Scheduled or system triggers
  * **API Gateway:** For REST API invocations

**📌 Exam Signal:**
If the question involves **event-based processing** like S3 uploads, stream records, or scheduled jobs → choose Lambda.

---

## ✅ 2. Runtime & Execution Environment

* Supports Python, Node.js, Java, Go, .NET, Ruby, and custom runtimes (via container images or Runtime API)
* **Max timeout: 15 minutes**
* Ephemeral storage: `/tmp` with 512MB or configurable up to 10GB
* **VPC Support** for secure networking

**📌 Exam Signal:**
For **short-lived** processes with runtime flexibility and no need to manage infrastructure, Lambda fits.

---

## ✅ 3. Data Engineering Use Cases

| Use Case                               | Why Use Lambda?                              |
| -------------------------------------- | -------------------------------------------- |
| Real-time ETL (Kinesis, S3, DynamoDB)  | Trigger Lambda on incoming data              |
| Event-driven ingestion                 | Lightweight compute on file or stream upload |
| Orchestration step (in Step Functions) | Stateless logic in a pipeline                |
| Log processing                         | Real-time transformation before delivery     |
| Scheduled data cleanup                 | CloudWatch Events trigger Lambda             |

**📌 Exam Signal:**
When asked about **automated ETL steps, stream consumption, or log transformation** → think Lambda.

---

## ✅ 4. Error Handling & Retries

* **Automatic retries** for asynchronous invocations
* **Dead Letter Queues (DLQs)**: SQS or SNS for failed events
* Integrates with **Step Functions** for complex error workflows
* Use **Lambda Destinations** for success/failure handling (e.g., route to SQS, SNS)

**📌 Exam Signal:**
Look for **fail-safe design**, retries, or failure notifications → use DLQ or Destinations.

---

## ✅ 5. Scaling & Concurrency

* **Automatic horizontal scaling** based on event rate
* **Concurrency limits** (default: 1000 per region; configurable)
* **Provisioned Concurrency**: Pre-warm functions for consistent latency
* **Reserved Concurrency**: Reserve capacity for critical functions

**📌 Exam Signal:**
If predictable latency or throttling control is needed → use **Provisioned or Reserved Concurrency**.

---

## ✅ 6. IAM & Security

* Lambda uses **IAM Execution Roles** for resource access (e.g., S3, DynamoDB)
* **Resource-based policies** allow cross-account invocation
* Can be placed inside a **VPC** to access private resources
* Supports **environment variables** (can be encrypted with KMS)

**📌 Exam Signal:**
For questions involving **secure data access or cross-service roles**, IAM roles for Lambda are key.

---

## ✅ 7. Monitoring & Logging

* Integrated with **CloudWatch Logs** (auto-created log groups per function)
* **X-Ray Tracing** for distributed tracing
* **CloudWatch Metrics** for invocations, errors, duration, throttles

**📌 Exam Signal:**
Use **CloudWatch + X-Ray** for Lambda observability.

---

## ✅ 8. Invocation Models

| Model            | Use Case                                              |
| ---------------- | ----------------------------------------------------- |
| **Synchronous**  | API Gateway, SDK (waits for response)                 |
| **Asynchronous** | S3, SNS, CloudWatch Events (retry, DLQ)               |
| **Poll-based**   | DynamoDB Streams, Kinesis (uses event source mapping) |

**📌 Exam Signal:**
Know which services **invoke Lambda directly (sync)** and which **trigger async or via polling**.

---

## ✅ 9. Lambda vs Alternatives

| Scenario                         | Use Lambda?                      | Alternatives                      |
| -------------------------------- | -------------------------------- | --------------------------------- |
| Short tasks triggered by events  | ✅ Yes                            |                                   |
| Long-running workflows (>15 min) | ❌ No                             | Use Step Functions + ECS/Fargate  |
| Managed ETL pipelines            | ❌ No                             | Use AWS Glue                      |
| Stateful processing              | ❌ No                             | Use MSK, Flink, EMR               |
| High concurrency + low latency   | ✅ (with Provisioned Concurrency) | EC2/ECS if more control is needed |

**📌 Exam Signal:**
Lambda is ideal for **short, stateless, reactive** tasks. Avoid for **long-running or stateful** pipelines.

---

# 🧠 Summary Table

| Scenario / Keyword                       | Lambda Feature or Behavior                   |
| ---------------------------------------- | -------------------------------------------- |
| Event-driven ingestion                   | S3, Kinesis, DynamoDB Streams trigger Lambda |
| Stateless compute                        | No infra mgmt, auto-scale                    |
| Max duration constraint                  | 15-minute limit                              |
| Secure access to S3 or RDS               | IAM Execution Role + VPC access              |
| Async error handling                     | DLQs and Destinations                        |
| Auto scaling for high-throughput streams | Built-in scaling with event source mapping   |
| Predictable latency                      | Use Provisioned Concurrency                  |
| API-based invocation                     | Use with API Gateway (sync)                  |
| Real-time stream ETL                     | Use with Kinesis or DynamoDB Streams         |

---

## 📚 Exam Focus

- Choose **AWS Lambda** when:  
  - You need **serverless, event-driven compute** for short-lived tasks  
  - Your workload is triggered by **events** like S3 uploads, DynamoDB streams, or scheduled triggers  
  - You require **automatic scaling and pay-per-use billing**  
  - You want **stateless compute without managing infrastructure**  
  - You need **built-in retry and error handling with DLQs and Step Functions integration**  
  - You want **fine control over concurrency with Provisioned or Reserved Concurrency**  
- Avoid Lambda if:  
  - Your workflows are **long-running (>15 minutes)** → use **Step Functions + ECS/Fargate**  
  - You require **stateful or managed ETL pipelines** → use **AWS Glue, MSK, or EMR**  
  - You need **high custom control over environment** → consider **EC2 or ECS**  

---
