# Module 9 — Security (AWS Cloud Practitioner Essentials)

## What this module covered (high-level)
- AWS Shared Responsibility Model (who secures what)
- Preventing unauthorized access (IAM + MFA)
- Protecting networks and applications (security groups, NACLs, WAF)
- Protecting data (encryption, key management, secrets)
- Detecting/responding to security incidents (logging + monitoring + threat detection)

## 5 key takeaways
1) **Shared Responsibility Model is the foundation:** AWS secures *the cloud* (facilities, hardware, managed service infrastructure), you secure *in the cloud* (IAM, data, configs, networking rules).
2) **IAM is your control plane for permissions:** Use policies to define access, follow **least privilege**, and prefer **roles** (short-lived credentials) over long-term access keys.
3) **Defense-in-depth wins:** Identity controls + network controls + encryption + monitoring. Don’t rely on one layer (ex: “private subnet” isn’t a security strategy by itself).
4) **Encryption is everywhere (and usually easy):** Encrypt data **at rest** (S3/EBS/RDS) and **in transit** (TLS). Use **KMS** for managed keys; rotate and restrict key use.
5) **Logging + detection are non-negotiable:** **CloudTrail** tells you *who did what* via API calls; tools like **GuardDuty** and **Security Hub** help you spot and aggregate risk signals.

## Service selection cheat-sheet (when to use what)
### Identity / Access
- **IAM** → users, groups, roles, policies (permissions)
- **MFA** → stronger authentication for users

### Network / App Protection
- **Security Groups** → instance-level firewall (stateful)
- **NACLs** → subnet-level rules (stateless)
- **AWS WAF** → protect web apps from common attacks (SQLi, XSS)
- **AWS Shield** → DDoS protection (Standard is automatic; Advanced is enhanced)

### Data Protection
- **KMS** → managed encryption keys integrated with AWS services
- **CloudHSM** → dedicated customer-controlled HSM hardware
- **Secrets Manager** → store/rotate secrets (DB creds, API keys)
- **SSM Parameter Store** → configuration + secrets (lighter-weight; common for app params)

### Visibility / Detection / Response
- **CloudTrail** → audit trail of API calls (who/what/when)
- **AWS Config** → track config changes + evaluate compliance rules
- **GuardDuty** → threat detection (suspicious activity patterns)
- **Inspector** → vulnerability scanning (instances/containers)
- **Security Hub** → central view of findings from multiple security services

## Things I’m fuzzy on (review list)
- When to choose **Security Groups vs NACLs** (stateful vs stateless + typical use cases)
- **CloudTrail vs Config vs CloudWatch** (audit vs configuration compliance vs metrics/logs/alarms)
- **KMS vs CloudHSM** (managed keys vs dedicated HSM and when that matters)
- **Secrets Manager vs Parameter Store** (rotation/managed features vs simpler parameters)
- How **WAF** differs from **Shield** (app-layer filtering vs DDoS protection)

## Quick self-quiz (3 questions)
1) The AWS Shared Responsibility Model means AWS is responsible for **security of the cloud**, and customers are responsible for **security in the cloud**.
2) If I need to log API activity across my account, I use: **CloudTrail** because it records **who made which API call and when**.
3) If I need managed encryption keys for AWS services, I use: **KMS** because it provides **centrally managed keys + tight IAM-based access control + service integration**.

## Common exam traps / gotchas
- **IAM Roles** are preferred for AWS services/apps running on AWS (avoid long-term access keys when possible).
- **Security Groups = stateful**, **NACLs = stateless**.
- **CloudTrail = API activity**, **Config = configuration history/compliance**, **CloudWatch = metrics/logs/alarms**.
