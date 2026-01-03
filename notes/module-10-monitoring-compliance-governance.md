# Module 10 — Monitoring, Compliance, and Governance (AWS Cloud Practitioner Essentials)

## What this module covered (high-level)
- Monitoring AWS resources, applications, and operational health
- Auditing API activity and changes
- Compliance and governance tooling in AWS
- Organization-wide visibility, cost, security, and best-practice checks

## 5 key takeaways
1) **Monitoring ≠ auditing:** CloudWatch focuses on metrics, logs, and alarms (performance/health), while CloudTrail focuses on **who did what via API calls**.
2) **CloudWatch is your operational heartbeat:** Metrics, logs, dashboards, and alarms let you detect issues *before* customers notice them.
3) **CloudTrail is mandatory for accountability:** It records API activity across AWS services and is critical for security investigations and compliance.
4) **Governance scales with accounts:** Services like **AWS Organizations** and **Config** help manage rules, policies, and standards across multiple accounts.
5) **Trusted Advisor is continuous guardrails:** It proactively checks cost optimization, security gaps, fault tolerance, performance, and service limits.

## Service selection cheat-sheet (when to use what)
### Monitoring & Visibility
- **Amazon CloudWatch** → metrics, logs, alarms, dashboards, operational health
- **AWS Health** → service events affecting your resources (planned + unplanned)

### Auditing & Compliance
- **AWS CloudTrail** → record API calls and user activity (audit trail)
- **AWS Config** → track resource configuration changes and compliance rules
- **AWS Audit Manager** → automate evidence collection for audits

### Governance & Organization
- **AWS Organizations** → centrally manage accounts, SCPs, consolidated billing
- **Service Control Policies (SCPs)** → guardrails on what accounts *can* do
- **AWS Artifact** → access AWS compliance reports and agreements

### Optimization & Best Practices
- **AWS Trusted Advisor** → real-time recommendations for:
  - Cost optimization
  - Security
  - Performance
  - Fault tolerance
  - Service limits

## Things I’m fuzzy on (review list)
- **CloudWatch vs CloudTrail vs Config** (metrics/logs vs API activity vs configuration state)
- When to use **AWS Health** vs **Trusted Advisor**
- How **SCPs** differ from **IAM policies**
- How **Audit Manager** simplifies compliance compared to manual audits
- What Config rules can (and cannot) enforce automatically

## Quick self-quiz (3 questions)
1) If I need to monitor CPU utilization and trigger alerts, I use: **CloudWatch** because it tracks metrics and alarms.
2) If I need to answer “who deleted this resource?”, I use: **CloudTrail** because it records API activity.
3) If I need to evaluate whether resources stay compliant over time, I use: **AWS Config** because it tracks configuration changes and evaluates rules.

## Common exam traps / gotchas
- **CloudWatch ≠ CloudTrail** (performance vs auditing)
- **IAM policies grant permissions; SCPs restrict maximum permissions**
- **Trusted Advisor is advisory**, not enforcement
- **Artifact is documentation**, not monitoring or enforcement
