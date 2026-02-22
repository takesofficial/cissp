# <p align=center>Domain 8 - Software Development Security</p>

## 🚨 Elevator Pitch  
Build security **into** software, not around it.  
Domain 8 is about integrating security throughout the **SDLC**, preventing vulnerabilities before deployment, and understanding what testing can and cannot find.

Think: design choices, secure coding, testing limits, and operational constraints.

---

## 🧠 DevSec Mindset  

Security failures in software are **design failures first**, coding failures second.

- Fixing bugs early is cheaper than fixing breaches later
- Automation helps, but **humans catch logic flaws**
- Availability and safety may outweigh confidentiality in some systems

---

## 🔄 Secure (S)SDLC
Security must be present in **every phase**.
**Security added late is weak security.**

1. **Requirements**
   - Security requirements
   - Abuse cases
   - Regulatory constraints

2. **Design**
   - Threat modeling
   - Trust boundaries
   - Architecture reviews

3. **Development**
   - Secure coding standards
   - Code reviews
   - Dependency management

4. **Testing**
   - SAST, DAST, IAST
   - Manual testing
   - Negative testing

5. **Deployment**
   - Secure configuration
   - Secrets management
   - Change control

6. **Maintenance**
   - Patch management
   - Monitoring
   - Vulnerability remediation


---

---

## 📈 Maturity Models (CMM, SAMM, IDEAL)
Maturity models show **how disciplined and repeatable** an organization’s processes are.  
They don’t just tell you whether something is “secure” — they tell you whether security (and delivery) is **predictable, governed, and improving** over time.

Use them to answer:
- Are we reacting to problems and relying on heroics?
- Or do we have standardized, measurable practices that improve continuously?

Security maturity matters because mature organizations handle incidents, change, and risk **consistently**—not improvisationally.

## ☑️ COMPARISON
| Model | Focus | Structure | Best Used For |
|-------|-------|----------|---------------|
| **CMM** | General process maturity | 5 Levels | Evaluating organizational discipline |
| **SAMM** | Secure software development | 4 Functions × 3 Practices × 5 Levels | Improving secure SDLC maturity |
| **IDEAL** | Change lifecycle | 5 Phases | Implementing structured improvement |


---

## 🪜 Capability Maturity Model (CMM) CMM = altitude (how mature you are)  
A useful way to spot CMM levels in questions: if you see "no documentation" and "no standard way of doing things," you’re looking at **Initial**. If you see "metrics, KPIs, and control," you're in **Managed** territory. If the organization is continuously refining and improving based on data and lessons learned, that's **Optimizing**.

### Levels

- 1️⃣ **Initial**  
Ad hoc, inconsistent, reactive. Success depends on individuals, not process.

- 2️⃣ **Repeatable**  
Basic project management exists. Teams can repeat earlier success, but it may still vary by group.

- 3️⃣ **Defined**  
Organization-wide standards exist. Processes are documented and institutionalized across teams.

- 4️⃣ **Managed**  
Processes are measured and controlled. Decisions become metrics-driven, not intuition-driven.

- 5️⃣ **Optimizing**  
Continuous improvement is the norm. The organization learns, adapts, and systematically refines process performance.

---

## 🛡️ Software Assurance Maturity Model (SAMM) by OWASP
Secure navigation (how mature secure software practices are). 
SAMM is purpose-built for **secure software development maturity**, it's like CMM, but focused specifically on software assurance practices.
4 Business Functions × 3 Security Practices × 5 Maturity Levels

SAMM is useful because it's modular: teams can assess maturity by practice and improve iteratively. Where CMM gives you a broad "how mature is the org," tells you **where your secure SDLC is strong or weak** (governance, build, verification, deployment).

### Business Functions

### 1️⃣ Governance
- Strategy & Metrics  
- Policy & Compliance  
- Education & Guidance  

### 2️⃣ Construction
- Threat Assessment  
- Secure Architecture  
- Secure Build  

### 3️⃣ Verification
- Security Testing  
- Code Review  
- Security Assessment  

### 4️⃣ Deployment
- Environment Hardening  
- Operational Enablement  
- Defect Management  

---

## 🔄 IDEAL Model (Improvement Lifecycle) = flight plan (how you improve on purpose)
IDEAL is not a maturity scorecard. It's a structured lifecycle for **driving improvement**. Shows up when the question is really asking: "How do we run a disciplined improvement program?" It's especially relevant when security has been fragmented and the organization needs a repeatable way to transform.

