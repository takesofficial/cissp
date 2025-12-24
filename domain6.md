# <p align=center>Domain 6 - Security Assessment and Testing</p>

## 🚨 Elevator Pitch  
Trust nothing without evidence.  
Domain 6 is about **verifying** that security controls exist, work as intended, and continue to work over time.  
You assess, test, audit, and measure security to prove risk is actually being reduced.

Think: **Are the controls there? Do they work? Can you prove it?**

---

## 🧠 Assessment Mindset  

This domain is about **validation**, not design.

- Design controls → Domain 1–3  
- Operate controls → Domain 7  
- **Verify controls → Domain 6**

Management wants assurance, not guesses.

---

## 🔍 Security Assessment vs Testing  

- **Assessment** - Broad evaluation of controls and posture  
- **Testing** - Hands-on verification that controls actually work

Exam trap: assessments are higher-level, tests are technical and specific.

---

## 🧪 Types of Security Testing  

### 🧫 Vulnerability Assessment  
- Identifies **known weaknesses**
- Uses scanners and tools
- No exploitation
- Safe and repeatable

### 🧨 Penetration Testing  
- Actively **exploits vulnerabilities**
- Simulates attacker behavior
- Requires authorization
- Higher risk, higher insight

### 🔁 Red Team / Blue Team  
- **Red team** - Attacker simulation
- **Blue team** - Defenders
- **Purple team** - Collaboration and learning

Exam angle: pentest proves exploitability, vuln scan does not.

---

## 📋 Test Planning and Scoping  

Before testing, define:

- Scope (what is tested)
- Rules of engagement
- Authorization
- Timing and impact limits
- Reporting expectations

Testing without approval = illegal.

---

## 🧾 Security Audits  

Audits verify **compliance**, not security strength.

- Internal audits
- External audits
- Regulatory audits
- Third-party audits

Auditors:
- Are independent
- Do not implement controls
- Do not accept risk

---

## 📊 Metrics and Measurements  

If you can’t measure it, you can’t manage it.

### Common Metrics  
- Number of vulnerabilities
- Mean time to detect (MTTD)
- Mean time to respond (MTTR)
- Patch compliance rate
- Control coverage

Metrics must be:
- Relevant
- Repeatable
- Actionable

---

## 🧱 Control Assessment  

Controls are evaluated by:

- Design effectiveness
- Operating effectiveness
- Consistency
- Coverage

Types of controls assessed:
- Administrative
- Technical
- Physical

---

## 🧾 Log Review and Monitoring  

Logs provide accountability and detection.

- Authentication logs
- Authorization failures
- Privileged access
- System changes
- Security events

Key exam point: **logs must be reviewed**, not just collected.

---

## 🧪 Test Coverage  

Testing should include:

- Systems
- Networks
- Applications
- Databases
- Cloud services
- IAM controls
- Physical security

Partial testing = blind spots.

---

## 🧬 Code Review and Static Testing  

### Static Application Security Testing (SAST)
- Reviews source code
- Finds logic flaws
- No execution required

### Dynamic Application Security Testing (DAST)
- Tests running applications
- Simulates attacks
- Black-box style

### Software Composition Analysis (SCA)
- Finds vulnerable libraries
- License issues

---

## 🔐 Cryptographic Testing  

Validate crypto usage, not math.

- Correct algorithms
- Strong key lengths
- Proper key management
- Secure modes
- Certificate validity

Exam angle: misconfiguration breaks crypto, not algorithms.

---

## 🧠 Security Assessment Tools  

- Vulnerability scanners
- Configuration compliance tools
- File integrity monitoring
- Network analyzers
- SIEM correlation

Tools support humans. They don’t replace judgment.

---

## 🧪 Environmental and Physical Testing  

- Fire suppression tests
- Power failover tests
- UPS and generator testing
- HVAC monitoring
- Access badge testing

Physical failures bypass all logical controls.

---

## 🔄 Continuous Monitoring  

Security is not point-in-time.

- Continuous control monitoring
- Automated alerting
- Regular reassessment
- Trend analysis

Best answer when asked how to maintain assurance over time.

---

## 🧾 Reporting and Remediation  

Reports must include:
- Findings
- Risk severity
- Evidence
- Recommendations

Remediation:
- Assigned owner
- Target date
- Retesting after fix

Unfixed findings = accepted risk (by management).

---

## ⚖️ Independence and Objectivity  

Assessments must be:
- Independent
- Objective
- Repeatable

You should not test your own work.

---

## 🧠 Exam Priorities Recap  

Recognize and apply quickly:

- Assessment vs testing
- Vulnerability scan vs penetration test
- Audit purpose and limitations
- Metrics that matter (MTTD, MTTR)
- Log review importance
- Continuous monitoring concept
- SAST vs DAST vs SCA
- Independence of assessors
- Authorization before testing
- Reporting and remediation lifecycle

---

## 📦 What Was Intentionally Removed (Too Long / Not Test-Critical)

- Tool-specific command syntax
- Vendor scan score calculations
- Deep exploit development techniques
- Full red team playbooks
- Regulatory audit checklists
- Custom SIEM rule writing
- Advanced threat hunting methodologies
- Detailed compliance mappings (SOC2, ISO clause-by-clause)

---

## 🔗 Useful Links / Mind Map  
[CISSP Domain 6 Destination Certification](https://youtu.be/A-aNmhB_WjM)
