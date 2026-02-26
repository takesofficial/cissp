# <p align=center>Domain 8 - Software Development Security</p>

## 🚨 Elevator Pitch  
Build security into software, not around it. Domain 8 focuses on integrating security throughout the **software development lifecycle (SDLC)** to reduce risk before deployment. It covers secure design, secure coding practices, application testing, and the operational realities that shape how software can be protected in production.

The emphasis is on preventing vulnerabilities early through proper requirements, architecture, and development practices, understanding the strengths and limitations of automated testing, and recognizing when human review is required. The domain also addresses environments where availability and safety outweigh confidentiality, such as ICS/SCADA systems, and highlights why design decisions matter more than tools in determining long-term security outcomes.

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
| Phase | Security Activities | Hook |
|------|---------------------|-----------|
| **Requirements** | Security requirements, abuse cases | Security starts here |
| **Design** | Threat modeling, trust boundaries | Design flaws > code flaws |
| **Development** | Secure coding, dependency mgmt | Humans catch logic |
| **Testing** | SAST, DAST, IAST, negative tests | No tool finds everything |
| **Deployment** | Secure config, secrets handling | Misconfig = breach |
| **Maintenance** | Patching, monitoring | Security never ends |

---

## 📈 Maturity Models (CMM, SAMM, IDEAL)
Maturity models show **how disciplined and repeatable** an organization's processes are.  
They don't just tell you whether something is "secure" — they tell you whether security (and delivery) is **predictable, governed, and improving** over time.

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

## 🪜 Capability Maturity Model Integration (CMMI) altitude (how mature you are)  

CMMI (Capability Maturity Model Integration) measures how mature an organization’s processes are, not how skilled individual people are. It shows whether work succeeds because of heroes or because of repeatable systems. A practical way to recognize CMMI levels is to look at how work is executed, measured, and improved. When processes are informal, undocumented, and success depends on individual effort, the organization is at Initial. When work is planned, tracked, and controlled using defined objectives and basic metrics, it has reached Managed. When performance data is actively used to refine processes, remove inefficiencies, and drive continuous improvement rather than just maintain control, the organization is operating at Optimizing.

### Levels (Integrated Model)

| Level | Name | Process Characteristics | Organizational Behavior | Mental State | Hook |
|-------|------|------------------------|-------------------------|-------------|-----------|
| 1️⃣ | **Initial** | Ad hoc, chaotic, unpredictable | Success depends on individuals | Chaos | No consistent processes |
| 2️⃣ | **Managed** | Plans and requirements are documented, executed, tracked | Basic project discipline exists | Controlled | Processes are repeatable |
| 3️⃣ | **Defined** | Standardized and documented organization-wide | Processes institutionalized across teams | Standardized | Formal policies and procedures |
| 4️⃣ | **Quantitatively Managed** | Process performance measured + controlled | Decisions driven by metrics and statistical techniques | Data-driven | Use metrics to manage quality |
| 5️⃣ | **Optimizing** | Continuous process improvement based on measurement | Proactive refinement and innovation | Continuous improvement | Lessons learned drive evolution |

---

## 🛡️ Software Assurance Maturity Model (SAMM) by OWASP
Secure navigation (how mature secure software practices are). SAMM is purpose-built for **secure software development maturity**, it's like CMM, but focused specifically on software assurance practices.
4 Business Functions × 3 Security Practices × 5 Maturity Levels

SAMM is useful because it's modular: teams can assess maturity by practice and improve iteratively. Where CMM gives you a broad "how mature is the org," tells you **where your secure SDLC is strong or weak** (governance, build, verification, deployment).

### 🛡️ Business Functions (Secure SDLC Maturity)

| Function | What It Covers | Core Practices | Primary Goal | Mental Model | Hook |
|---------|----------------|---------------|--------------|-------------|-----------|
| **1️⃣ Governance** | Organization-wide security direction | Strategy & Metrics · Policy & Compliance · Education & Guidance | Define expectations and build security culture | Direction | Sets the rules and trains people |
| **2️⃣ Construction** | Building software securely | Threat Assessment · Secure Architecture · Secure Build | Prevent vulnerabilities during design and development | Prevention | Design flaws beat code flaws |
| **3️⃣ Verification** | Proving security actually works | Security Testing · Code Review · Security Assessment | Find weaknesses before release | Validation | Humans + tools validate controls |
| **4️⃣ Deployment** | Running software securely in production | Environment Hardening · Operational Enablement · Defect Management | Maintain security after release | Sustainment | Security doesn’t stop at go-live |

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

Threat modeling happens **before coding** by analyzing architecture, data flows, and trust boundaries. Design flaws beat code flaws.
Always focus on: Trust boundaries, data flows, entry points, privileged operations  

| Method | Core Purpose | What It Emphasizes | Hook |
|--------|-------------|-------------------|-----------|
| Ⓜ️ STRIDE | Categorize threats | Spoofing, Tampering, Repudiation, Info disclosure, DoS, Elevation | Think attacker techniques |
| 💀 DREAD | Prioritize risk | Damage, Reproducibility, Exploitability, Affected users, Discoverability | Ranking and scoring |
| 🍝  PASTA | Risk-driven modeling | Business impact + attacker paths | Business-context threats |
| 🏴‍☠️ VAST | Scalable modeling | Enterprise-wide automation | DevOps-friendly |
| 🦖 Trike | Risk auditing | Assets + trust boundaries | Asset-first thinking |

