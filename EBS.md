# 📘 Amazon EBS (Elastic Block Storage)

Amazon Elastic Block Store (EBS) provides **persistent, high-performance block storage volumes** for use with EC2 instances. EBS volumes behave like raw, unformatted block devices, ideal for databases, file systems, and workloads needing low-latency storage that persists independently of EC2 lifecycle.

---

## ✅ 1. When to Use EBS

**Scenario Keywords**  
- Block storage for EC2  
- Persistent storage for applications or databases  
- Needs low-latency storage with high performance  
- Data must persist after EC2 stop/start  

**Use Case**  
Use **EBS** when you need **block-level storage** attached to EC2 instances.

---

## ✅ 2. Volume Types and Performance Mapping

| EBS Volume Type      | Scenario                      | Key Metrics                          | Use Case                                  |
|----------------------|-------------------------------|---------------------------------------|--------------------------------------------|
| `gp3` (General SSD)  | Default, cost-effective SSD   | 3,000 IOPS baseline, up to 16,000     | Balanced workloads, boot volumes           |
| `io2` / `io2 Block Express` | High performance, critical DBs | Up to 256,000 IOPS, 99.999% durability | OLTP, SAP HANA, latency-sensitive apps     |
| `st1` (Throughput HDD) | Large, sequential workloads | 500 MB/s throughput                   | Big data, log processing                   |
| `sc1` (Cold HDD)     | Infrequent access             | Low throughput, lowest cost           | Archival, cold data                        |
| `gp2` (Legacy SSD)   | Replaced by `gp3`             | Scales with volume size               | Boot volumes, general workloads            |

**📌 Exam Signal**  
If **IOPS**, **throughput**, or **cost** is emphasized → match the volume type accordingly.

---

## ✅ 3. Snapshots (Backups & DR)

**Scenario Keywords**  
- Backup EBS volume  
- Copy data to another region  
- Automate backup  
- Restore volume from backup  

**Use Case**  
Use **EBS Snapshots** (stored in **S3**) for point-in-time backups and cross-region **disaster recovery**.

**📝 Exam Tip**  
- Snapshots are **incremental** after the first one  
- Use **Lifecycle Manager** to automate snapshot creation

---

## ✅ 4. Data Durability & Availability

- EBS volumes are designed for **99.999% availability**
- **Replicated within the same Availability Zone (AZ)**

**📌 Exam Signal**  
If **multi-AZ durability** is needed → **EBS is not multi-AZ by default**.  
Use **EFS** or **S3** for multi-AZ storage, or replicate snapshots manually.

---

## ✅ 5. Resizing and Modifying Volumes

**Scenario Keywords**  
- Increase volume size or IOPS  
- No downtime  
- Resize without stopping instance  

**Use Case**  
EBS volumes support **online resizing** (modify type, size, or IOPS **without downtime**).

---

## ✅ 6. Encryption

**Scenario Keywords**  
- Encrypt data at rest  
- Use KMS-managed keys  
- Compliance requirement  

**Use Case**  
Enable EBS encryption using **AWS KMS**. This encrypts:  
- Data at rest  
- Snapshots  
- Volumes created from snapshots

---

## ✅ 7. Performance Optimization

**Scenario Keywords**  
- EC2 is slow  
- High disk latency  
- Not meeting IOPS  

**Tips**
- Use **Provisioned IOPS (io2)** for consistent performance  
- Enable **Multi-Attach** (`io1`/`io2`) for cluster-aware applications  
- Choose **EBS-optimized EC2 instances**

---

## ✅ 8. Use with Other AWS Services

- **Auto Scaling Groups** → Use launch templates with EBS root volumes  
- **CloudFormation** → Automate EBS provisioning  
- **AWS Backup / DMS / Lambda** → Interact with EBS snapshots programmatically

---

## 🧠 Quick EBS Tips for Exam

| Feature             | Tip                                                                 |
|---------------------|----------------------------------------------------------------------|
| `gp3`               | Best general-purpose SSD (customizable IOPS & throughput)            |
| `io2`               | For critical apps needing high durability and performance            |
| `st1` / `sc1`       | Use for large, sequential, cost-sensitive workloads                  |
| Snapshots           | Stored in S3, **incremental**, supports **cross-region** copy       |
| Encryption          | Use **KMS**; encrypts data, snapshots, and restored volumes          |
| Performance tuning  | Resize volumes, switch to `io2` for higher IOPS                      |
| Durability          | Single AZ only – manually replicate for multi-AZ                     |
| Multi-Attach        | Only supported with `io1` and `io2` (for cluster-aware FS)           |
| Auto backup         | Use **Data Lifecycle Manager** to automate snapshots                 |

---

📚 **Exam Focus:**  
Focus on **EBS volume types** matching workload needs: gp3 for general use, io2/io2 Block Express for high-performance critical DBs, and HDD types (st1/sc1) for throughput or cost optimization. Remember **snapshots** are incremental and stored in S3. Know that EBS is **single AZ** storage and multi-AZ requires manual replication. Understand **online volume resizing** without downtime and **encryption with AWS KMS**. Watch for **Multi-Attach** feature on io1/io2 for clustered applications. Also, automation via **Lifecycle Manager** and **CloudFormation** is commonly tested.


