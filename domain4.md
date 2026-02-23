# <p align=center>Domain 4 - Communication and Network Security</p>

## 🚨 Elevator Pitch  
Move data safely from A to B.   Domain 4 is about how data travels across networks, how networks are designed, and how security controls are applied to prevent interception, manipulation, and disruption.  
Think: protocols, segmentation, secure architecture, and controlling trust across connections.

---

## 🌐 Networking Mindset  

Always think in **flows, trust boundaries, and exposure**.

- **Networks exist to move data** - security exists to control how and where.
- **Every connection is a potential attack path**.
- **Segmentation reduces blast radius**.
- **Encryption protects data in motion, not endpoints**.
- **Availability matters as much as confidentiality**.

Manager view: reduce business risk, not maximize packet filtering.

---

## 📶 OSI Model
| # | Mnemonic | OSI Layer      | Example        | Phrase  | PDU      |
|---|----------|---------------|----------------|---------|----------|
| 1 | **P**lease   | Physical      | Hardware       | **D**on't   | Data     |
| 2 | **D**o       | Data          | MAC            | **D**on't   | Data     |
| 3 | **N**ot      | Network       | IP             | **D**on't   | Data     |
| 4 | **T**hrow    | Transport     | TCP/UDP        | **S**top    | Segments |
| 5 | **S**ausage  | Session       | Connections    | **P**ouring | Packets  |
| 6 | **P**izza    | Presentation | Encryption     | **F**ree    | Frames   |
| 7 | **A**way     | Application  | HTTPS / DNS    | **B**eer    | Bits     |

- Place controls and failures at the correct layer.
- Troubleshooting questions almost always map to OSI.

---

## 🧭 TCP/IP Model (real-world view)

- **Network Interface** - Physical + Data Link  
- **Internet** - IP, ICMP  
- **Transport** - TCP, UDP  
- **Application** - Everything user-facing

OSI = learning model  
TCP/IP = implementation model

---

## 📡 Network Types

- **LAN** - Local, high speed, controlled  
- **WAN** - Long distance, higher latency, leased lines  
- **MAN** - City-scale  
- **PAN** - Personal (Bluetooth, NFC)  
- **CAN** - Campus network  
- **SAN** - Storage Area Network (block-level storage)

Exam angle: WAN = higher risk, lower control.

---

## 🚄 MPLS (Multiprotocol Label Switching)

MPLS is used in **WAN environments** to control traffic paths.

Key behavior:
- **First router decides the path**
- Packet is given a **label**
- All following routers **forward based on the label**
- No per-hop routing decisions

Why this matters:
- Faster forwarding  
- Predictable paths  
- Better traffic engineering  

Exam hook:  
**MPLS = first router thinks, the rest obey**

---

## 🧱 Network Topologies

- **Bus** - Single backbone, legacy  
- **Star** - Central switch, most common  
- **Ring** - Token passing, legacy  
- **Mesh** - Redundancy, high availability  
- **Hybrid** - Real-world mix

Availability increases with redundancy.

---

## 🔌 Network Devices (who does what)

- **Hub** - Layer 1, repeats everything (insecure)  
- **Switch** - Layer 2, MAC-based forwarding  
- **Router** - Layer 3, IP routing  
- **Firewall** - Enforces security policy  
- **Proxy** - Application-level mediation  
- **Load balancer** - Availability and performance  
- **IDS/IPS** - Detects or blocks malicious traffic  
- **WAF** - Protects web applications

Exam trap: switches do NOT enforce security policy by default.

---

## 🔐 Secure Network Architecture

### Segmentation Types

- **Physical segmentation** - Separate hardware  
- **Logical segmentation** - VLANs, VRFs  
- **Microsegmentation** - Host or workload level controls

Goal: limit lateral movement.

---

## 🧠 Software-Defined Networking (SDN)

SDN separates **decision-making** from **packet forwarding**.

### SDN Planes

- **Data Plane**
  - Forwards packets  
  - Lives on switches and routers  

- **Control Plane**
  - Makes forwarding decisions  
  - Centralized in SDN controller  

- **Application Plane**
  - Defines network intent and policy  
  - Talks to controller via APIs  

Why this matters:
- Centralized control = efficiency  
- Centralized control = high-value target  

