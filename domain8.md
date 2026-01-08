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

## 🔄 Secure SDLC
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
