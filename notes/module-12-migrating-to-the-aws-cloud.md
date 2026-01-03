# Module 12 — Migrating to the AWS Cloud (AWS Cloud Practitioner Essentials)

## What this module covered (high-level)
- AWS migration frameworks and planning
- The AWS Cloud Adoption Framework (CAF)
- The 7 migration strategies (7 Rs)
- Migration services for applications, databases, and data
- Online vs offline data transfer options

## 5 key takeaways
1) **Migration is a business transformation, not just a technical move**  
   Successful migrations consider people, processes, and governance — not just servers.

2) **AWS CAF provides structure for large-scale migrations**  
   CAF organizes migration planning across six perspectives (Business, People, Governance, Platform, Security, Operations).

3) **The 7 migration strategies guide decision-making**  
   Rehost, Replatform, Refactor, Repurchase, Retire, Retain, Relocate help determine *how* each workload should move.

4) **AWS provides specialized tools for each migration phase**  
   Services like Application Migration Service, DMS, DataSync, Snowball, and Snowmobile address different workload and data needs.

5) **Data transfer strategy depends on size, speed, and connectivity**  
   Online transfers work for smaller datasets, while offline services handle massive data volumes efficiently.

## Service selection cheat-sheet (when to use what)
- **AWS CAF** → Plan and govern enterprise-scale cloud adoption
- **AWS Migration Hub** → Track migration progress across tools
- **AWS Application Migration Service** → Lift-and-shift servers to AWS
- **AWS Database Migration Service (DMS)** → Migrate databases with minimal downtime
- **AWS DataSync** → Automated online data transfers
- **AWS Snowball** → Petabyte-scale offline data transfer
- **AWS Snowmobile** → Exabyte-scale data transfer
- **AWS Transfer Family** → Managed SFTP/FTP/FTPS to AWS storage

## Things I’m fuzzy on (review list)
- When to choose **Replatform vs Refactor** in real-world scenarios  
- Differences between **Snowball vs Snowmobile** thresholds  
- How CAF perspectives map to specific AWS services  
- When DMS alone is sufficient vs paired with schema conversion tools  

## Quick self-quiz (3 questions)
1) Which migration strategy minimizes code changes but improves performance?  
2) Which AWS service is best for migrating large datasets when internet bandwidth is limited?  
3) Which CAF perspective focuses on identity, compliance, and risk management?