Exam angle:
- **Compromise of the control plane impacts the entire network**
- SDN increases power **and** risk

---

## 🧩 VLANs and Trunking

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

Controls who can connect and under what conditions.

- Device posture checks  
- Authentication before access  
- Quarantine networks  

Exam angle: NAC is **preventive and detective**.

---

## 📜 Core Network Protocols (recognize purpose)

### IP and Support
- **IP** - Logical addressing  
- **ICMP** - Errors and diagnostics (ping)  
- **ARP** - Maps IP to MAC (spoofable)  

### Transport
- **TCP** - Reliable, ordered, slower  
- **UDP** - Fast, connectionless, unreliable  

### Application (examples)
- **HTTP/HTTPS**  
- **FTP / SFTP**  
- **SMTP / POP3 / IMAP**  
- **DNS**  
- **SNMP**  
- **NTP**  

Exam mindset: insecure protocols still exist, security wraps them.

---

## 🔑 Ports You Should Instantly Recognize

- 20 - FTP (data active mode)
- 21 - FTP (control)
- 22 - SSH
- 23 - Telnet
- 25 - SMTP
- 49 - TACACS+
- 53 - DNS
- 67 - DHCP (server)
- 68 - DHCP (client)
- 80 - HTTP
- 88 - Kerberos
- 110 - POP3
- 123 - NTP
- 137 - NetBIOS Name Service
- 138 - NetBIOS Datagram Service
- 139 - NetBIOS Session Service
- 143 - IMAP
- 161 - SNMP
- 162 - SNMP Trap
- 389 - LDAP
- 443 - HTTPS
- 445 - SMB
- 636 - LDAPS
- 989 - FTPS (data)
- 990 - FTPS (control)
- 993 - IMAPS
- 995 - POP3S
- 1812 - RADIUS (authentication)
- 1813 - RADIUS (accounting)
- 3389 - RDP

You do not need all of them, just the common ones.

---

## 🔒 Secure Communication

### Encryption in Transit

- **TLS** - Primary control for data in motion  
- **IPsec**  
  - Transport mode - host to host  
  - Tunnel mode - network to network  

### VPN Types

- **Site-to-site** - Network level trust  
- **Remote access** - User to network  
- **Clientless** - Browser based  

VPNs protect confidentiality, not endpoint compromise.

---

## 📛 Wireless Security

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

DNS is critical infrastructure.

Threats:
- Cache poisoning  
- Spoofing  
- Amplification attacks  

Controls:
- **DNSSEC** - Integrity and authenticity  
- Logging and monitoring  
- Redundancy  

---

## 🧯 Firewalls (conceptual, not vendor)

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

- **DoS / DDoS** - Availability attack  
- **Man-in-the-middle** - Confidentiality and integrity  
- **Replay attacks** - Lack of freshness  
- **Spoofing** - Identity deception  
- **Sniffing** - Unencrypted traffic capture  

Best defense often involves **architecture**, not tools.

---

## 🕸️ WAN Availability and Resilience

WAN security prioritizes **availability and predictability**.

Key concepts:
- Redundant links  
- Diverse physical paths  
- Failover and load sharing  
- SLA-driven design  

Exam mindset:
- WAN outages = business outages  
- Availability controls matter as much as encryption  
- Architecture decisions often beat filtering rules  

---

## 🧠 Exam Priorities Recap  

Recognize and apply quickly:

- OSI layers and common examples  
- TCP vs UDP use cases  
- Difference between switch, router, firewall, proxy  
- Segmentation as a risk-reduction tool  
- Encryption for data in transit  
- VPN types and use cases  
- Wireless threats and protections  
- Why DNS and ICMP matter  
- Availability-focused thinking (DDoS, redundancy)  

---

## 📦 What Was Intentionally Removed (Too Long / Not Test-Critical)

- Vendor-specific firewall syntax  
- Routing protocol deep dives (OSPF metrics, BGP path selection)  
- Packet-level Wireshark analysis  
- RF physics and antenna design  
- Advanced multicast tuning  
- Full IPv6 transition mechanics  
- Detailed SDN controller architectures  
- Carrier-grade WAN engineering  

---

## 🔗 Useful Links / Mind Map  
[CISSP Domain 4 Destination Certification](https://youtu.be/KpULwJNlX9g)
