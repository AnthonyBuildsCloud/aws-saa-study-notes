# Module 5 – Networking (AWS Cloud Practitioner Essentials)

## High-yield summary (by module)
Module 5 introduces how AWS networking is organized and secured using **Amazon VPC**:
- VPC = your private network in AWS
- Subnets = segments of that network (public/private)
- Route tables + gateways control where traffic can go
- Security Groups + NACLs control what traffic is allowed
It also covers ways to connect to AWS and basic global networking concepts.

---

## 5 key takeaways
1) **Amazon VPC = your isolated network in AWS.**
   It’s where you place resources like EC2, RDS, and internal services.

2) **Subnets split your VPC into smaller networks (often by AZ).**
   - Public subnet: route to the internet (via Internet Gateway)
   - Private subnet: no direct internet route (often uses NAT for outbound-only access)

3) **Security Groups vs NACLs = instance-level vs subnet-level security.**
   - Security Group: attached to resources (like EC2), “allow rules only”
   - NACL: attached to subnets, allows/denies traffic

4) **Routing decides reachability.**
   Route tables + gateways are the “traffic directors.”  
   If it can’t route, it can’t communicate—even if security rules are open.

5) **Connectivity options depend on the use case.**
   - Public internet access (simple)
   - Site-to-site VPN (encrypted over internet)
   - Direct Connect (dedicated private connection)

---

## Fuzzy areas to review (common confusion zones)
- **VPC vs Subnet**
  VPC = the overall private network; subnets are subdivisions inside it.

- **Public vs Private subnet**
  The difference is **routing** (internet route or not), not the name.

- **Security Group vs NACL**
  People mix these up constantly; know the scope:
  SG = resource level. NACL = subnet level.

- **Route table vs Security rules**
  Route table = “where traffic can go.”
  SG/NACL = “whether traffic is allowed.”

- **Ways to connect to AWS**
  VPN vs Direct Connect (internet-based vs dedicated line).

---

## (Next) Flashcards
**Q:** What is a VPC?  
**A:** A logically isolated virtual network in AWS where you launch resources.

**Q:** What is a subnet?  
**A:** A segment of a VPC (often mapped to one AZ) where resources are placed.

**Q:** What makes a subnet “public”?  
**A:** It has a route to the internet through an Internet Gateway.

**Q:** What makes a subnet “private”?  
**A:** It has no direct route to an Internet Gateway (often uses NAT for outbound).

**Q:** What is a Security Group?  
**A:** A resource-level virtual firewall that controls inbound/outbound traffic (allow rules).

**Q:** What is a Network ACL (NACL)?  
**A:** A subnet-level firewall that can allow or deny traffic.

**Q:** What does a route table do?  
**A:** Determines where network traffic is directed (routing destinations/targets).

**Q:** What is AWS Site-to-Site VPN?  
**A:** Encrypted connection between on-prem network and AWS over the public internet.

**Q:** What is AWS Direct Connect?  
**A:** Dedicated private network connection between on-prem and AWS.

---

## (Next) Mistakes Bank (things to watch for)
- Calling a subnet “public” because it *has public IPs* (public/private is about **routing**).
- Assuming Security Groups “deny” traffic explicitly (they are allow-based; anything not allowed is implicitly blocked).
- Forgetting that **both** routing and security must permit traffic (open ports don’t help if routing is wrong).
- Mixing up SG vs NACL scope (SG = instance/resource; NACL = subnet).
- Thinking Direct Connect is “just faster VPN” (it’s a dedicated private link with different reliability/latency profile).

---

## Quick decision rules (exam-style shortcuts)
- “Private network in AWS” → VPC
- “Split network by AZ / isolate resources” → subnets
- “Control traffic to an EC2 instance” → Security Group
- “Control traffic at subnet boundary” → NACL
- “Need on-prem to AWS connection (encrypted over internet)” → Site-to-Site VPN
- “Need consistent, dedicated private connectivity” → Direct Connect
