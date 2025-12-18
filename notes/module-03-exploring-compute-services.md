# Module 3 – Exploring Compute Services (AWS Cloud Practitioner Essentials)

## Review (Quick refresher)
Goal of this module: learn compute options beyond EC2 and how to choose the right one.

---

## MODULE 3 INTRODUCTION
### Introduction to Serverless Computing
**Serverless =** you don’t manage servers; AWS manages provisioning/scaling/availability.
You still manage:
- your code
- config (permissions, environment variables)
- triggers/integrations

**Why it matters:**
- faster time-to-value
- auto-scaling by default
- pay for usage (not idle capacity)

**Good fit:**
- event-driven workloads
- unpredictable/spiky traffic
- automation & “glue” tasks

**Not ideal when:**
- you need full OS control
- long-running jobs (use containers/EC2/Batch)

---

## AWS SERVERLESS, CONTAINERS, AND SOLUTIONS OVERVIEW

### AWS Lambda
**What it is:** event-driven compute that runs your code when triggered.

**Common triggers (high yield):**
- API calls (API Gateway)
- S3 object upload
- scheduled events (EventBridge)
- DynamoDB streams

**Best for:**
- lightweight APIs
- file processing (resize images, convert formats)
- automation (cleanup jobs, notifications)
- event-driven pipelines

**Core ideas:**
- stateless by default (store state in S3/DynamoDB/RDS/etc.)
- scales automatically (concurrency is the key scaling word)
- permissions via IAM roles

---

### Containers and Orchestration on AWS
**Containers =** package app + dependencies consistently.

**Orchestration =** system that schedules/runs/maintains containers (health checks, scaling, networking).

#### ECS (Elastic Container Service)
- AWS-native container orchestrator
- simpler ops than Kubernetes for most teams
- runs containers on **EC2** or **Fargate**

#### EKS (Elastic Kubernetes Service)
- managed Kubernetes control plane
- best when you *must* use Kubernetes

#### Fargate (Serverless Containers)
- run containers without managing EC2 hosts
- works with ECS or EKS
- strong fit for “containers without the ops overhead”

**Quick decision rule:**
- Want containers, AWS-native, simpler → **ECS**
- Want Kubernetes specifically → **EKS**
- Want containers but no servers → **Fargate**

---

### Additional Compute Services
#### Elastic Beanstalk (PaaS)
- deploy web apps easily
- AWS provisions infra (EC2, load balancer, autoscaling) under the hood
- you focus on the application and deployment

**Best for:** “I want to deploy a web app fast without building the infrastructure manually.”

#### Lightsail
- simplified VPS-style compute with predictable pricing
- great for simple websites, small apps, WordPress, prototypes

**Best for:** quick/simple hosting where you don’t need full AWS complexity.

#### AWS Batch
- batch job scheduling + compute provisioning
- best for queued jobs and large-scale background processing

**Best for:** “run 10,000 jobs from a queue and scale compute to match.”

(Optional if your module mentions it:)
#### AWS Outposts / Wavelength
- Outposts: AWS hardware in your on-prem data center
- Wavelength: AWS compute at the edge (low latency 5G scenarios)

---

## MODULE 3 CONCLUSION
### Assessment prep (flash prompts)
- When would you choose **Lambda** vs **EC2**?
- When would you choose **ECS/Fargate** vs **EKS**?
- When would you choose **Beanstalk** vs **EC2**?
- When would you choose **Lightsail** instead of “full AWS”?

### Module Summary
- Serverless: no servers to manage, pay per use
- Lambda: event-driven functions
- Containers: ECS/EKS, Fargate removes server management
- Extra compute options: Beanstalk, Lightsail, Batch (plus edge/hybrid if covered)
