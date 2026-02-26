# <p align=center>Domain 7 - Security Operations</p>

---

## 🧠 Mind Map
[CISSP Domain 7 Destination Certification](https://destcert.com/resources/cissp-domain-7-security-operations/)

---

## 🚨 Elevator Pitch  
Keep security running day to day and respond when things go wrong. Domain 7 is about **operating**, **monitoring**, **responding**, and **recovering**. This is where incidents happen, alerts fire, people make mistakes, and processes either save you or sink you.

Detect fast, respond correctly, recover cleanly, and learn afterward.

---

## 🧠 Operations Mindset  

This domain is about **execution**, not theory.

- Design controls > Domains 1-3  
- Secure systems > Domains 4-5  
- **Run and defend systems > Domain 7**

---

## 👀 Monitoring and Detection  

**Alerts without response are useless**.
You cannot respond to what you cannot see. 

### Sources  
- System logs  
- Application logs  
- Network logs  
- Authentication and authorization logs  
- Endpoint telemetry  

### Tools  
- SIEM  
- EDR/XDR  
- IDS/IPS  
- File integrity monitoring  
- SOAR (automated response orchestration)

---

### Monitoring Quick Reference

| Area | What You Watch | Why |
|------|---------------|-----|
| Auth | Logins, failures, privilege use | Detect account compromise |
| Network | Firewall, IDS | Lateral movement |
| Endpoint | EDR alerts | Malware execution |
| Files | Integrity changes | Unauthorized modification |
| SIEM | Correlation | Single-pane visibility |

---

## 🚨 Incident Management  

### Incident vs Event  
- **Event** - Something happened  
- **Incident** - Security impact or policy violation  

### Incident Communication

- Legal involvement
- Executive notification
- Regulatory reporting (where required)
- Public relations coordination

Not every event is an incident.

---

### 🔥 Incident Response Lifecycle (What happens, why, and how)

Containment is not equal to eradication. Stop spread first. Remove root cause later.

| Phase | Core Meaning | Primary Goal | Key Actions | Hook |
|------|--------------|-------------|------------|-----------|
| **Preparation** | Be ready | Ensure readiness | IR plan, defined roles, tools, access, exercises | No prep = chaos |
| **Detection & Analysis** | Confirm + scope | Validate and understand incident | Alert triage, impact assessment, evidence preservation | Do not destroy evidence |
| **Containment** | Stop spread | Limit damage | Isolate hosts, disable accounts, block IPs | Buys time |
| **Eradication** | Remove cause | Eliminate root issue | Delete malware, patch vulnerabilities, remove persistence | Happens after containment |
| **Recovery** | Restore service | Return to production safely | Rebuild systems, monitor closely, validate operations | Watch for recurrence |
| **Lessons Learned** | Fix process | Improve posture | Document findings, update controls, refine IR plan | Prevent repeat incidents |

---

## 🧪 Incident Classification  
Classification drives response and reporting.

- Malware  
- Unauthorized access  
- Data breach  
- Denial of service  
- Insider threat  
- Physical security incident  

---

## 🎯 Cyber Kill Chain

The cyber kill chain is a security framework developed by Lockheed Martin that breaks down a cyberattack into various stages to help identify and mitigate security incidents. It outlines the steps attackers typically follow, allowing security teams to prevent, detect, or intercept attacks at different points in the process. The framework is inspired by military strategies and aims to enhance the effectiveness of cybersecurity measures by providing a structured approach to understanding and responding to threats.

You can find a detailed video on this [here](https://www.youtube.com/watch?v=19hw_CHO0X8)

| Phase | Attacker Goal | What Happens | Defensive Focus |
|-------|--------------|--------------|-----------------|
| 🔎 **1. Reconnaissance** | Gather intelligence | Identify targets, employees, technologies, IP ranges, vulnerabilities | OSINT monitoring, attack surface reduction |
| 🛠️ **2. Weaponization** | Prepare attack payload | Combine exploit with malware (e.g., malicious document, exploit kit) | Threat intelligence, malware analysis |
| 📤 **3. Delivery** | Transmit payload to victim | Phishing email, malicious link, USB drop, drive-by download | Email security, web filtering, user awareness |
| 💥 **4. Exploitation** | Trigger vulnerability | Malicious code executes by exploiting software flaw or user action | Patch management, EDR, exploit prevention |
| 📦 **5. Installation** | Establish persistence | Malware installs backdoor, rootkit, or persistence mechanism | Application control, endpoint monitoring |
| 📡 **6. Command & Control (C2)** | Maintain remote access | Infected host communicates with attacker-controlled server | Network monitoring, IDS/IPS, egress filtering |
| 🎯 **7. Actions on Objectives** | Achieve mission goal | Data exfiltration, ransomware deployment, destruction, lateral movement | DLP, segmentation, anomaly detection |

---

## 🧬 Forensics Basics

You can find more details here: [RFC 3227](https://www.rfc-editor.org/rfc/rfc3227). Preserve first. Analyze later. Never touch originals.  
🚨 **Golden rule:** Never analyze original evidence. Always image first.


| Concept | Core Rule | What You Do | Why It Matters |
|--------|-----------|-------------|-----------------------------|
| Chain of Custody | Every handoff must be documented | Record who, when, where, why, how | Broken chain = evidence may be inadmissible |
| Order of Volatility | Collect most volatile data first | CPU/cache > RAM > network > disk > logs | Powering off too early destroys critical evidence |
| Forensic Imaging | Always work from a copy | Create bit-for-bit image (incl. slack/deleted space) using write blockers | Original evidence must remain untouched |
| Integrity Verification | Prove evidence was not altered | Hash before and after imaging (e.g., SHA-256) | Matching hashes = defensible integrity |
| Evidence Handling | Never analyze originals | Perform all work on verified images | Protects legal validity |
| Documentation | Log everything | Actions, timestamps, tools used | Technical skill without documentation fails in court |

### Order of Volatility (memorize)
1. CPU registers / cache  
2. RAM  
3. Network connections / running processes  
4. Disk data  
5. Logs / archival media  

---

### Types of Evidence

| Type | Meaning |
|------|--------|
| Real | Physical objects (hardware, drives) |
| Documentary | Logs, records, files |
| Testimonial | Verbal statements |
| Demonstrative | Visual aids, diagrams |

---

### Evidence Handling Summary

Powering off early destroys evidence.

| Rule | Meaning |
|------|--------|
| Never touch original | Always image first |
| Hash before + after | Proves integrity |
| Document everything | Legal defensibility |
| RAM first | Volatile data disappears |

---

## 🔐 Identity and Access Operations  

### Access Management  
- Provisioning  
- Review and recertification  
- Deprovisioning  

---

### Privileged Access  
- Separate admin accounts  
- MFA everywhere  
- Logging and monitoring  
- Just-in-time access  

---

## 🔄 Change and Configuration Management  


### Change Types  
- Standard  
- Normal  
- Emergency  

All changes require:
- Approval  
- Documentation  
- Rollback plan  

---

## 🧰 Patch and Vulnerability Management  

### Patch Management  
- Identify  
- Test  
- Deploy  
- Verify  

---

### Vulnerability Management  
- Scan  
- Prioritize  
- Remediate  
- Rescan  

Severity + exploitability + exposure matter.

---

## 🧯 Disaster Recovery (DR)  

Restore IT systems after major failure.

### DR Focus  
- Systems and data  
- Backups  
- Alternate processing  

Key metrics:
- **RTO** - restore time  
- **RPO** - acceptable data loss  

### Recovery Sites

| Type | Speed | Cost | Notes |
|------|-------|------|------|
| 🔥 Hot | Fastest | Most expensive | Fully operational duplicate site |
| 🥵 Warm | Moderate | Medium | Partial systems ready |
| 🥶 Cold | Slowest | Cheapest | Empty facility, hardware installed later |

---

### IR vs DR vs BCP

IR handles security events. DR restores systems. BCP keeps operations alive.

| Discipline | Focus |
|-----------|------|
| Incident Response | Stop attack |
| Disaster Recovery | Restore IT |
| Business Continuity | Keep business running |

---

## 🧪 Exercises and Testing  

**C-T-P-F** = **C**hecklist > **T**abletop > **P**arallel > **F**ull interruption (least > most disruptive)

- Tabletop exercises  
- Walkthroughs  
- Simulations  
- Full interruption tests  

---

## 💽 RAID (Availability vs Performance vs Cost)

| Emoji | RAID | Layout | Disk Failures Tolerated | Strength | Weakness | Hook |
|------|------|--------|-------------------------|----------|----------|------------|
| 🚀 | RAID 0 | Striping only | 0 | Maximum performance | Any disk loss = total data loss | **0 = 0 redundancy** (fast + dead) |
| 🪞 | RAID 1 | Mirroring | 1 (per mirror pair) | High availability, simple | 50% storage loss | **1 = 1 mirror** |
| 📦 | RAID 5 | Striping + single parity | 1 | Good storage efficiency | Write penalty, risky rebuilds on large arrays | Balanced, but fragile |
| 🛡️ | RAID 6 | Striping + dual parity | 2 | Safer than RAID 5 for large arrays | Higher write penalty | RAID 5 with seatbelt |
| 🏦 | RAID 10 (1+0) | Mirrored stripes | Multiple (one per mirror pair) | Best performance + redundancy | Expensive | **Mission-critical choice** |

🚫 RAID = availability only.  
🚫 RAID ≠ backup (does not protect against deletion, ransomware, or corruption).  

---

## 🔄 Backup Operations  

⚠️ **Backups must be tested regularly. Untested backups are assumptions.**  
A backup only has value if it can be successfully restored.

### 💾 Backup Types

| Backup Type | What It Backs Up + Hook | Backup Speed | Restore Speed | Disk Space | Production Impact | Restore Complexity | RTO Impact |
|------------|--------------------------|-------------|--------------|-------------|-------------------|-------------------|-----------|
| 📦 **Full** | Complete copy of all data. Simplest restore. Baseline for all others. | 🐢 Slow | ✨ Fastest | 💾 Highest | 🏭 Heavy | One step | Lowest |
| ➕ **Incremental** | Files changed since last full *or incremental*. Clears archive bit. Full + every incremental needed to restore. More steps = higher failure risk. | ⚡ Fast | 🐢 Slowest | 💾 Lowest | 🏭 Light | Many steps | Highest |
| 📈 **Differential** | Files changed since last **full**. Does NOT clear archive bit. Backup grows daily. Restore = full + latest differential. | ⏳ Grows daily | ⚡ Faster than incremental | 💾 Medium | Medium | Two steps | Lower than incremental |
| 🧩 **Synthetic** | New "full" built from prior full + incrementals/differentials without touching production systems. Minimizes backup window load. | ⏱️ Very fast | ⚡ Fast | 💾 Depends on chain | 📦 Minimal | One step | Low |


---

### Restore Complexity

More restore steps = higher failure probability.

| Type | Restore Steps | Risk |
|------|--------------|------|
| Full | One | Lowest |
| Differential | Two | Medium |
| Incremental | Many | Highest |

---

### ♻️ Rotation Strategy - GFS (Grandfather-Father-Son)
Used to balance retention, cost, and recovery flexibility.
Provides structured retention and versioning over time.

- 👶 **Son** = Daily backups  
- 👨 **Father** = Weekly backups  
- 👴 **Grandfather** = Monthly backups  

---

### 🛡️ Backup Rule – 3-2-1 Rule
Consider **immutable or air-gapped backups** to resist ransomware.
Best practice for resilience and ransomware protection:

- 3️⃣ **Three** copies of data (1 production + 2 backups)  
- 2️⃣ **Two** different media types (e.g., disk + cloud/tape)  
- 1️⃣ **One** copy offsite (or offline/immutable)  

---

## 🧑‍🤝‍🧑 Personnel and Operational Security  

### Insider Threat  
- Malicious  
- Negligent  
- Compromised  

Controls:
- Least privilege  
- Monitoring  
- Separation of duties  
- Mandatory vacations  

---

### Insider Threat Controls

| Control | Purpose |
|--------|--------|
| Mandatory vacation | Detect fraud |
| Job rotation | Reduce knowledge silos |
| Monitoring | Catch abuse |
| SoD | Prevent single-person compromise |

---

## 📊 Operational Metrics

| Metric | Meaning |
|-------|--------|
| MTTD | Time to detect |
| MTTR | Time to respond |
| MTBF | Mean Time Between Failures (repairable systems) |
| MTTF | Mean Time To Failure (non-repairable systems) |

Availability = MTBF / (MTBF + MTTR)
Higher MTBF + Lower MTTR = Higher availability
