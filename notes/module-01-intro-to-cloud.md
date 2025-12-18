# Module 1 — Introduction to the Cloud (AWS SAA)

## What “Cloud” Means (in plain English)
Cloud computing = renting compute, storage, and services over the internet with:
- **On-demand** access (spin up resources when you need them)
- **Pay-as-you-go** pricing (reduce upfront capex)
- **Elastic scaling** (scale up/down quickly)
- **Managed services** (AWS runs the heavy ops work)

---

## Cloud Deployment Models
- **Public cloud**: AWS owns/operates the infrastructure; you rent it.
- **Private cloud**: cloud-like environment owned/managed by one organization.
- **Hybrid**: mix of on-prem + cloud (common during migrations).
- **Multi-cloud**: using multiple providers (Azure + AWS, etc.) for strategy or requirements.

---

## Cloud Service Models (High Yield)
- **IaaS (Infrastructure as a Service)**  
  You manage OS and above; provider manages hardware/data center.  
  *Example mindset:* virtual machines, networking, storage.

- **PaaS (Platform as a Service)**  
  You manage your app + data; provider manages runtime/OS/infra.  
  *Example mindset:* “I deploy code, AWS handles the platform.”

- **SaaS (Software as a Service)**  
  You consume a finished product; provider manages everything.  
  *Example mindset:* “I just log in and use it.”

**Exam-style rule:** The more you move from IaaS → PaaS → SaaS, the less you manage.

---

## Why Companies Use the Cloud
- **Cost efficiency**: shift capex → opex; pay only for what you use
- **Speed & agility**: provision resources in minutes, not weeks
- **Global reach**: deploy closer to users worldwide
- **Reliability**: design for HA using regions/AZs
- **Security options**: strong controls, logging, encryption (shared responsibility model)
- **Innovation velocity**: access managed services (databases, analytics, AI)

---

## Key AWS Global Infrastructure Terms
- **Region**: geographic area (example: us-west-2).
- **Availability Zone (AZ)**: isolated data centers within a Region.
- **Edge Location**: used for content delivery + low-latency experiences (often tied to CDN concepts).

**Rule of thumb:**  
- Multi-AZ = high availability within a region  
- Multi-Region = disaster recovery / global performance

---

## Shared Responsibility Model (very testable)
### AWS is responsible for: “Security OF the Cloud”
- Physical data centers, hardware, networking, virtualization layer

### You are responsible for: “Security IN the Cloud”
- Identity/access management
- Data encryption choices
- Network configuration (security groups/NACLs)
- OS patching (depending on the service type)
- App security and data classification

**Exam-style rule:** Managed services shift more responsibility to AWS.

---

## 5 Key Takeaways
1. Cloud = on-demand, pay-as-you-go, scalable resources over the internet.
2. Public vs private vs hybrid vs multi-cloud are strategy choices (hybrid is common).
3. IaaS/PaaS/SaaS = how much you manage (IaaS most, SaaS least).
4. Regions contain multiple AZs; use Multi-AZ for HA and Multi-Region for DR/global reach.
5. Shared responsibility model is core: AWS secures the cloud; you secure what you deploy in it.

---

## Things Im Fuzzy On (review targets)
- Differences between **IaaS vs PaaS vs SaaS** (who manages what)
- **Hybrid vs multi-cloud** (mixing on-prem vs mixing providers)
- When to choose **Multi-AZ vs Multi-Region**
- Shared responsibility model details (what AWS vs customer owns)
