# Module 13 — Well-Architected Solutions (AWS Cloud Practitioner Essentials)

## What this module covered (high-level)
- AWS Well-Architected Framework and its purpose
- The six pillars of well-architected workloads
- Using the AWS Well-Architected Tool to review architectures
- Overview of specialized AWS services and real-world use cases
- How serverless architectures align with well-architected principles

## 5 key takeaways
1) **The Well-Architected Framework is AWS’s gold standard for design**  
   It provides best practices to build systems that are secure, reliable, performant, cost-efficient, and sustainable.

2) **The six pillars guide architectural decision-making**  
   Operational Excellence, Security, Reliability, Performance Efficiency, Cost Optimization, and Sustainability should all be balanced.

3) **The Well-Architected Tool identifies risk, not failure**  
   It highlights *high-risk issues* and improvement areas so teams can iterate safely and continuously.

4) **Serverless architectures naturally support well-architected workloads**  
   Services like Lambda, API Gateway, and DynamoDB reduce operational burden and improve scalability and cost efficiency.

5) **Well-architected reviews are ongoing, not one-time events**  
   Architectures should evolve as workloads, scale, and business needs change.

## Service selection cheat-sheet (when to use what)
- **AWS Well-Architected Tool** → Review workloads against the six pillars
- **AWS Lambda** → Serverless compute with no infrastructure management
- **Amazon API Gateway** → Build and manage APIs at scale
- **Amazon DynamoDB** → Serverless NoSQL database for high-scale applications
- **AWS Trusted Advisor** → Ongoing best-practice checks across cost, security, and performance

## Things I’m fuzzy on (review list)
- When to prioritize one pillar over another in real-world tradeoffs
- How often well-architected reviews should be performed in production
- Differences between Trusted Advisor checks and Well-Architected reviews

## Quick self-quiz (3 questions)
1) What is the main purpose of the AWS Well-Architected Framework? To help architects design, evaluate, and continuously improve cloud workloads using AWS best practices so they are secure, reliable, high-performing, cost-optimized, and sustainable.  
2) Name at least three of the six Well-Architected pillars.  
Operational Excellence
Security
Reliability
Performance Efficiency
Cost Optimization
Sustainability
3) Why do serverless services align well with the Well-Architected Framework? Because serverless services offload infrastructure management to AWS, automatically scale, improve reliability and security by default, optimize costs through pay-per-use pricing, and support high performance with minimal operational overhead.
