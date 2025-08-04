# 📘 AWS Cloud Development Kit (CDK) – Infrastructure as Code with Real Programming Languages

AWS CDK lets you define AWS infrastructure using familiar programming languages like Python, TypeScript, Java, etc., which compile into CloudFormation templates for deployment. It's powerful for teams that need programmatic flexibility and reusable infrastructure components.

---

## ✅ 1. Imperative Infrastructure as Code

- Define infrastructure using **actual code** (Python, TypeScript, Java, etc.)
- Supports **loops, conditionals, environment variables**, and modular logic
- Compiles code into **CloudFormation templates** behind the scenes

📌 **Exam Signal:**  
Choose CDK when the scenario calls for **code logic**, **reusability (DRY)**, or **dynamic infrastructure**.

---

## ✅ 2. CDK Constructs and Stacks

- **Constructs:** Core building blocks (single or grouped resources)  
- **Stacks:** A unit of deployment (mapped to CloudFormation stack)  
- **Apps:** Group of stacks for multi-environment or multi-region deployments

📌 **Exam Signal:**  
If a question refers to **modular or reusable architecture**, answer with **Constructs and Stacks** in CDK.

---

## ✅ 3. Language Support

- CDK supports **Python, TypeScript, Java, C#, Go**
- Same features across all supported languages

📌 **Exam Signal:**  
Use CDK when a developer team prefers to write **IaC in their preferred language** (e.g., Python or TS).

---

## ✅ 4. CDK Bootstrapping & Deployment

- Requires `cdk bootstrap` for initial setup  
- CLI commands:
  - `cdk deploy` – deploy stack  
  - `cdk diff` – show changes before deploying  
  - `cdk destroy` – delete deployed resources  

📌 **Exam Signal:**  
CLI commands like `cdk diff`, `cdk deploy`, or **bootstrapping** clearly indicate **CDK usage**.

---

## ✅ 5. Constructs Library (L1–L3)

| Level | Description | Example |
|-------|-------------|---------|
| L1    | Low-level, raw CloudFormation resources | `CfnBucket` |
| L2    | AWS-managed with defaults & simplified APIs | `Bucket`, `Function` |
| L3    | Patterns combining best practices | `LambdaRestApi`, `FargateService` |

📌 **Exam Signal:**  
If the scenario refers to **abstractions, productivity, or best practices**, it’s about **L2 or L3 Constructs**.

---

## ✅ 6. CDK vs CloudFormation vs Terraform

| Feature                        | CDK           | CloudFormation | Terraform     |
|-------------------------------|---------------|----------------|---------------|
| Imperative IaC (loops, logic) | ✅ Yes         | ❌ No          | ✅ Yes (HCL)   |
| AWS-native coverage           | ✅ Deepest     | ✅ Deepest     | 🔶 Slight lag |
| Reusability & abstraction     | ✅ Constructs  | 🔶 Limited     | ✅ Modules     |
| Multi-cloud support           | ❌ AWS only    | ❌ AWS only    | ✅ Yes         |

📌 **Exam Signal:**  
Pick CDK when:
- You need **imperative programming** with logic  
- You want to use **constructs for reusability**  
- You’re **deploying on AWS only**

---

## 🧠 Summary Table

| Scenario / Keyword              | CDK Feature / Concept              |
|---------------------------------|------------------------------------|
| Use Python or TS for IaC        | Language-based IaC support         |
| Don’t Repeat Yourself (DRY)     | Constructs                         |
| Multiple deployments/environments | CDK Apps + Stacks                 |
| Preview infra updates           | `cdk diff`                         |
| Imperative logic (if, loop)     | Full programming support           |
| Underlying CloudFormation       | Synthesized YAML output            |
| Pre-built infra best practices  | L3 Constructs                      |
| Lifecycle control               | `cdk deploy`, `cdk destroy`, etc.  |

---

## 📚 Exam Focus

### ✅ When to Choose AWS CDK:
- You need **code-driven infrastructure** with **logic and loops**
- You want **reusable**, **modular components** via Constructs
- Your team prefers using **Python, TS, or Java** for IaC
- You require **previewing changes** (`cdk diff`) before deploy
- You’re building **AWS-only** infrastructure with **CI/CD integration**

### ❌ When *Not* to Choose CDK:
- You require **multi-cloud** infrastructure → Use **Terraform**
- You want **simple, declarative templates** without code → Use **CloudFormation**
- You don’t want to manage language environments or installations → CloudFormation may be simpler

---
