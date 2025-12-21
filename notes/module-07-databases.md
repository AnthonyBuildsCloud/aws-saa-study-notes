# Module 7 — Databases (AWS Cloud Practitioner Essentials)

## What I learned (module summary)
In this module, we explored the managed relational database capabilities of Amazon RDS and Amazon Aurora. We covered how AWS DMS supports database migrations, and how DynamoDB provides a NoSQL option for scalable applications.

We also learned about in-memory caching with ElastiCache, MongoDB-compatible document databases with Amazon DocumentDB, and AWS Backup for centralized data protection across AWS services. Finally, we looked at Amazon Neptune for graph databases and relationship-based queries.

## Core services covered
- Amazon RDS (managed relational databases)
- Amazon Aurora (high-performance managed relational database)
- AWS Database Migration Service (DMS)
- Amazon DynamoDB (serverless NoSQL)
- Amazon ElastiCache (in-memory caching)
- Amazon DocumentDB (MongoDB-compatible document database)
- AWS Backup (centralized backup management)
- Amazon Neptune (graph database)

## 5 key takeaways
1) **RDS vs Aurora:** Both are managed relational databases, but Aurora is optimized for performance and scalability in the AWS ecosystem.
2) **DMS:** Helps migrate databases to AWS and can support ongoing replication during migration scenarios.
3) **DynamoDB:** Serverless NoSQL database designed for scale and low-latency access patterns.
4) **ElastiCache:** In-memory caching to reduce database load and improve application performance (not a primary system of record).
5) **Specialized databases exist for a reason:** DocumentDB supports document use cases, and Neptune supports relationship-heavy graph queries.

## Service selection cheat-sheet (architect mindset)
- Need SQL + structured schema + joins → **RDS or Aurora**
- Need high-performance relational + strong AWS integration → **Aurora**
- Need massive scale + low-latency key-value/document access → **DynamoDB**
- Need caching to accelerate reads / offload DB → **ElastiCache**
- Need MongoDB-style document database compatibility → **DocumentDB**
- Need relationship/graph queries (connected data) → **Neptune**
- Need to migrate existing DBs into AWS with minimal downtime → **DMS**
- Need centralized backups across AWS services → **AWS Backup**

## Things I may be fuzzy on (to review)
- When to choose **RDS vs Aurora** (decision signals)
- DynamoDB basics: partition key vs sort key, and how access patterns drive design
- Difference between **DocumentDB vs DynamoDB** (both “NoSQL-ish” but different use cases)
- What ElastiCache solves vs what it does NOT solve (cache vs database)
- Where AWS Backup fits vs native DB backups (centralized policy vs service-level features)
- When Neptune is the right tool (graph queries vs relational modeling)

## Next steps (Module 8 prep)
- Start Module 8: AI/ML & Data Analytics
- Track new services and map each to: (Use case → Why → Key limitation)

## Interview-style decision bullets
- If the requirement includes SQL joins + transactions, I start with RDS/Aurora rather than DynamoDB.
- If the bottleneck is read latency and repeated lookups, I consider ElastiCache to offload the primary database.
- If the problem is relationship traversal (friends-of-friends, fraud rings), I consider Neptune for graph queries.
