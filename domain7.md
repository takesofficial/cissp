# <p align=center>Domain 7 - Security Operations</p>

## 🚨 Elevator Pitch  
Keep security running day to day and respond when things go wrong. Domain 7 is about **operating**, **monitoring**, **responding**, and **recovering**. This is where incidents happen, alerts fire, people make mistakes, and processes either save you or sink you.

Detect fast, respond correctly, recover cleanly, and learn afterward.

---

## 🧠 Operations Mindset  

This domain is about **execution**, not theory.

- Design controls > Domains 1-3  
- Secure systems > Domains 4-5  
- **Run and defend systems > Domain 7**

When security fails, this domain decides the damage.

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

---

### Monitoring Quick Reference

Visibility without response = wasted telemetry.

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

Not every event is an incident.

---

## 🔥 Incident Response Lifecycle  

1. **Preparation**  
2. **Detection and Analysis**  
3. **Containment**  
4. **Eradication**  
5. **Recovery**  
6. **Lessons Learned**

Order matters. Do not skip steps.

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

Never jump straight to eradication. Never skip lessons learned.

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

### Malware Response

Detect > Isolate > Analyze > Eradicate > Restore > Review

Never skip isolation.

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

```
Break early in the chain = prevent full compromise.
```


---

## 🧬 Forensics Basics

You can find more details here: [RFC 3227](https://www.rfc-editor.org/rfc/rfc3227). Preserve first. Analyze later. Never touch originals.  
🚨 **Golden rule:** Never analyze original evidence. Always image first.


| Concept | Core Rule | What You Do | Why It Matters |
|--------|-----------|-------------|-----------------------------|
| Chain of Custod | Every handoff must be documented | Record who, when, where, why, how | Broken chain = evidence may be inadmissible |
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

Failures here cause most breaches.

---

### Privileged Access  
- Separate admin accounts  
- MFA everywhere  
- Logging and monitoring  
- Just-in-time access  

Privileged misuse = high impact.

---

## 🔄 Change and Configuration Management  

Changes introduce risk.

### Change Types  
- Standard  
- Normal  
- Emergency  

All changes require:
- Approval  
- Documentation  
- Rollback plan  

Unauthorized changes = security incident.

---

## 🧰 Patch and Vulnerability Management  

### Patch Management  
- Identify  
- Test  
- Deploy  
- Verify  

Delays increase risk exposure.

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

DR is technical. BCP is business.

---

### IR vs DR vs BCP

IR handles security events. DR restores systems. BCP keeps operations alive.

| Discipline | Focus |
|-----------|------|
| Incident Response | Stop attack |
| Disaster Recovery | Restore IT |
| Business Continuity | Keep business running |

---

## 🕒 Business Continuity vs DR  

- **BCP** - keep business running  
- **DR** - restore IT systems  

BCP may operate without IT. DR restores IT.

---

## 🧪 Exercises and Testing  

Practice before real incidents.
**C-T-P-F** = **C**hecklist > **T**abletop > **P**arallel > **F**ull interruption (least > most disruptive)

- Tabletop exercises  
- Walkthroughs  
- Simulations  
- Full interruption tests  

---

## 🧠 Knowledge Management  

- Runbooks  
- Playbooks  
- Procedures  
- Documentation  

People leave. Knowledge must stay.

---

## 💽 RAID (Availability vs Performance vs Cost)

RAID 2 and RAID 3 are effectively obsolete and ignored.

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

## 🧯 Operational Resilience  

- Redundancy  
- Fault tolerance  
- Graceful degradation  

Systems should fail safely, not catastrophically.

---

## 📊 Operational Metrics

Lower is better.

| Metric | Meaning |
|-------|--------|
| MTTD | Time to detect |
| MTTR | Time to respond |

---

## 🔗 Useful Links / Mind Map  
[CISSP Domain 7 Destination Certification](https://youtu.be/ECUnAw3uDLY)
