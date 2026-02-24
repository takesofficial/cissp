# <p align=center>Domain 7 - Security Operations</p>

## 🚨 Elevator Pitch  
Keep security running day to day and respond when things go wrong. Domain 7 is about **operating**, **monitoring**, **responding**, and **recovering**. This is where incidents happen, alerts fire, people make mistakes, and processes either save you or sink you.

**Detect fast, respond correctly, recover cleanly, and learn afterward.**

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

## 🧬 Forensics Basics  
Preservation first, investigation second. Documentation matters as much as technical skill. Volatile data is prioritized. Integrity must always be provable. Preserve, collect, analyze, and present digital evidence in a legally defensible way.  

> **🚨 Never analyze original evidence; always work on a verified copy.**

- 🧾 **Chain of Custody**
  - Document every person who handled the evidence  
  - Record: who, when, where, why, and how  
  - Must be continuous and traceable  
  - Broken chain = evidence may be inadmissible  

- ⚡ **Order of Volatility**
  Collect most volatile data first (data that disappears fastest):
  1. CPU registers / cache  
  2. RAM  
  3. Network connections / processes  
  4. Disk data  
  5. Logs / archival media  

  👉 If you power off too early, volatile evidence is lost forever.

- 💽 **Forensic Imaging**
  - Create a **bit-for-bit (forensic) copy**
  - Includes deleted space and slack space  
  - Use write blockers to prevent modification  
  - Work only on the image, never the original  

- 🔎 **Integrity Verification**
  - Hash evidence before and after imaging  
  - Matching hashes prove integrity  
  - Common hashes: SHA-256  

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

- 1️⃣📦 **Full**
Complete copy of all data  
  - 🐢 Slow backup  
  - ⚡ Fastest restore  
  - 💾 Highest storage use  
  - 🏭 Heavy production impact  

- 2️⃣➕ **Incremental** 👉 Small backup, but restoring takes more steps.
Backs up only the files that changed since the last backup (full or incremental).
After backing them up, it marks them as "saved" (clears the archive bit).
  - ⚡ Fast backup  
  - 🐢 Slowest restore (must restore full + every incremental)  
  - 💾 Lowest storage use  
  - 🏭 Light production impact  
  - ⚠️ More restore steps = higher failure risk  

- 3️⃣📈 **Differential** 👉 Backup gets bigger each day, but restore is easier (full + latest differential).
Backs up only the files that changed since the last full backup.
It does not mark them as "saved" (archive bit stays set).
  - ⏳ Backup grows over time  
  - ⚡ Faster restore than incremental (full + latest differential only)  
  - 💾 Medium storage use  
  - 🎯 Lower RTO than incremental  

- 4️⃣🧩 **Synthetic** 👉 Less impact on production systems.
Creates a new full backup by combining a previous full backup with incremental or differential backups, without copying everything again from the original system.
  - ⏱️ Reduces production impact  
  - 📦 Minimizes backup window load

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
