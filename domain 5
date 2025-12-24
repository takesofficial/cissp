# <p align=center>Domain 5 - Identity and Access Management (IAM)</p>

## 🚨 Elevator Pitch  
Make sure the **right subject** gets the **right access** to the **right object** at the **right time**, for the **right reason**, and that every action is **accountable**.  
Domain 5 is about identity lifecycle, authentication, authorization, access models, and preventing both abuse and accidents.

Think: who you are, how you prove it, what you’re allowed to do, and how it’s monitored.

---

## 🧠 IAM Mindset  

Always separate **identity**, **authentication**, and **authorization**.

- Identity answers **who**  
- Authentication answers **prove it**  
- Authorization answers **what you can do**  
- Accountability answers **what you did**

IAM failures usually cause **data breaches**, not outages.

---

## 🔐 AAA (+ Auditing)

The IAM lifecycle.

- **Identification** - Claiming an identity (username, ID)
- **Authentication** - Proving identity
- **Authorization** - Permissions granted
- **Accountability** - Actions tied to identity
- **Auditing** - Logs reviewed and retained

Exam trap: authentication ≠ authorization.

---

## 🧾 Identity Lifecycle  

Access must change as people and systems change.

1. **Provisioning** - Create identity and grant access
2. **Review** - Validate access periodically
3. **Modification** - Role or responsibility change
4. **Deprovisioning** - Remove access immediately

Key exam phrase: **joiner / mover / leaver**.

---

## 👥 Subjects and Objects  

- **Subject** - Active entity (user, process, service, device)
- **Object** - Passive resource (file, database, system)

Access control always mediates **subject → object**.

---

## 🪪 Authentication Factors  

Authentication is based on **factors**, not methods.

- **Something you know** - Password, PIN
- **Something you have** - Token, smart card
- **Something you are** - Biometrics
- **Something you do** - Behavior (keystrokes)
- **Somewhere you are** - Location

### MFA  
- Uses **two or more different factors**
- Two passwords ≠ MFA

---

## 🧬 Authentication Methods  

- **Passwords** - Weak alone, still common
- **Tokens** - Hardware or software
- **Smart cards** - Certificate-based auth
- **Biometrics** - Fingerprint, iris, face
- **Certificates** - Strong identity binding

Biometrics trade-off:
- Cannot be revoked
- False acceptance vs false rejection

---

## 🧠 Biometrics Metrics (exam favorites)

- **FAR** - False Acceptance Rate (security risk)
- **FRR** - False Rejection Rate (usability issue)
- **CER** - Crossover Error Rate (equal FAR/FRR)
- **Enrollment** - Initial biometric capture

Security prefers **low FAR**, users prefer **low FRR**.

---

## 🧱 Access Control Models  

### Mandatory Access Control (MAC)
- System-enforced
- Labels and clearances
- No user discretion
- Government environments

### Discretionary Access Control (DAC)
- Owner controls access
- Flexible, weak
- Common in filesystems

### Role-Based Access Control (RBAC)
- Permissions tied to roles
- Scales well
- Best answer for enterprises

### Rule-Based Access Control
- Decisions based on rules
- Often used in firewalls

### Attribute-Based Access Control (ABAC)
- Uses attributes (user, resource, environment)
- Very flexible, complex
- Used in zero trust architectures

---

## 🧭 Least Privilege and Need-to-Know  

- **Least privilege** - minimum access required
- **Need-to-know** - access only if required for task

These apply to:
- Users
- Admins
- Services
- Applications

Over-privileged accounts = exam red flag.

---

## 🔑 Privileged Access  

### Privileged Accounts
- Admins, root, service accounts
- High risk, high impact

### Controls
- Separate admin accounts
- MFA everywhere
- Just-in-time access
- Session logging
- Password vaults

### PAM / PIM
- **PAM** - Privileged Access Management
- **PIM** - Privileged Identity Management

Exam angle: limit standing admin rights.

---

## 🔄 Federation and SSO  

### Federation
- Trust relationship between organizations
- One identity, multiple domains

### Single Sign-On (SSO)
- Authenticate once, access many systems

### Identity Roles
- **IdP** - Identity Provider
- **SP** - Service Provider

Protocols:
- **SAML**
- **OAuth**
- **OpenID Connect**

Exam trap: SSO increases convenience, not security by itself.

---

## 🌍 Extended Identity  

Used across partners and cloud services.

Flow:
- Organization acts as **IdP**
- Partners act as **Service Providers**
- Trust is established via standards

Common in SaaS ecosystems.

---

## 🧪 Account Types  

- **User accounts**
- **Service accounts**
- **Shared accounts** (avoid)
- **Guest accounts**
- **Emergency / break-glass accounts**

Break-glass:
- Rare use
- Strong controls
- Monitored
- Documented

---

## 🧾 Access Reviews and Auditing  

- Periodic access reviews
- Owner approval
- Logging and monitoring
- Separation of duties enforced

Auditors never accept risk.

---

## 🧠 Identity Proofing  

Before issuing credentials:
- Verify identity
- Match assurance level to risk

Higher risk = stronger proofing.

---

## ⚠️ IAM Threats  

- Credential stuffing
- Password reuse
- Privilege creep
- Orphaned accounts
- Insecure APIs
- Over-permissive roles

Most breaches start with IAM failure.

---

## 🧠 Exam Priorities Recap  

Recognize and apply quickly:

- Difference between identification, authentication, authorization
- MFA factor types
- RBAC vs DAC vs MAC vs ABAC
- FAR vs FRR vs CER
- Least privilege everywhere
- Admin account separation
- PAM / PIM purpose
- Federation roles (IdP vs SP)
- Identity lifecycle (joiner/mover/leaver)
- IAM as primary breach vector

---

## 📦 What Was Intentionally Removed (Too Long / Not Test-Critical)

- Vendor-specific IAM platforms
- Detailed OAuth token flows
- Kerberos ticket internals
- Password hashing algorithms
- Biometric sensor hardware
- Country-specific identity regulations
- Deep zero trust framework mappings
- API gateway implementation details

---
## 🔗 Useful Links / Mind Map  
[CISSP Domain 5 Destination Certification](https://www.youtube.com/watch?v=WBlQQ6qTlGI)