Acronym:
- **Initiating** - Identify need, build sponsorship  
- **Diagnosing** - Assess current state  
- **Establishing** - Define target state & roadmap  
- **Acting** - Implement changes  
- **Learning** - Measure outcomes and refine  

---

## 🧠 Threat Modeling (early risk reduction)

Purpose: identify threats **before code exists**.

Common methods:
- **STRIDE** - Categorize threats
- **DREAD** - Prioritize risk
- **PASTA** - Risk-based modeling
- **VAST** - Scalable modeling
- **Trike** - Risk-centric

Focus on:
- Trust boundaries
- Data flows
- Entry points
- Privileged operations

---

## 🧱 Secure Design Principles  
Encryption does not fix poor design.

- Least privilege  
- Defense in depth  
- Fail secure  
- Secure defaults  
- Input validation  
- Complete mediation  

---

## 🧬 Secure Coding Practices  

- Validate all input
- Encode all output
- Use parameterized queries
- Handle errors securely
- Log security events
- Avoid hardcoded secrets
- ORM promotes parameterized queries → reduces SQL injection risk

Frameworks help, but do not guarantee security.

---

## 🧪 Application Security Testing (what finds what)
**No single test finds everything.**

### SAST (Static)
- Source code analysis
- Finds logic and design flaws
- Early SDLC
- High false positives

### DAST (Dynamic)
- Tests running app
- Finds runtime issues
- Black-box
- Misses logic flaws

### IAST (Interactive)
- Combines static + dynamic
- Runs inside application
- Better context, more coverage


---

## 🧪 Testing Types

Automation misses business logic abuse.

- **Negative testing**
  - Invalid input
  - Boundary conditions
  - Input length, type, format

- **Interface testing**
  - API boundaries
  - Component interaction failures

- **Fuzzing**
  - Random or malformed input
  - Crashes and unexpected behavior

---

## 🔍 Code Review  

Manual review is irreplaceable.

Finds:
- Authorization flaws
- Privilege escalation
- Insecure logic
- Missing validation

Best done:
- Peer review
- Before deployment
- With security checklist

---

## 📦 Dependency and Supply Chain Risk  

Modern software depends on third parties.

Risks:
- Vulnerable libraries
- Abandoned projects
- Malicious packages

Controls:
- SBOM
- Version pinning
- Trusted repositories
- Patch monitoring

---

## 🧪 Test Environments (Never test _destructively_ in production.)

- **Development** - Fast, unsafe
- **Test** - Controlled
- **Staging** - Production-like
- **Production** - Restricted


---

## 🧠 Automation Limits (!!)

Automation cannot reliably detect:
- Business logic abuse
- Authorization bypass via workflow
- Context-dependent flaws

Human review is mandatory.

---

## ⚠️ ICS / SCADA Constraints (!!)
Industrial systems prioritize **availability and safety**.
**Do not scan or patch ICS aggressively.**
Active scanning and frequent patching increase risk in ICS environments.

Characteristics:
- Fragile systems
- Long lifecycles
- Legacy protocols
- Limited patch windows

Security priorities:
- Availability > integrity > confidentiality
- Monitoring over prevention
- Change control is critical

---

## 🔐 Secure Configuration and Secrets  

- Secure defaults
- Least functionality
- Secrets stored outside code
- Rotate credentials

Hardcoded secrets = instant fail.

---

## 🧾 Change and Release Management  

- Approved changes only
- Rollback plans
- Segregation of duties
- Logging and validation

Unauthorized changes = security incidents.

---

## 🧠 Exam Priorities Recap  

Recognize and apply quickly:

- Security in every SDLC phase  
- Threat modeling before coding  
- SAST vs DAST vs IAST  
- Negative vs interface vs fuzz testing  
- Automation limits  
- Manual code review value  
- Dependency risk awareness  
- ICS availability-first mindset  
- Secure configuration and secrets handling  

---

## 📦 What Was Intentionally Removed (Too Long / Not Test-Critical)

- Language-specific coding examples  
- Detailed OWASP Top 10 walkthroughs  
- CI/CD pipeline tooling  
- Container hardening deep dives  
- Advanced exploit development  
- Secure compiler internals  

---

## 🔗 Useful Links / Mind Map  
[CISSP Domain 8 Destination Certification](https://www.youtube.com/watch?v=ZK_S3Z5r6dM)
