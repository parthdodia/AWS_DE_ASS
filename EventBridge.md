# 📘 Amazon EventBridge

Amazon EventBridge is a **serverless event bus service** that makes it easy to connect applications using data from your own apps, integrated SaaS apps, and AWS services with near real-time event routing and processing.

---

## ✅ 1. Event-Driven Architecture & Serverless Integration

- Enables building **loosely coupled, event-driven applications**  
- Routes events from **AWS services, SaaS partners, or custom apps** to targets like Lambda, Step Functions, SNS, SQS, Kinesis, and more  
- Supports **schema discovery and registry** for event validation and code generation  

📌 **Exam Signal:**  
If a question involves **event routing without managing infrastructure** or **integrating SaaS with AWS apps via events**, EventBridge is the answer.

---

## ✅ 2. Event Sources & Targets

- Supports **native AWS services** as event sources (CloudTrail, EC2, S3, CodePipeline, etc.)  
- Integrates with **SaaS providers** (Zendesk, PagerDuty, Datadog, etc.) as event sources  
- Targets include **AWS Lambda, Step Functions, Kinesis streams, SQS queues, SNS topics, and more**  

📌 **Exam Signal:**  
If a scenario involves **event ingestion from SaaS or AWS services routed to serverless or stream processing**, EventBridge fits perfectly.

---

## ✅ 3. Event Filtering & Routing Rules

- Define **event patterns** to filter and route events selectively  
- Supports **content-based filtering** on event payloads  
- Routes events to **multiple targets** based on rules  
- Supports **dead-letter queues (DLQs)** for failed event deliveries  

📌 **Exam Signal:**  
Look for questions on **routing specific events based on content or multiple targets**, EventBridge rules handle this efficiently.

---

## ✅ 4. Schema Registry & Discovery

- Automatically discovers event schemas from event streams  
- Allows storing and versioning schemas in a **central schema registry**  
- Enables **code generation** for typed event bindings in popular programming languages  

📌 **Exam Signal:**  
If the question emphasizes **schema validation or generating code from event schemas**, EventBridge Schema Registry is the feature.

---

## ✅ 5. Reliability & Scalability

- Fully managed, **highly available and scalable** event bus  
- Supports **at-least-once delivery semantics**  
- Event archiving and replay capabilities for auditing and recovery  
- Event size up to 256 KB, supports batching to increase throughput  

📌 **Exam Signal:**  
If high availability, durability, or event replay is part of the scenario, EventBridge supports all these.

---

## ✅ 6. Security & Access Control

- Uses **IAM policies** to control event bus and rule permissions  
- Supports **resource-based policies** on event buses  
- Integrates with **AWS KMS** for encryption at rest  
- Events encrypted in transit via TLS  

📌 **Exam Signal:**  
Questions on securing event routing and controlling who can publish or consume events point to EventBridge’s IAM and encryption features.

---

## ✅ 7. Use Cases

| Use Case                | Explanation                                                   |
| ----------------------- | ------------------------------------------------------------- |
| Application integration | Connect decoupled microservices via events                    |
| SaaS integration        | Ingest SaaS events (e.g., Zendesk tickets) into AWS workflows |
| Automated workflows     | Trigger Lambda or Step Functions based on events              |
| Auditing & compliance   | Archive and replay events for audit trails                    |
| Real-time monitoring    | Route system and app events to monitoring tools               |

📌 **Exam Signal:**  
If the scenario involves **event-driven orchestration, SaaS-AWS integration, or event replay**, EventBridge is ideal.

---

## ✅ 8. Comparison with SNS & SQS

| Feature / Scenario           | EventBridge                        | SNS                        | SQS                            |
| ---------------------------- | ---------------------------------- | -------------------------- | ------------------------------ |
| Event routing with filtering | ✅ Advanced content-based filtering | No content filtering       | Message queueing, no filtering |
| Integration with SaaS apps   | ✅ Supports SaaS event sources      | No native SaaS integration | No native SaaS integration     |
| Delivery semantics           | At-least-once                      | At-least-once              | At-least-once                  |
| Event size limit             | 256 KB                             | 256 KB                     | 256 KB                         |
| Fan-out messaging            | ✅ Supports fan-out via rules       | ✅ Supports fan-out         | No fan-out, queue-based        |

📌 **Exam Signal:**  
Use **EventBridge** for event-driven app integration and SaaS event ingestion, **SNS** for pub/sub messaging, and **SQS** for message queuing.

---

# 🧠 Summary Table

| Scenario / Keyword                      | Amazon EventBridge Feature                         |
| --------------------------------------- | -------------------------------------------------- |
| Serverless event bus                    | ✅ Fully managed, scalable event routing            |
| Integrate SaaS and AWS events           | ✅ Supports SaaS event sources                      |
| Content-based event filtering           | ✅ Advanced filtering with event patterns           |
| Multiple targets and dead-letter queues | ✅ Route events to Lambda, SQS, SNS, Step Functions |
| Schema registry & code generation       | ✅ Schema discovery and registry                    |
| Event archiving and replay              | ✅ Archive and replay events                        |
| IAM-based security & KMS encryption     | ✅ Fine-grained access control and encryption       |

---

## 📚 Exam Focus

- Choose **Amazon EventBridge** when:  
  - You need a **serverless, fully managed event bus** for integrating AWS services, SaaS apps, and custom applications  
  - Your scenario requires **advanced, content-based event filtering and routing to multiple targets**  
  - You want **schema discovery, versioning, and code generation** for event-driven development  
  - You require **event archiving, replay, and at-least-once delivery guarantees**  
  - You need **fine-grained IAM-based security and encryption at rest/in transit**  
- Avoid EventBridge if:  
  - You want a simple pub/sub messaging system without advanced filtering → Use **SNS**  
  - You require a message queue with decoupling and message buffering → Use **SQS**

---
