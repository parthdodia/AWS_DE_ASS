# 📘 AWS Backup – Centralized Backup Service
 
AWS Backup is a **fully managed, policy-based backup service** that helps **centralize and automate backups** across AWS services and some on-premises systems. It simplifies **compliance**, automates **scheduling**, and supports **disaster recovery** and **auditing** at scale.

---

## ✅ 1. When to Use AWS Backup

**Scenario Keywords**
- Centralized backup solution
- Compliance and retention policies
- Automate backup schedules
- Restore at a later time
- Cross-region or cross-account backup
- Audit backup activity

**📌 Use Case**  
Use AWS Backup when you need **centralized, automated, and compliant backups** across AWS services like **RDS, EFS, DynamoDB, EC2 volumes**—all managed through **policies, not scripts**.

---

## ✅ 2. Supported Services

| Service                        | Notes                                     |
|-------------------------------|-------------------------------------------|
| Amazon EFS                    | Full support for backup/restore           |
| Amazon RDS                    | Works with snapshots                      |
| Amazon DynamoDB               | PITR and backup without performance hit   |
| Amazon EC2 (EBS Volumes)      | Snapshot-based backups                    |
| Amazon FSx                    | Fully supported                           |
| Amazon S3                     | ❌ Not natively supported!                |
| On-prem (via Storage Gateway) | Use backup gateway or VM agent            |

> 📝 **Exam Tip**: **S3 is not directly supported** — this is a common **trick question**!

---

## ✅ 3. Key Components

| Component               | Description                                                        |
|-------------------------|--------------------------------------------------------------------|
| **Backup Plan**         | Defines schedule, lifecycle, and backup rules                     |
| **Backup Vault**        | Encrypted logical container to store backups                      |
| **Resource Assignments**| Link AWS resources to a plan using tags or direct selection        |
| **Lifecycle Rules**     | Move backups to cold storage or auto-expire                       |
| **Cross-Region/Account**| Enable disaster recovery or compliance backups                     |
| **Tags**                | Automate backup assignment and selection                          |

---

## ✅ 4. Retention, Cold Storage & Lifecycle

| Lifecycle Stage | Meaning                                                     |
|------------------|-------------------------------------------------------------|
| **Warm Storage** | Default for new backups                                     |
| **Cold Storage** | Lower cost, delayed deletion possible                       |
| **Expiration**   | Auto-delete backups after the defined retention period      |

> 🔐 All backups are **encrypted with AWS KMS**. You can assign a custom key per **backup vault**.

---

## ✅ 5. Backup Vault Access & Security

**Scenario Keywords**
- Prevent deletion
- Protect backups
- Cross-account access
- Audit access

**Security Features**
- **Vault Lock**: Prevents deletion (even by root); ensures immutability  
- **IAM + KMS policies**: Control who can access or restore backups  
- **AWS CloudTrail**: Logs all backup and restore operations for auditing

---

## ✅ 6. Monitoring & Recovery

- **Backup and restore jobs are logged**
- **CloudWatch metrics and alarms** supported
- **Point-in-time restore (PITR)** available for DynamoDB
- Restore backups via **console**, **CLI**, or **SDK**

---

## 🧠 Quick AWS Backup Tips for Exam

| Feature                 | Tip                                                   |
|--------------------------|--------------------------------------------------------|
| Centralized backup       | Across AWS services (not S3)                          |
| Policy-driven            | Use **Backup Plans** with schedules & lifecycle rules |
| Cold storage             | Lower cost, but delayed deletion                      |
| Vault Lock               | Immutable backups, even root can’t delete             |
| Cross-account/region     | For DR and compliance                                 |
| EFS, RDS, DynamoDB       | Fully supported                                        |
| **S3 NOT supported**     | Trick question—don’t fall for it!                     |
| KMS encryption           | Default for backups at rest                           |
| Audit-ready              | CloudTrail integration logs all actions               |
| Tag-based selection      | Automate backup assignments                           |
| Lifecycle policies       | Warm ➝ Cold ➝ Expire                                  |
| PITR support             | Only for **DynamoDB**                                 |

---

📚 **Exam Focus**: Watch for terms like **cross-account backup**, **Vault Lock**, **policy-driven backup**, or **lifecycle transitions**. When S3 is mentioned—**double-check**—it’s **not** supported natively by AWS Backup!

