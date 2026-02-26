# <p align=center>Domain 4 - Communication and Network Security</p>

---

## 🧠 Mind Map
[CISSP Domain 4 Destination Certification](https://destcert.com/resources/cissp-domain-4-communication-and-network-security/) 

---

## 🚨 Elevator Pitch  
Move data safely from A to B. Domain 4 is about how data travels across networks, how networks are designed, and how security controls are applied to prevent interception, manipulation, and disruption. Think: protocols, segmentation, secure architecture, and controlling trust across connections.

---

## 🌐 Networking Mindset  

Networking security is about controlling how data moves and where trust begins and ends. Every connection increases risk. CISSP thinking focuses on reducing business impact through segmentation, encryption, and architecture - not chasing packets.

- **Every connection is a potential attack path**.
- **Segmentation reduces blast radius**.
- **Encryption protects data in motion, not endpoints**.

---

## 🧵 Transmission Media

Different cables and wireless technologies create different risks. Some are easy to tap, some resist interference, some travel farther. CISSP cares which media increases exposure and which reduces it.

### 🧷 Wired vs Wireless Transmission Media

| Media Type | Technology | Key Characteristics | Angle |
|------------|------------|--------------------|------------------|
| Wired | Twisted Pair (UTP/STP) | Common Ethernet cabling, limited distance (~100m). UTP more susceptible to EMI than STP. | Cheap and common, but vulnerable to interference and tapping |
| Wired | Coaxial | Older LAN and cable systems, better shielding than twisted pair | Legacy medium, improved shielding |
| Wired | Fiber Optic | Uses light instead of electricity, immune to EMI, hard to tap, supports long distances. Single-mode = long distance, multi-mode = shorter | **Best choice for long distance + EMI resistance** |
| Wireless | RF (Wi-Fi) | Radio-based communication | Easy interception, requires strong encryption |
| Wireless | Bluetooth | Short-range personal networking | Pairing and device trust risks |
| Wireless | NFC | Very short range communication | Physical proximity reduces but doesn’t eliminate risk |
| Wireless | Infrared | Line-of-sight communication | Limited range, niche use |

- **Fiber** = most secure physical medium (EMI immune, hard to tap)  
- **Wireless** = highest interception risk  
- Encryption + strong authentication are mandatory for wireless  
---

## 📶 OSI Model

OSI is a learning model used to place problems and controls at the right layer. On the exam, it helps you identify where failures occur and where security belongs.

| # | Mnemonic | OSI Layer      | Example        | Phrase  | PDU      |
|---|----------|---------------|----------------|---------|----------|
| 1 | **P**lease   | Physical      | Hardware       | **B**eer     | Bits     |
| 2 | **D**o       | Data Link     | MAC            | **F**ree   | Frames   |
| 3 | **N**ot      | Network       | IP             | **P**ouring | Packets  |
| 4 | **T**hrow    | Transport     | TCP/UDP        | **S**top | Segments |
| 5 | **S**ausage  | Session       | Connections    | **D**ata    | Data     |
| 6 | **P**izza    | Presentation  | Encryption     | **D**ata    | Data     |
| 7 | **A**way     | Application   | HTTPS / DNS    | **D**ata    | Data     |

- Place controls and failures at the correct layer.
- Troubleshooting questions almost always map to OSI.

---

## 🧭 TCP/IP Model (real-world view)

TCP/IP is how networks actually work. CISSP uses it to explain real-world traffic flow while OSI explains concepts.

- **Network Interface** - Physical + Data Link  
- **Internet** - IP, ICMP  
- **Transport** - TCP, UDP  
- **Application** - Everything user-facing

OSI = learning model  
TCP/IP = implementation model

---

## 🔀 Switching Methods

Internet = packet-switched network.

| Type | Description | Security View |
|------|------------|---------------|
| Circuit Switching | Dedicated path for duration of session | Predictable, less efficient |
| Packet Switching | Data split into packets, dynamic routing | More efficient, dominant model (Internet) |

---

## 📡 Network Types

Not all networks carry equal risk. LANs offer control. WANs rely on third parties. CISSP assumes longer distance equals higher exposure and lower ownership. WAN = highest exposure + least ownership. Always assume increased interception and availability risk.

| Network Type | Scope / Distance | Typical Use | Security Characteristics | Angle |
|--------------|------------------|-------------|--------------------------|------------------|
| **LAN** | Local building / floor | Office networks | High speed, high control | Lowest inherent risk |
| **WAN** | Long distance (ISP / leased lines) | Inter-site connectivity | Higher latency, third-party infrastructure | **Highest risk, lowest control** |
| **MAN** | City-wide | Metro networks | Moderate control, shared infrastructure | Between LAN and WAN |
| **PAN** | Personal range | Bluetooth, NFC | Very short range, device-level trust | Weak auth = easy compromise |
| **CAN** | Campus | Universities, enterprises | Multiple LANs under one org | Requires segmentation |
| **SAN** | Data center storage | Block-level storage | High performance, highly sensitive | Must be isolated and protected |

---

## 📢 Transmission Methods

Data can go to one device, many devices, or the closest device. CISSP focuses on how each method affects attack surface and availability.

| Method | Description | Typical Use | Angle |
|--------|------------|-------------|------------------|
| Unicast | One sender to one receiver | Normal client/server traffic | Default communication model |
| Broadcast | One sender to all devices in subnet | ARP, discovery protocols | Increases attack surface |
| Multicast | One sender to selected group | Streaming, routing updates | Efficient group delivery |
| Anycast | One sender to nearest identical destination | DNS, CDNs | Improves availability and performance |

- CDNs improve availability and reduce DDoS impact through distributed architecture.
- Broadcast increases exposure.
- Anycast improves resiliency and latency.

---

## 🚄 MPLS (Multiprotocol Label Switching)

MPLS is used in **WAN environments** to control traffic paths. MPLS predefines traffic paths to improve speed and predictability in WANs. CISSP views it as an availability and architecture feature, not a security control.

Key behavior:
- Packet is given a **label**
- All following routers **forward based on the label**

Why this matters:
- Faster forwarding  
- Predictable paths  
- Better traffic engineering  

---

## 🧱 Network Topologies

Topology describes how systems connect. More paths mean more resilience. CISSP values redundancy over simplicity.

- 🚌 **Bus** - Single backbone, legacy  
- ⭐ **Star** - Central switch, most common  
- 💍 **Ring** - Token passing, legacy  
- Ⓜ️ **Mesh** - Redundancy, high availability  

Availability increases with redundancy.

---

## 🔌 Network Devices (Who Does What)

Each device has a role. Switches move traffic. Firewalls enforce rules. IDS detects. IPS blocks. CISSP tests whether you understand responsibilities, not configurations.

- IDS = detect. IPS = block.
- WAF protects applications, not networks.

| Device | OSI Layer | Primary Function | Security Role |  Note |
|--------|-----------|------------------|---------------|-----------------|
| **Hub** | L 1 | Repeats all traffic to every port | None | Insecure, no filtering |
| **Switch** | L 2 | Forwards frames by MAC address | Minimal (port security only) | **Does NOT enforce security policy by default** |
| **Router** | L 3 | Routes packets by IP | Basic filtering (ACLs) | Connects networks |
| **Firewall** | L 3-7 | Enforces access policy | Preventive control | Core perimeter control |
| **Proxy** | L 7 | Application-level mediation | Hides clients, filters content | Full application awareness |
| **Load Balancer** | L 4 | Distributes traffic by IP + port | Availability | Fast, no app visibility |
| **Load Balancer** | L 7 | Routes by URL/headers/content | Availability + intelligence | Granular application routing |
| **IDS** | L 3-7 | Detects malicious activity | Detective | Alerts only |
| **IPS** | L 3-7 | Blocks malicious activity | Preventive | Inline enforcement |
| **WAF** | L 7 | Protects web apps (HTTP/S) | Prevents OWASP-style attacks | App-specific firewall |

- Port security (limit MAC addresses)
- Disable unused ports
- BPDU Guard
- DHCP Snooping
- Dynamic ARP Inspection (DAI)

---

## 🔐 Secure Network Architecture

Architecture limits damage before tools are even applied. Segmentation exists to stop attackers from moving sideways.

### Segmentation Types

- **Physical segmentation** – Separate hardware  
- **Logical segmentation** – VLANs, VRFs  
- **Microsegmentation** – Host or workload-level controls  

- **Zero Trust** – Assumes no implicit trust based on network location  
- **Defense in Depth** – Multiple overlapping controls across layers  

Goal: limit lateral movement and reduce blast radius.

---

## 🧠 Software-Defined Networking (SDN)

SDN separates centralized control from packet forwarding. A compromise of the control plane affects the entire network. SDN improves efficiency and agility, but also concentrates risk into a single high-value target.

### SDN Planes

- **Data Plane**
  - Forwards packets  
  - Lives on switches and routers  

- **Control Plane**
  - Makes forwarding decisions  
  - Centralized in SDN controller    

Why this matters:
- Centralized control = high-value target  

---

### 🧱 Trust Boundaries & DMZ

Security architecture is built around trust boundaries, where security controls change strength.
Compromise in DMZ should NOT equal compromise of internal network.

- **Trust Boundary** - Point where data moves between different trust levels
- **DMZ (Demilitarized Zone)** - Isolated network segment between internal network and untrusted networks (e.g., Internet)
- Public-facing systems (web, mail, DNS) belong in the DMZ
- Internal systems should NEVER be directly exposed
---

### East-West vs North-South Traffic

| Direction | Meaning | Example | Angle |
|-----------|---------|---------|-------------|
| North-South | Into / out of network | Internet > web server | Perimeter controls |
| East-West | Inside network | Server > database | Lateral movement risk |

---

## 🧩 VLANs and Trunking

VLANs separate traffic logically. Trunks carry many VLANs. CISSP focuses on misconfiguration risks and lateral movement.

- **VLAN** - Logical network separation  
- **Trunk** - Carries multiple VLANs  
- **Access port** - Single VLAN

Risks:
- VLAN hopping  
- Misconfigured trunks  

Controls:
- Disable unused ports  
- Native VLAN hardening  
- Port security  

---

## 🧪 Network Access Control (NAC)

NAC decides who connects and under what conditions and is both preventive and detective.

- 802.1X - Port-based network access control (often used with WPA2/WPA3 Enterprise)
- Device posture checks  
- Authentication before access  
- Quarantine networks  


---

## 🔐 AAA Protocol Roles

Authentication systems decide who gets access. CISSP focuses on where each protocol is used, not how to configure it.

| Protocol | Transport | Primary Use | Hook |
|----------|-----------|-------------|-----------------|
| RADIUS | UDP | Network access (Wi-Fi, VPN) | Auth + authz combined |
| TACACS+ | TCP | Device administration | Separates AAA functions |
| Kerberos | UDP/TCP | Enterprise SSO | Ticket-based authentication |

Quick rules:
- TACACS+ = network device admin  
- RADIUS = user network access  
- Kerberos = centralized authentication (no passwords on wire)

---
## 📜 Core Network Protocols (Recognize Purpose)

Protocols move data. Most were not designed securely. CISSP tests whether you recognize which ones need protection.

| Layer | Protocol | Primary Purpose | Security Consideration |  Angle |
|--------|----------|----------------|------------------------|------------------|
| Network | IP | Logical addressing and routing | No built-in security | Foundation of communication |
| Network | ICMP | Error reporting and diagnostics (ping, traceroute) | Can be abused for reconnaissance | Useful but often filtered |
| Network | ARP | Maps IP to MAC address | Vulnerable to spoofing | Enables MITM if unprotected |
| Transport | TCP | Reliable, ordered delivery | Connection-oriented | Used where reliability matters |
| Transport | UDP | Fast, connectionless delivery | No reliability guarantees | Used for speed-sensitive traffic |
| Application | HTTP | Web communication | Plaintext | Insecure without TLS |
| Application | HTTPS | Secure web communication | TLS encryption | Default secure web standard |
| Application | FTP | File transfer | Plaintext credentials | Replace with SFTP/FTPS |
| Application | SFTP | Secure file transfer over SSH | Encrypted | Preferred secure file transfer |
| Application | SMTP | Mail transfer | Spoofable without controls | Pair with SPF/DKIM/DMARC |
| Application | POP3 | Retrieve email | Plaintext unless secured | Use POP3S |
| Application | IMAP | Retrieve/manage email | Plaintext unless secured | Use IMAPS |
| Application | DNS | Name resolution | Spoofable / cache poisoning | DNSSEC adds integrity |
| Application | SNMP | Network management | v1/v2 insecure | Use SNMPv3 |
| Application | NTP | Time synchronization | Critical for logs & Kerberos | Time integrity matters |

---

## 🔑 Ports with Mnemonics

Ports identify services. CISSP expects instant recognition of common ones to understand attack paths.

| Emoji | Mnemonic | Port | Protocol | Service |
|-------|----------|------|----------|----------|
| 🦠 | FTP - Forget That Period | 20 | TCP | FTP Data (active) |
| 🦠 | FTP - Forget That Period | 21 | TCP | FTP Control |
| 🐢 | 2 Ninja Turtles (2+2 Shell) | 22 | TCP | SSH / SCP / SFTP |
| 🏀 | Jordan's Jersey - Tell It To The Net | 23 | TCP | Telnet |
| 🎄 | Santa Mail | 25 | TCP | SMTP |
| 🔐 | Device Admin | 49 | TCP | TACACS+ |
| 🧂 | Dad No SALT! You're | 53 | TCP/UDP | DNS |
| ♋ | DHCP Request | 67 | UDP | DHCP Server |
| ♋ | DHCP Response | 68 | UDP | DHCP Client |
| 👴 | Old person tired of HTTP | 80 | TCP | HTTP |
| ⛩️ | Kerberos Gate | 88 | TCP | Kerberos |
| 🍿 | POP Corn (with 110 kcal) | 110 | TCP | POP3 |
| ⏱️ | 1…2…3 Time | 123 | UDP | NTP |
| 💌 | I(1) LOVE(4) YOU(3) | 143 | TCP | IMAP4 |
| 🏛️ | MAP Rome | 161 | UDP | SNMP |
| 🏛️ | SNMP Trap | 162 | UDP | SNMP Trap |
| 📂 | Directory Access | 389 | TCP | LDAP |
| 🌍 | Secure Web | 443 | TCP | HTTPS |
| 🔑 | Key Exchange | 500 | UDP | ISAKMP / IKE |
| 🔒 | Secure LDAP | 636 | TCP | LDAPS |
| 🪢 | SUIDAR (reverse RADIUS) | 1812 | UDP | RADIUS Auth |
| 🪢 | SUIDAR (reverse RADIUS) | 1813 | UDP | RADIUS Accounting |

Remote administration:
- Telnet = insecure (plaintext)
- SSH = secure replacement
- Disable legacy remote protocols

---

## 🌍 IP Addressing, NAT, and PAT

Private addresses hide internal systems. NAT reduces visibility but does not equal security. Firewalls still matter.

### Private IP Ranges (Not Internet Routable)

| Range |
|-------|
| 10.0.0.0/8 |
| 172.16.0.0 - 172.31.255.255 |
| 192.168.0.0/16 |

---

### IPv6

- 128-bit addressing
- Larger address space
- Built-in IPsec support (optional in practice)
- No NAT required (conceptually)

---

### Address Translation

NAT hides internal addresses but does NOT replace firewall security.

| Technology | Purpose | View |
|------------|---------|-----------|
| NAT | Translates private to public IPs | Reduces exposure, **not security** |
| PAT | Multiple internal hosts share one public IP via ports | Conserves addresses |

---

## 🔒 Secure Communication

Encryption protects data while moving. CISSP stresses that encryption does not protect compromised endpoints.

### Encryption in Transit

- **TLS** - Primary control for data in motion  
- **IPsec**  
  - Transport mode - host to host  
  - Tunnel mode - network to network  

### Encryption Layer Comparison

| Technology | Layer | Protects |
|------------|-------|----------|
| MACsec | Layer 2 | Switch-to-switch |
| IPsec | Layer 3 | Host or network |
| TLS | Layer 7 | Application traffic |

### 🔐 VPN Types

VPNs protect **data in transit (confidentiality)**.  .

| VPN Type | Description | Typical Use | Angle |
|----------|-------------|-------------|-------------|
| Site-to-site | Connects entire networks together | Branch offices | Network-to-network trust |
| Remote access | Connects individual users to internal network | Remote employees | User authentication + endpoint risk |
| Clientless | Browser-based access (no VPN client) | Partner/vendor access | Limited capability, higher exposure |

---

### 🧭 VPN Traffic Modes

| VPN Mode | Description | Risk | Angle |
|----------|-------------|------|-----------|
| Full Tunnel | All traffic forced through VPN | Lower | Preferred. Prevents internet breakout |
| Split Tunnel | Only corporate traffic uses VPN | Higher | Allows data leakage via local internet |

VPNs do **NOT** protect compromised endpoints.

---

## 📛 Wireless Security

Wireless trades convenience for exposure. CISSP assumes interception unless strong authentication and encryption exist.

### Wi-Fi Standards

- **WEP** - Broken, never acceptable  
- **WPA/WPA2** - Improved, still vulnerable if misused  
- **WPA3** - Modern standard  

### Wireless Attacks

- Evil twin  
- Deauthentication  
- Rogue AP  
- Jamming  

Controls:
- Strong auth  
- Monitoring  
- Disable legacy protocols  

---

## 🧠 DNS Security

DNS is foundational. If compromised, everything breaks. CISSP treats DNS integrity as critical infrastructure.

Threats:
- Cache poisoning  
- Spoofing  
- Amplification attacks  

Controls:
- **DNSSEC** - Integrity and authenticity  
- Logging and monitoring  
- Redundancy  

---

### 📧 Email Security Controls (SPF / DKIM / DMARC)

Email authentication prevents spoofing and tampering. CISSP focuses on trust validation, not mail servers.

| Control | What It Does | Primary Security Goal | Hook |
|---------|--------------|----------------------|-----------------|
| SPF | Specifies which mail servers are authorized to send on behalf of a domain | Prevent sender spoofing | **Who may send email** |
| DKIM | Cryptographically signs outgoing messages | Ensure message integrity and authenticity | **Prove email was not altered** |
| DMARC | Defines policy for handling SPF/DKIM failures and provides reporting | Enforce authentication + visibility | **What to do when SPF/DKIM fail** |

---

## 🧯 Firewalls (conceptual, not vendor)

Firewalls enforce policy. Routers forward traffic. CISSP tests whether you understand this separation.

Types:
- Packet filtering  
- Stateful inspection  
- Application-aware  
- Next-gen firewalls  

Rule design:
- Default deny  
- Least privilege  
- Explicit allow rules  
- Logging enabled  

Exam trap: firewalls enforce policy, routers forward traffic.

---

## ⚠️ Network Attacks (recognize patterns)

Most network attacks exploit trust and visibility. CISSP prefers architectural prevention over reactive tools.

- **ARP poisoning** - Redirects traffic by falsifying ARP mappings (MITM)
- **DoS / DDoS** - Availability attack designed to exhaust resources
- **MAC flooding** - Overflows switch CAM table, forcing hub-like behavior
- **Man-in-the-middle (MITM)** - Intercepts and possibly alters communication (confidentiality & integrity impact)
- **Replay attacks** - Reuses captured transmissions due to lack of freshness controls
- **Spoofing** - Impersonates identity (IP, MAC, DNS, email, etc.)
- **Sniffing** - Captures unencrypted traffic

### DDoS Mitigation

- Rate limiting  
- Blackholing  
- Sinkholing  
- CDN / distributed architecture  
- Upstream ISP filtering  

Best defense often involves **architecture, segmentation, and redundancy - not just tools.**

---

## 🕸️ WAN Availability and Resilience

WAN resilience means assuming links will fail and designing so the business keeps running. Use redundancy, diverse paths, failover, and SLAs.

| Topic | Description | Angle |
|------|-------------|------------------|
| Redundant Links | Multiple WAN connections to avoid single points of failure | Availability beats a single "secure" link |
| Diverse Physical Paths | Circuits routed through different buildings/streets/providers | Prevents one cut from killing everything |
| Failover & Load Sharing | Automatic rerouting and traffic distribution | Design for failure, not perfection |
| SLA-Driven Design | Contracts define uptime, latency, recovery expectations | Business requirements drive architecture |
