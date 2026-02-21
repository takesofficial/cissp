# <p align=center>Domain 7 - Security Operations</p>

## 🚨 Elevator Pitch  
Keep security running day to day and respond when things go wrong.  
Domain 7 is about **operating**, **monitoring**, **responding**, and **recovering**.  
This is where incidents happen, alerts fire, people make mistakes, and processes either save you or sink you.

Think: **detect fast, respond correctly, recover cleanly, and learn afterward.**

---

## 🧠 Operations Mindset  

This domain is about **execution**, not theory.

- Design controls → Domains 1–3  
- Secure systems → Domains 4–5  
- **Run and defend systems → Domain 7**

When security fails, this domain decides the damage.

---

## 👀 Monitoring and Detection  

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

Key exam point: **alerts without response are useless**.

---

## 🚨 Incident Management  

### Incident vs Event  
- **Event** - Something happened  
- **Incident** - Security impact or policy violation  

Not every event is an incident.

---

## 🔥 Incident Response Lifecycle  

Standard flow CISSP expects:

1. **Preparation**  
2. **Detection and Analysis**  
3. **Containment**  
4. **Eradication**  
5. **Recovery**  
6. **Lessons Learned**

Order matters. Do not skip steps.

---

### 1️⃣ Preparation  
- IR plan  
- Roles and contacts  
- Tools and access  
- Training and exercises  

No plan = panic.

---

### 2️⃣ Detection and Analysis  
- Validate alerts  
- Identify scope  
- Preserve evidence  

Do not destroy evidence during analysis.

---

### 3️⃣ Containment  
- Short-term: stop the bleeding  
- Long-term: isolate and stabilize  

Examples: disable accounts, block IPs, isolate hosts.

---

### 4️⃣ Eradication  
- Remove malware  
- Close vulnerabilities  
- Patch systems  

Root cause must be addressed.

---

### 5️⃣ Recovery  
- Restore systems  
- Monitor for recurrence  
- Validate normal operations  

Return to production carefully.

---

### 6️⃣ Lessons Learned  
- What failed  
- What worked  
- What to improve  

This step improves future security posture.

---

## 🧪 Incident Classification  

Common categories:

- Malware  
- Unauthorized access  
- Data breach  
- Denial of service  
- Insider threat  
- Physical security incident  

Classification drives response and reporting.

---

## 🧬 Forensics Basics  

Purpose: preserve and analyze evidence.

### Key Rules  
- **Chain of custody** - document every handoff  
- **Order of volatility** - RAM first, then disk, then logs  
- **Imaging** - bit-for-bit copies  
- **Integrity** - hashes before and after  

Never analyze original evidence.

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

## 🕒 Business Continuity vs DR  

- **BCP** - keep business running  
- **DR** - restore IT systems  

BCP may operate without IT. DR restores IT.

---

## 🧪 Exercises and Testing  

**C-T-P-F** = **C**hecklist > **T**abletop > **P**arallel > **F**ull interruption (least > most disruptive)

- Tabletop exercises  
- Walkthroughs  
- Simulations  
- Full interruption tests  

Practice before real incidents.

---

## 🧠 Knowledge Management  

- Runbooks  
- Playbooks  
- Procedures  
- Documentation  

People leave. Knowledge must stay.

---

## 💽 RAID
- Mission-critical database: **RAID 10 (1+0):** (mirroring + striping; performance + redundancy; higher cost)
- Minimize risk of data loss in large array: **RAID 6:** (like RAID 5 but dual parity; tolerates 2 disk failures; more write penalty)
- Maximize storage efficiency: **RAID 5:** (striping + distributed parity; balanced; tolerates 1 disk failure; write penalty)
- **RAID 1:** **"1 = 1 mirror"** (mirroring; availability)
- Maximum performance, no redundancy: **RAID 0:** **"0 = 0 redundancy"** (striping; performance; any disk loss = data loss)
- ~~**RAID 2** and **RAID 3**~~ (effectively not used / rare)

---

## 🔄 Backup Operations  

⚠️ **Backups must be tested regularly. Untested backups are assumptions.**  
A backup only has value if it can be successfully restored.

### 💾 Backup Types

- 📦 **Full** - Complete copy of all data  
- ➕ **Incremental** - Changes since last backup (small backup, slower restore)  
- 📈 **Differential** - Changes since last full backup (grows over time, faster restore than incremental)  
- 🧩 **Synthetic** - Creates a new full backup from previous backups without re-copying all original data  

### 🗂 Rotation Strategy - GFS (Grandfather-Father-Son)
Used to balance retention, cost, and recovery flexibility.
Provides structured retention and versioning over time.

- 👶 **Son** = Daily backups  
- 👨 **Father** = Weekly backups  
- 👴 **Grandfather** = Monthly backups  

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

## 🧯 Operational Resilience  

- Redundancy  
- Fault tolerance  
- Graceful degradation  

Systems should fail safely, not catastrophically.

---

## 🧠 Exam Priorities Recap  

Recognize and apply quickly:

- Incident vs event  
- Incident response lifecycle order  
- Containment vs eradication  
- Evidence handling rules  
- Chain of custody and order of volatility  
- DR vs BCP distinction  
- RTO vs RPO usage  
- Privileged access controls  
- Patch and vulnerability management flow  
- Change management importance  
- Insider threat categories  
- Backup testing requirement  

---

## 📦 What Was Intentionally Removed (Too Long / Not Test-Critical)

- Vendor-specific IR tooling  
- Detailed malware reverse engineering  
- Advanced memory forensics  
- SOC staffing models  
- Deep threat hunting techniques  
- SIEM rule syntax  
- Cloud-native incident tooling internals  
- Regulatory breach notification timelines by country  

---

## 🔗 Useful Links / Mind Map  
[CISSP Domain 7 Destination Certification](https://youtu.be/ECUnAw3uDLY)
