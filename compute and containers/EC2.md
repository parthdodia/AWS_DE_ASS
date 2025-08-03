# 📘 Amazon EC2 – Elastic Compute Cloud

Amazon EC2 provides **resizable compute capacity in the cloud**, used to run virtual machines (instances) in a highly configurable and scalable environment.

---

## ✅ 1. Instance Types & Use Cases

* **General Purpose (t4g, t3, m6i):** Balanced CPU/memory, e.g., web servers  
* **Compute Optimized (c6g, c7i):** High-performance compute tasks (e.g., batch processing, ETL jobs)  
* **Memory Optimized (r7g, x2idn):** In-memory databases, large analytics workloads  
* **Storage Optimized (i4i, d3):** High-speed local storage for heavy read/write (e.g., big data)  
* **Accelerated Computing (p4, inf2):** ML inference/training, GPU tasks  

**📌 Exam Signal:**  
Look for clues around **ETL, real-time analytics, Spark, Hadoop** → use **Compute/Storage-Optimized EC2**.

---

## ✅ 2. Purchasing Options

* **On-Demand:** Pay per second; no long-term commitment  
* **Reserved Instances:** 1- or 3-year commitment for steady-state usage  
* **Spot Instances:** Up to 90% cheaper; ideal for **fault-tolerant, interruptible workloads**  
* **Savings Plans:** Flexible pricing across instance families  

**📌 Exam Signal:**  
Choose **Spot** for **cost-optimized batch jobs**, **On-Demand** for **short-term or unpredictable workloads**, and **Reserved** for **consistent usage**.

---

## ✅ 3. Auto Scaling & Elastic Load Balancing

* **Auto Scaling Groups (ASG):** Automatically scale in/out EC2 instances based on policies  
* **Elastic Load Balancer (ELB):** Distributes incoming traffic across EC2 fleet  
* Combine with CloudWatch metrics for dynamic scaling  

**📌 Exam Signal:**  
Scenarios needing **resiliency, high availability, or load balancing** point to **ASG + ELB**.

---

## ✅ 4. Storage Options with EC2

* **EBS (Elastic Block Store):** Persistent, attachable storage per instance  
  * gp3 → General-purpose SSD  
  * io2 → High-performance SSD for IOPS-intensive workloads  
* **Instance Store:** Ephemeral, high-speed storage tied to instance lifecycle  
* **EFS (Elastic File System):** Managed NFS file storage (shared)  
* **FSx / S3:** For complex or shared data scenarios  

**📌 Exam Signal:**  
Use **EBS gp3** for general use, **io2** for heavy IOPS, and **Instance Store** for **temporary scratch space** (e.g., Spark shuffle).

---

## ✅ 5. Networking & Security

* Each instance resides in a **VPC subnet**, assigned private/public IP  
* **Security Groups:** Virtual firewalls to control inbound/outbound rules  
* **IAM roles for EC2:** Attach roles to allow access to S3, DynamoDB, etc.  
* Use **Elastic IPs** for fixed external addresses  
* **Placement Groups** for low-latency/high-throughput networking between instances  

**📌 Exam Signal:**  
If access control or VPC/subnet/network placement is discussed → focus on **Security Groups + IAM Roles + Placement Strategies**.

---

## ✅ 6. EC2 User Data & Bootstrap

* **User data scripts** (shell/Python) run at first boot for setup/configuration  
* Used for installing agents, setting environment, configuring apps  

**📌 Exam Signal:**  
If instance **initialization or automation** is mentioned → use **User Data**.

---

## ✅ 7. Monitoring, Logging & Cost Optimization

* **CloudWatch** for metrics (CPU, disk, network), alarms, dashboards  
* **CloudTrail** for API activity auditing  
* **Trusted Advisor & Cost Explorer** for optimization  
* Rightsize EC2, schedule idle shutdowns  

**📌 Exam Signal:**  
If the question involves **monitoring performance or reducing unused capacity**, use **CloudWatch + Trusted Advisor**.

---

## ✅ 8. Use Cases for Data Engineers

| Scenario / Task                           | EC2 Application                                |
| ----------------------------------------- | ---------------------------------------------- |
| Big data processing (e.g., Spark, Hadoop) | Compute/Storage Optimized EC2 with Spot or ASG |
| ETL job runners or schedulers             | EC2 with CloudWatch or Step Functions          |
| Real-time analytics or ingestion          | EC2 + Kafka / Flink, use ENA networking        |
| Custom ingestion pipelines                | EC2 running custom agents / scripts            |
| Host dbt, Airflow, or self-managed tools  | EC2 + EBS + IAM + Security Groups              |

**📌 Exam Signal:**  
When full control of environment or high customization is required, EC2 is preferred over managed services.

---

## ✅ 9. EC2 vs Related Services

| Need / Scenario                     | Use ?           | 
| ----------------------------------- | ------------------ | 
| Full control of OS and dependencies | ✅ EC2              |                
| Simple microservices                | ❌ Consider Lambda  |                  
| Managed orchestration               | ❌ Consider ECS/EKS |                
| Stateless, event-driven logic       | ❌ Use Lambda       |                 
| Managed big data processing         | ❌ Use EMR or Glue  |                 

---

# 🧠 Summary Table

| Scenario / Keyword                | EC2 Feature / Option                    |
| --------------------------------- | --------------------------------------- |
| Custom batch processing           | EC2 Compute/Storage Optimized Instances |
| Cost optimization for jobs        | Spot Instances / Auto Scaling           |
| Initialization automation         | EC2 User Data                           |
| Instance persistence & IOPS       | EBS gp3 / io2                           |
| Temporary scratch data            | Instance Store                          |
| Access control & permissions      | IAM Roles + Security Groups             |
| Big data frameworks (e.g., Spark) | EC2 (possibly on EMR)                   |
| Long-running analytics pipelines  | EC2 with monitoring + scaling           |

---

## 📚 Exam Focus

- Choose **Amazon EC2** when:  
  - You need **custom compute environments** with full control over OS, storage, and networking  
  - Your workloads require **complex setup, custom agents, or third-party dependencies**  
  - You are running **Spark, Kafka, Hadoop**, or **big data pipelines** not suited for managed services  
  - You want **dedicated instances** with **low-level access** (e.g., GPU, specialized networking)  
  - You need **flexible pricing models** (e.g., Spot for batch jobs, Reserved for steady-state)  
  - You want to host **open-source or self-managed orchestration tools** like Airflow or dbt  
- Avoid EC2 if:  
  - You prefer **fully managed compute environments** → Use **Lambda, ECS, or EKS**  
  - You want **serverless, event-driven execution** → Use **Lambda**  
  - Your job fits into **ETL/ELT patterns with managed connectors** → Use **Glue or Data Pipeline**

---
