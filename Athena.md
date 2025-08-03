# 📘 Amazon Athena – Serverless SQL for S3 Data

Amazon Athena is a **fully managed, serverless SQL query service** that makes it easy to analyze data directly in Amazon S3 using standard SQL. It uses Presto under the hood, supports structured/semi-structured formats (Parquet, JSON, ORC, CSV), and works seamlessly with the AWS Glue Data Catalog.

---

## ✅ 1. When to Use Amazon Athena

**Scenario Keywords:**

- Query S3 data using SQL
- Ad-hoc analysis, serverless querying
- No ETL or data movement
- Query logs (CloudTrail, ELB, VPC, etc.)
- Federated queries (RDS, Redshift, etc.)
- Visualize in Power BI, QuickSight, Tableau
- Reduce cost with Parquet/ORC
- Build dashboards or BI reports from S3

**Use Case:**  
Use Athena when you want to run SQL queries directly on data in S3 without setting up infrastructure. Great for data exploration, quick analysis, dashboarding, and log analytics.

---

## ✅ 2. Core Components

| Component            | Purpose                                                                 |
|----------------------|-------------------------------------------------------------------------|
| **Athena Query Engine** | Executes SQL queries on data stored in S3 using Presto                   |
| **Glue Data Catalog**   | Stores schema and metadata used by Athena for table definitions          |
| **Workgroups**          | Manage user-level query access, cost control, and separation             |
| **CTAS (Create Table As)** | Save query results as new optimized tables (e.g., Parquet)             |
| **UDFs with Lambda**    | Extend SQL capabilities using custom functions via AWS Lambda            |
| **Apache Iceberg**      | Transactional table format supporting updates, deletes, time travel     |
| **Athena Notebooks**    | Jupyter-like interface with Spark backend for interactive analysis       |

---

## ✅ 3. Typical Use Cases

| Use Case               | Description                                                        |
|------------------------|--------------------------------------------------------------------|
| Query S3 directly      | Ad-hoc analysis of raw or partitioned data in S3                   |
| BI Dashboard backend   | Power BI, QuickSight, Tableau data source                          |
| Log analysis           | CloudTrail, ELB, VPC logs stored in S3                             |
| Schema-on-read         | Read structured/semi-structured data without ingestion             |
| Federated query        | Join/query data across S3, RDS, DynamoDB, Redshift, and external JDBC |
| Schema evolution / rollback | Use Apache Iceberg for ACID-compliant versioned tables          |
| Transform data in-place | Use CTAS to convert CSV → Parquet / ORC                            |

---

## ✅ 4. Optimization Strategies

**Scenario Keywords:** Reduce cost, improve performance, partitioned data, large-scale analytics

| Optimization         | Description                                                    |
|----------------------|----------------------------------------------------------------|
| Partitioning         | Filter data early using partitioned columns (e.g., date, region) |
| Use Parquet/ORC      | Columnar and compressed = less data scanned, faster queries     |
| CTAS for performance | Create optimized summary tables in compressed format            |
| Query Result Reuse   | Enable to avoid scanning same data again                         |
| Workgroups with limits | Set per-user query cost control                                 |

---

## ✅ 5. Integration Points

| Service             | Integration                                                       |
|---------------------|------------------------------------------------------------------|
| Amazon S3           | Primary data source for all Athena queries                       |
| AWS Glue Catalog    | Stores schema metadata used in Athena queries                    |
| Amazon QuickSight   | Direct visualization of Athena query results                     |
| RDS / Redshift      | Access via Federated Query connectors                            |
| Amazon Lambda       | UDFs to extend Athena with custom logic (e.g., geocoding, sentiment scoring) |
| CloudTrail, VPC Logs | Analyze logs in S3 using Athena with prebuilt schemas            |
| Apache Iceberg      | Time travel, updates, deletes, transactional tables              |

---

## ✅ 6. Cost Optimization

- Pricing: **$5 per TB scanned** — use compression + partitioning to save.
- CTAS: Store optimized query results for repeat use (e.g., dashboards).
- Column projection: Only select necessary fields to reduce scan size.
- **Avoid SELECT ***: Explicitly select required columns.
- Enable result reuse: Skip re-running unchanged queries.

---

## 🧠 Quick Athena Tips for Exam

| Feature                 | Tip                                                        |
|-------------------------|------------------------------------------------------------|
| Serverless SQL          | No infrastructure to manage                                |
| Pay per TB scanned      | Optimize with Parquet, partitions                           |
| Use with Glue Data Catalog | Glue holds table definitions + partitions                  |
| CTAS                    | Used to transform, convert, or summarize data              |
| Workgroups              | For cost monitoring and access control                      |
| Federated Query         | Query RDS, Redshift, or JDBC sources via Athena             |
| Supports JSON/CSV/Parquet/ORC | Choose best format based on performance and structure     |
| Iceberg Format          | ACID operations (updates/deletes) and time travel          |
| Partition Pruning       | Use WHERE on partition column to limit scanned data        |
| Lambda UDFs             | Extend SQL logic with custom Python code                    |
| Analyze logs (e.g., CloudTrail) | Predefined schemas help simplify querying of structured logs |
| Athena Notebooks (Spark) | Interactive data exploration + visualization using Spark SQL |

