# Module 2 — Compute in the Cloud (AWS SAA)

## What “Compute” Means
Compute = the resources that run your applications and workloads.
In AWS, compute ranges from virtual servers to containers to serverless functions.

---

## Core AWS Compute Options (High Yield)

### EC2 (Elastic Compute Cloud)
**What it is:** Virtual machines in the cloud.  
**Best for:**
- Full control of OS/runtime
- Custom software installs
- Lift-and-shift workloads
- Steady workloads (especially with Reserved Instances/Savings Plans)

**Key concepts:**
- Instance types = optimized for different needs (general, compute, memory, storage)
- AMI = template for launching instances
- Security Groups = instance-level firewall
- Placement in a VPC + subnet (public/private)

**Exam mindset:** If you need control of the OS or “a server,” EC2 is usually the answer.

---

### Auto Scaling (ASG)
**What it is:** Automatically adjusts the number of EC2 instances based on demand/health.  
**Why it matters:** High availability + cost efficiency.

**Common setup:**
- Launch Template/Config
- Min / Desired / Max capacity
- Scaling policies (CPU, request count, custom metrics)
- Health checks (EC2 + Load Balancer)

**Exam mindset:** “Handle traffic spikes + keep costs down” → ASG.

---

### Elastic Load Balancing (ELB)
**What it is:** Distributes traffic across targets for availability and performance.

**Main types (know the differences):**
- **ALB (Application Load Balancer)**: HTTP/HTTPS, Layer 7, routing rules (paths/hosts), microservices.
- **NLB (Network Load Balancer)**: very high performance, Layer 4 (TCP/UDP), low latency.
- **GWLB (Gateway Load Balancer)**: deploy/scale network appliances (advanced scenarios).

**Exam mindset:**
- “Route based on URL path/host headers” → ALB
- “Extreme performance / TCP / low latency” → NLB

---

### Containers (ECS / EKS)
**Why containers:** Package apps with dependencies; consistent deployment.

- **ECS (Elastic Container Service)**: AWS-native container orchestration.
- **EKS (Elastic Kubernetes Service)**: managed Kubernetes.

**Exam mindset:**
- “We want Kubernetes” → EKS
- “We want containers without managing Kubernetes” → ECS

---

### Serverless (Lambda)
**What it is:** Run code without managing servers.  
**Best for:**
- Event-driven workloads (S3 uploads, API calls, scheduled tasks)
- Spiky/variable traffic
- Microservices “glue” work

**Key concepts:**
- billed per execution/time
- integrates with many AWS services
- works well behind API Gateway

**Exam mindset:** “No servers to manage + event-driven” → Lambda.

---

## When to Choose What (Decision Rules)
- Need OS control / install anything / long-running server → **EC2**
- Need automatic scaling with traffic patterns → **ASG (with EC2)**
- Need to spread traffic across instances reliably → **ELB**
- Need consistent packaging + deployment of apps → **Containers (ECS/EKS)**
- Need event-driven code + no infrastructure mgmt → **Lambda**

---

## Reliability & Cost “Architect” Patterns
- Use **Multi-AZ** designs for high availability (with ELB + ASG).
- Scale out horizontally (more instances) more often than scaling up vertically.
- Cost levers:
  - **On-Demand**: flexible, higher cost
  - **Reserved Instances / Savings Plans**: steady workloads, lower cost
  - **Spot**: cheapest, interruptible (great for batch/fault-tolerant jobs)

---

## 5 Key Takeaways
1. EC2 = flexible VM compute when you need OS/runtime control.
2. ASG + ELB is the classic HA pattern for traffic spikes and resilience.
3. ALB (Layer 7) for HTTP routing; NLB (Layer 4) for extreme performance/low latency.
4. Containers (ECS/EKS) are for packaged apps; EKS specifically when Kubernetes is required.
5. Lambda is serverless, event-driven compute that scales automatically and reduces ops overhead.

---

## Things You May Be Fuzzy On (Review Targets)
- ALB vs NLB (Layer 7 routing vs Layer 4 performance)
- “Scaling up” vs “scaling out” and when ASG is the better play
- When to choose ECS vs EKS (AWS-native vs Kubernetes requirement)
- On-Demand vs Reserved/Savings Plans vs Spot (cost vs reliability tradeoffs)
- How ELB + ASG + Multi-AZ creates high availability