---

## 🌐 OWASP Top 10

The OWASP Top 10 is an industry-recognized awareness document identifying the most critical security risks to web applications. It is risk-based, updated periodically, and widely used to guide secure coding practices, security testing, and application security programs. It is not a compliance framework, but a developer-focused risk prioritization reference.

Official site: https://owasp.org/www-project-top-ten/

| # | Category | What It Means (Managerial View) | Typical Root Cause |
|---|-----------|---------------------------------|-------------------|
| 1 | 🔓 Broken Access Control | Users can access data or functions they should not | Missing authorization checks |
| 2 | 🔐 Cryptographic Failures | Sensitive data exposed due to weak or missing encryption | Improper crypto implementation |
| 3 | 💉 Injection | Untrusted input executed as commands or queries | Lack of input validation / parameterization |
| 4 | 🧱 Insecure Design | Security not built into architecture | Missing threat modeling / secure patterns |
| 5 | ⚙️ Security Misconfiguration | Default settings or misconfigured services expose systems | Poor hardening |
| 6 | 📦 Vulnerable & Outdated Components | Using libraries with known vulnerabilities | Lack of patching / dependency management |
| 7 | 🪪 Identification & Authentication Failures | Broken login/session management | Weak authentication controls |
| 8 | 🔁 Software & Data Integrity Failures | Trusting unverified updates or CI/CD pipelines | Missing integrity validation |
| 9 | 📊 Security Logging & Monitoring Failures | Attacks not detected or investigated | Insufficient logging / alerting |
| 10 | 🌐 Server-Side Request Forgery (SSRF) | Server abused to access internal resources | Improper URL/request validation |

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

### DAST (Dynamic) like 
- Tests running app
- Finds runtime issues
- Black-box
- Misses logic flaws

### IAST (Interactive)
- Combines static + dynamic
- Runs inside application
- Better context, more coverage

---

### SAST vs DAST vs IAST

| Method | Runs Where | Finds | Misses | SDLC Stage | Hook |
|--------|-----------|------|--------|-----------|------|
| SAST | Source code | Logic + design flaws | Runtime issues | Early | High false positives |
| DAST | Running app | Runtime issues | Business logic | Late | Black-box |
| IAST | Inside app | Both | Some logic | Mid | Best context |

---

## 🧪 Testing Types

Automation misses business logic abuse.

| Type | What It Finds | Automation? | Hook |
|------|--------------|------------|------|
| Negative | Invalid input paths | Partial | Boundary abuse |
| Interface | Component failures | Partial | API gaps |
| Fuzzing | Crashes | Yes | Random input |

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

### Supply Chain Controls

| Control | Purpose |
|--------|--------|
| SBOM | Know what you ship |
| Version pinning | Prevent surprise upgrades |
| Trusted repos | Reduce malicious packages |
| Patch monitoring | Track exposure |

---

## 🧪 Environment Usage (Never test _destructively_ in production.)

| Environment | Characteristics | Risk |
|------------|----------------|------|
| Development | Fast, unsafe | High |
| Test | Controlled | Medium |
| Staging | Production-like | Low |
| Production | Restricted | Critical |

---

## 🧠 Automation Limits (!!)

Automation cannot reliably detect:
- Business logic abuse
- Authorization bypass via workflow
- Context-dependent flaws

Human review is mandatory.

---

## ⚠️ ICS / SCADA Constraints (Availability First)

Industrial control systems prioritize **availability and safety over security hardening**.  
Aggressive scanning or frequent patching can **cause outages or physical damage**.
IT protects data / ICS protects people and processes.

- 🚫 Do NOT aggressively scan ICS  
- 🚫 Do NOT patch casually  
- ✅ Prefer passive monitoring  
- ✅ Enforce strict change management  
- ✅ Segment networks (zones / conduits)  
- ✅ Plan patches during outages  
- ✅ Protect availability first  

### ICS / SCADA Security Reality

| Area | What It Means | Practical Impact | Hook |
|------|--------------|-----------------|-----------|
| Primary Goal | Keep systems running safely | Downtime can stop production or harm people | Availability beats everything |
| Priority Order | Availability > Integrity > Confidentiality | Different from IT environments | Safety-first mindset |
| System Fragility | Devices are sensitive to change | Scanning can crash controllers | Do NOT scan aggressively |
| Lifecycles | Decades-long deployments | Old OS and firmware remain in use | Legacy is normal |
| Protocols | Often insecure / proprietary | Little or no native auth/encryption | Compensating controls |
| Patch Windows | Rare and tightly controlled | Patching requires shutdown planning | No "Patch Tuesday" |
| Monitoring | Passive visibility preferred | Detect without touching systems | Monitor, don't probe |
| Change Control | Extremely strict | Every change is reviewed and scheduled | Governance is critical |
| Prevention Style | Limited inline blocking | IPS/firewalls may disrupt operations | Detection over prevention |
| Architecture | Flat networks common | Segmentation becomes high value | Zones and conduits |
| Human Safety | Physical consequences possible | Cyber incidents can become safety incidents | People > data |

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

## 🔗 Useful Links / Mind Map  
[CISSP Domain 8 Destination Certification](https://www.youtube.com/watch?v=ZK_S3Z5r6dM)
