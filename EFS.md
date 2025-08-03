# 📘 Amazon EFS – Elastic File System

Amazon EFS is a **fully managed, scalable, elastic NFS** (Network File System) that allows you to **mount the same file system across multiple EC2 instances**. Ideal for shared, POSIX-compliant file storage with elastic capacity and high availability.

---

## ✅ 1. When to Use Amazon EFS

**Scenario Keywords**
- Shared file storage across multiple EC2s
- Linux-based workloads
- Dynamic scaling of storage
- Serverless access to files
- Durable and regional (multi-AZ) file system

**📌 Use Case**  
Use EFS when you need **shared, scalable storage** across instances in **multiple Availability Zones**, especially for:
- Web servers  
- CMS  
- Analytics jobs  
- Container-based apps  

---

## ✅ 2. Performance Modes & Throughput Modes

### 🌀 Performance Modes

| Mode            | Use When                  | Key Points                            |
|------------------|---------------------------|----------------------------------------|
| General Purpose | Most apps, web servers    | Low latency, general I/O (default)     |
| Max I/O         | Big data, large workloads | Higher latency, better scalability     |

### 🚀 Throughput Modes

| Mode          | Use When                       | Key Points                                |
|---------------|----------------------------------|--------------------------------------------|
| Bursting      | Default, cost-effective         | Scales with size, uses burst credits       |
| Provisioned   | Steady high throughput needed   | Decouples IOPS from size                   |

**📌 Exam Signal**  
- **Low-latency / web apps** → General Purpose  
- **Big data / many clients** → Max I/O  

---

## ✅ 3. Storage Classes

| Storage Class          | Key Use Case              | Durability           | Cost       |
|------------------------|---------------------------|----------------------|------------|
| EFS Standard           | Frequently accessed files | 99.999999999%        | Higher     |
| EFS Infrequent Access  | Rarely accessed files     | Same as Standard     | ~92% lower |
| EFS Lifecycle Mgmt     | Auto-tiering to IA        | Configurable (7–90d) | Cost saver |

**🧠 Exam Tip**:  
EFS uses **Lifecycle Policies** for automatic tiering like **S3**.

---

## ✅ 4. Access Patterns

**Scenario Keywords**
- Multi-AZ
- Shared access
- Multiple EC2s
- Serverless compute

**Supported Access**
- **EC2** via **mount targets**
- **ECS/Fargate** via **EFS volumes**
- **Lambda** using **EFS integration** (for large files)

---

## ✅ 5. Security and Encryption

**Scenario Keywords**
- Encrypt data at rest
- Compliance requirements
- VPC-level access

**Security Features**
- **Encryption at rest** using **KMS**
- **Encryption in transit** using **TLS**
- **POSIX permissions** for file-level control
- Controlled by **Security Groups** + **NFS rules**
- **IAM Policies** for API access control

---

## ✅ 6. Backup and Durability

- **Automatically stored across multiple AZs**
- **AWS Backup** supports managed backups
- **Durable and HA** by default
- **Linux-only** (not compatible with Windows)

---

## ✅ 7. Pricing Considerations

- **Pay per GB** used in each storage class  
- **Provisioned throughput** adds extra cost  
- **Lifecycle policy** reduces cost via IA tiering  
- Great for **large shared files** without needing block storage

---

## 🧠 Quick EFS Tips for Exam

| Feature             | Tip                                                        |
|---------------------|------------------------------------------------------------|
| Shared storage       | Mount on multiple EC2s using NFS                          |
| Elastic scaling      | Automatically expands and shrinks                        |
| Storage classes      | Standard (frequent) vs IA (cost-saving)                  |
| Lifecycle management | Auto-transition to IA after 7–90 days                    |
| Encryption           | KMS (at rest), TLS (in transit)                          |
| Durability           | Multi-AZ, regional by default                            |
| Performance          | General Purpose (default), Max I/O (scalable)            |
| Throughput           | Bursting (default), Provisioned (manual)                 |
| Lambda access        | Supported for large payloads                             |
| Mount targets        | Required per AZ for EC2                                  |
| Use case match       | Big data, CMS, analytics, web apps                       |
| OS support           | **Linux-only**, POSIX-compliant                          |

---

📚 **Exam Focus**: Watch for keywords like **multi-AZ**, **POSIX**, **shared access**, or **elastic scaling**—they almost always point to EFS as the right answer.

