# Module 3 – Exploring Compute Services (AWS SAA)

## What “Compute Services” Means (SAA lens)
Compute services are the different ways AWS runs your code:
- **Servers (VMs):** EC2
- **Containers:** ECS / EKS (often with Fargate)
- **Serverless functions:** Lambda
- **Platform-managed apps:** Elastic Beanstalk / App Runner
- **Simplified VM bundles:** Lightsail
- **Batch workloads:** AWS Batch

High-yield goal: pick the *right* compute for the workload + tradeoffs.

---

## Decision Cheat Sheet (Pick the Service Fast)
- Need **full OS control / custom installs / legacy app** → **EC2**
- Need **run code on events** (S3 upload, API call) → **Lambda**
- Need **containers** but want AWS-managed orchestration → **ECS**
- Need **Kubernetes** specifically → **EKS**
- Want **no servers to manage for containers** → **Fargate** (with ECS/EKS)
- Want **PaaS “deploy app, AWS runs it”** → **Elastic Beanstalk**
- Want **simple hosting** (small apps, WordPress, quick VM+DB) → **Lightsail**
- Need **massive batch jobs / queues / scheduled compute** → **AWS Batch**

---

## AWS Lambda (Serverless Functions)
**What it is:** Run code without managing servers. Trigger-based execution.
**Best for:**
- Event-driven tasks (S3 events, DynamoDB streams, EventBridge schedules)
- Short-running APIs (often behind API Gateway)
- Automation / glue code / lightweight ETL

**Key concepts (SAA):**
- You pay per execution + duration (and memory setting affects CPU)
- Stateless by default (use S3/DynamoDB/RDS/etc for state)
- Concurrency matters (throttling + scaling behavior)
- Typical pattern: API Gateway → Lambda → DynamoDB

**When NOT to use:**
- Long-running jobs (better: ECS/Fargate/Batch/EC2)
- Apps requiring heavy local state or specialized networking needs

---

## Containers Overview (Why Containers)
Containers package your app + dependencies consistently.
Core choices:
- **ECS** (AWS-native orchestrator)
- **EKS** (Kubernetes orchestrator)
- **Fargate** (serverless compute engine for containers)

---

## Amazon ECS (Elastic Container Service)
**What it is:** AWS-managed container orchestration (no Kubernetes required).
**Best for:**
- Containerized microservices
- Teams that want “AWS way” without K8s complexity

**Key concepts (SAA):**
- Runs tasks/services on **EC2** or **Fargate**
- Integrates with ALB, IAM, CloudWatch, ECR
- Easier operational overhead vs EKS

---

## Amazon EKS (Elastic Kubernetes Service)
**What it is:** Managed Kubernetes control plane on AWS.
**Best for:**
- Standardizing on Kubernetes
- Portability / K8s ecosystem (Helm, operators, etc.)

**Key concepts (SAA):**
- Control plane managed; worker nodes on EC2 or Fargate
- More flexibility + more complexity than ECS
- IAM + Kubernetes RBAC is a common security theme

---

## AWS Fargate (Serverless Containers)
**What it is:** Run containers without managing EC2 instances.
**Best for:**
- When you want containers but don’t want to manage servers/cluster capacity
- Spiky workloads, small teams, fast deployment

**Key concepts (SAA):**
- Works with ECS or EKS
- Pay for resources used (task-level)
- Less low-level control, less ops work

---

## Elastic Beanstalk (PaaS)
**What it is:** Deploy an application; AWS provisions EC2, LB, Auto Scaling, etc.
**Best for:**
- “I want to deploy my web app quickly” without building infra manually
- Common runtimes: Node, Python, Java, .NET, etc.

**Key concepts (SAA):**
- You still pay for underlying resources (EC2, ALB, etc.)
- Beanstalk handles deployment + scaling config patterns
- Great for getting moving fast; less control than custom infra

---

## Amazon Lightsail
**What it is:** Simplified VPS-style hosting with predictable pricing.
**Best for:**
- Simple websites, small apps, quick WordPress
- Learning, prototypes, low-complexity production workloads

**Key concepts (SAA):**
- “Easy button” experience vs building VPC + EC2 + networking yourself
- Limited compared to full EC2 ecosystem

---

## AWS Batch
**What it is:** Batch job scheduling and compute provisioning.
**Best for:**
- Large-scale batch processing (data processing, simulations)
- Queue-based compute that runs when resources are available

**Key concepts (SAA):**
- Uses EC2 and/or Fargate under the hood
- Works well with job queues + compute environments
- Often paired with S3 for input/output data

---

## Exam Patterns (SAA “tell” words → answer)
- “Event-driven”, “trigger on upload”, “run code when…” → **Lambda**
- “Microservices in containers, want AWS-managed orchestration” → **ECS**
- “Must use Kubernetes” → **EKS**
- “Don’t manage servers for containers” → **Fargate**
- “Deploy web app quickly, managed platform” → **Elastic Beanstalk**
- “Simple VPS + predictable price” → **Lightsail**
- “Many jobs in a queue / scheduled batch processing” → **Batch**
- “Need OS-level control / custom networking / legacy app” → **EC2**
