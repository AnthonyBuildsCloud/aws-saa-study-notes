# Module 6 – Storage (AWS Cloud Practitioner Essentials)

## High-yield summary (by module)
Module 6 covers AWS storage categories and when to use each:
- **Block storage (EBS / Instance Store):** disks for EC2
- **Object storage (S3):** buckets for files/objects at massive scale
- **File storage (EFS / FSx):** shared file systems accessed over a network
It also introduces storage lifecycle concepts and hybrid storage options.

---

## 5 key takeaways
1) **Block vs Object vs File is the core decision.**
   - Block = “hard drive” for an EC2 instance
   - Object = “bucket of files” with metadata, accessed via API
   - File = “shared folder” over the network

2) **EBS is persistent block storage for EC2.**
   If an EC2 instance stops/starts, EBS data remains (persistence is the key word).

3) **Instance Store is temporary storage attached to the host.**
   Great performance, but data is lost if the instance is stopped/terminated (ephemeral).

4) **S3 is durable, scalable object storage.**
   Best for backups, media, static websites, logs, and data lakes.
   Storage classes + lifecycle rules help manage cost.

5) **EFS is a managed shared file system for multiple EC2 instances.**
   Good for shared application files, home directories, content management, and shared workloads.

---

## Fuzzy areas to review (common confusion zones)
- **EBS vs Instance Store**
  - EBS = persistent (data survives instance stop/start)
  - Instance Store = ephemeral (data loss on stop/terminate)

- **EBS vs EFS**
  - EBS = attached to one instance (typical)
  - EFS = shared file system mounted by many instances

- **S3 “object storage” concept**
  Not a normal file system. Access via API; objects live in buckets.

- **S3 Storage Classes + Lifecycle**
  Know that you can automatically move objects between classes over time to save money.

- **When to use FSx**
  Managed file systems for specific needs (Windows/Lustre/NetApp/OpenZFS depending on use case).

---

## (Next) Flashcards
**Q:** What are the three main storage types in AWS?  
**A:** Block storage, object storage, and file storage.

**Q:** What is Amazon EBS?  
**A:** Persistent block storage volumes for EC2 (like a virtual hard drive).

**Q:** What is EC2 Instance Store?  
**A:** Temporary storage physically attached to the host (high performance, not persistent).

**Q:** When do you choose EBS vs Instance Store?  
**A:** Choose EBS when data must persist; choose Instance Store for temporary/high-speed scratch data.

**Q:** What is Amazon S3?  
**A:** Object storage service that stores data as objects in buckets, accessed via API.

**Q:** What is an S3 bucket?  
**A:** A container for storing objects in S3.

**Q:** What is an S3 lifecycle policy?  
**A:** Rules that transition objects to cheaper storage classes or expire/delete them automatically.

**Q:** What is Amazon EFS?  
**A:** Managed file storage that provides a shared file system for multiple compute resources.

**Q:** What is Amazon FSx?  
**A:** Managed file system service offering specialized file systems (commonly Windows workloads or high-performance needs).

**Q:** What is AWS Storage Gateway?  
**A:** Hybrid service connecting on-prem environments to AWS storage (commonly for hybrid storage use cases).

---

## (Next) Mistakes Bank (things to watch for)
- Treating **S3 like a mounted drive** (it’s object storage via API, not a traditional file system).
- Forgetting **Instance Store is temporary** (great speed, but data can vanish with instance stop/terminate).
- Confusing **EBS and EFS**
  - EBS = “one server’s disk”
  - EFS = “shared network drive”
- Choosing expensive storage because it “sounds faster” instead of matching the workload.
- Not using **lifecycle policies** (leaves money on the table for data that should move to colder storage).

---

## Quick decision rules (exam-style shortcuts)
- “Need a disk for EC2” → **EBS**
- “Need temporary scratch space / super fast local storage” → **Instance Store**
- “Store files at massive scale, backups, static website assets” → **S3**
- “Shared file system for multiple instances” → **EFS**
- “Windows file share needs / specialized file system” → **FSx**
- “Hybrid on-prem to AWS storage” → **Storage Gateway**
