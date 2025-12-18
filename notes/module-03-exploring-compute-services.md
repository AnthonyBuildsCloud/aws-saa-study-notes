# Module 3 – Exploring Compute Services (AWS Cloud Practitioner Essentials)

## High-yield summary (by module)
Module 3 expands “compute” beyond EC2 into:
- **Serverless (Lambda):** run code on-demand without managing servers
- **Containers (ECS/EKS + Fargate):** package apps consistently and run them at scale
- **Additional compute services:** simpler deployment/hosting or specialized workloads (Beanstalk, Lightsail, Batch)

Core skill: **choose the right compute model** based on control vs simplicity, workload pattern, and scaling needs.

---

## 5 key takeaways
1) **Serverless doesn’t mean “no work,” it means “no servers.”**  
   You still manage code, permissions, triggers, and observability.

2) **AWS Lambda = event-driven compute.**  
   If the question says “when X happens, run code,” your default thought should be Lambda.

3) **Containers solve “it works on my machine.”**  
   They package the app + dependencies so it runs consistently across environments.

4) **ECS vs EKS is mainly an orchestration choice.**  
   - Want AWS-native + simpler ops → **ECS**  
   - Must use Kubernetes → **EKS**

5) **Fargate is the “no server management” layer for containers.**  
   You run containers without provisioning or maintaining EC2 hosts.

---

## Fuzzy areas to review (common confusion zones)
- **Serverless vs containers vs EC2:**  
  When do you pick each? (Control vs simplicity vs execution model)

- **Lambda “stateless” concept:**  
  Where does state live? (S3, DynamoDB, RDS, etc.)

- **ECS vs EKS vs Fargate relationship:**  
  Fargate is not an orchestrator; it’s a compute engine used *with* ECS/EKS.

- **Elastic Beanstalk vs EC2:**  
  Beanstalk is “deploy the app, AWS sets up the infra” (still uses EC2/LB under the hood).

- **Lightsail vs “full AWS”:**  
  Lightsail is simplified hosting with fewer knobs; great for small/simple workloads.

---

## (Next) Flashcards
**Q:** What does “serverless” mean in AWS?  
**A:** AWS manages the servers/infrastructure; you manage code + config (permissions, triggers, monitoring).

**Q:** What is AWS Lambda best for?  
**A:** Event-driven workloads (run code when triggered by API calls, S3 uploads, schedules, streams).

**Q:** Lambda vs EC2 (one-liner decision rule)?  
**A:** Lambda for event-driven/on-demand tasks; EC2 when you need OS control and traditional server-based apps.

**Q:** What problem do containers solve?  
**A:** Consistent packaging of app + dependencies so it runs the same across environments.

**Q:** ECS vs EKS?  
**A:** ECS = AWS-native orchestration; EKS = Kubernetes orchestration.

**Q:** What is AWS Fargate?  
**A:** Serverless compute for containers (no EC2 host management), used with ECS/EKS.

**Q:** What is Elastic Beanstalk?  
**A:** Managed platform to deploy web apps quickly; AWS provisions infra like EC2/LB/Auto Scaling.

**Q:** What is Lightsail best for?  
**A:** Simple VPS-style hosting with predictable pricing (small sites, WordPress, prototypes).

**Q:** What is AWS Batch best for?  
**A:** Queue-based batch processing jobs at scale (scheduled/large job runs).

---

## (Next) Mistakes Bank (things to watch for)
- Thinking **Fargate replaces ECS/EKS** (it doesn’t; it runs containers *for* them).
- Treating **Lambda as a “server”** (it’s a function execution model, typically stateless, event-triggered).
- Choosing **EKS “because it sounds advanced”** when the requirement doesn’t mention Kubernetes.
- Assuming **Beanstalk is “free compute”** (you still pay for underlying resources).
- Using **Lightsail for complex enterprise networking needs** (it’s meant to be simple).

---

## Service map (quick mental model)
- **EC2:** full control, traditional servers
- **Lambda:** event-driven functions, serverless
- **ECS/EKS:** orchestrate containers
- **Fargate:** run containers without managing servers
- **Elastic Beanstalk:** deploy apps quickly (managed platform)
- **Lightsail:** simplified hosting
- **AWS Batch:** batch job scheduling + execution
