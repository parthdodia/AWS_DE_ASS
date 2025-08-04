# 📘 AWS CLI – Command Line Interface for Managing AWS Resources

The AWS CLI enables you to manage AWS services directly from the terminal. It's widely used for automation, quick task execution, and scripting—especially valuable for DevOps and Data Engineering workflows.

---

## ✅ 1. General AWS Resource Management

- Use commands like: `aws <service> <operation> [parameters]`
- Supports **create**, **update**, **delete**, and **read** actions on resources
- Output formats: **JSON**, **text**, or **table**

📌 **Exam Signal:**  
When a question describes **one-liner commands**, **scripts**, or **quick resource interaction**, the answer is likely **AWS CLI**.

---

## ✅ 2. Authentication and Configuration

- Setup via: `aws configure` (access key, secret key, default region, output format)
- Stores credentials at `~/.aws/credentials`
- Supports **named profiles** for multi-account usage

📌 **Exam Signal:**  
If switching accounts or managing credentials in scripts is part of the scenario, mention **named profiles or environment variables** with the CLI.

---

## ✅ 3. Common Data Engineering Use Cases

| Task                        | CLI Command Example |
|-----------------------------|---------------------|
| Upload to S3                | `aws s3 cp file.csv s3://bucket/` |
| Run Athena query            | `aws athena start-query-execution` |
| Trigger a Glue job          | `aws glue start-job-run --job-name` |
| Create an EMR cluster       | `aws emr create-cluster --name` |
| List Kinesis streams        | `aws kinesis list-streams` |
| Start Step Function         | `aws stepfunctions start-execution` |

📌 **Exam Signal:**  
If the scenario includes **S3, Athena, Glue, EMR**, or **Step Functions**, used programmatically, expect **CLI or SDK**.

---

## ✅ 4. Automation and Scripting

- Used in **shell scripts**, **CI/CD**, **cron jobs**, and **batch pipelines**
- Can be combined with tools like `jq` for JSON parsing

📌 **Exam Signal:**  
For automation, especially **scheduled jobs**, CLI is the go-to tool.

---

## ✅ 5. CLI vs SDK vs Console

| Scenario                        | AWS CLI       | SDK (Boto3, etc.) | AWS Console   |
|--------------------------------|---------------|-------------------|---------------|
| Quick command-line task        | ✅ Best Fit    | ❌ Too heavy       | 🔶 Possible    |
| Integrate with app code        | ❌ Not suitable| ✅ Best Fit        | ❌ Not suitable|
| Visualize resources            | ❌             | ❌                 | ✅ Best Fit    |
| Cross-platform scripting       | ✅             | ✅                 | ❌             |

📌 **Exam Signal:**  
If you need **lightweight execution or scripting**, pick **AWS CLI** over SDK or Console.

---

## ✅ 6. Advanced Features

- **Waiters:** Automate waiting for a resource to reach a certain state  
  e.g., `aws ec2 wait instance-running --instance-ids i-xxxx`
- **Pagination:** Handle large data sets  
  e.g., `--page-size`, `--starting-token`
- **Filters:** Narrow results based on tags or attributes  
  e.g., `--filters Name=tag:Env,Values=prod`

📌 **Exam Signal:**  
If a scenario involves **waiting for resource states**, or **filtered queries**, use **Waiters** and **Filters** in CLI.

---

## 🧠 Summary Table

| Scenario / Keyword            | AWS CLI Feature / Concept              |
|-------------------------------|----------------------------------------|
| Scripting & automation        | CLI in Bash, cron, CI/CD               |
| Multi-account config          | Named Profiles, `~/.aws/config`        |
| Infra from terminal           | `aws ec2`, `aws s3`, etc.              |
| Query data tools (Athena, Glue) | `start-query-execution`, `start-job-run` |
| Monitor resource state        | **Waiters**                            |
| Paginate/Filter results       | `--page-size`, `--filters`             |
| Trigger data workflows        | Use with Step Functions, Lambda, etc.  |
| Lightweight task automation   | Use CLI over SDK for small jobs        |

---

## 📚 Exam Focus

### ✅ When to Choose AWS CLI:
- The scenario involves **command-line resource operations**
- You need to **script tasks** or automate jobs in **cron**, **CI/CD**, or **bash**
- Working with **multiple AWS accounts or profiles**
- You need a **lightweight** tool instead of a full SDK

### ❌ When *Not* to Choose AWS CLI:
- If infrastructure is defined as **code (IaC)** → Use **CloudFormation, CDK, or Terraform**
- If it's a **visual task** or **UI-based management** → Use **AWS Console**
- If deeply **integrated with application logic** → Use **AWS SDKs** (e.g., Boto3)

---
