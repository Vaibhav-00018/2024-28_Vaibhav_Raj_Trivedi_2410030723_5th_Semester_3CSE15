# SmartBranch 360 — Cisco Networking Virtual Internship

**Cisco-AICTE Virtual Internship Program 2026 | IILM University, Greater Noida**

---

This repository contains the complete internship deliverables for **SmartBranch 360: Enterprise Branch Network Design, Multi-Layer Security & Automated Assurance**, developed as part of the **Cisco-AICTE Virtual Internship Program 2026** in collaboration with the **Cisco Networking Academy** and **IILM University, Greater Noida, U.P.**

The repository includes the final academic internship report in PDF format, the viva/presentation slide deck in PDF format, complete technical documentation, Cisco Packet Tracer topology and device configurations, systematic multi-layer fault simulations, an automated Python network assurance engine, and official Cisco Networking Academy course completion credentials.

---

## 📑 Table of Contents

- [👤 Student Details](#-student-details)
- [📌 About the Internship](#-about-the-internship)
- [🌐 About SmartBranch 360](#-about-smartbranch-360)
- [🎯 Objectives](#-objectives)
- [⏱️ Internship & Project Timeline](#️-internship--project-timeline)
- [🗓️ Phase-wise Project Development](#️-phase-wise-project-development)
- [🏗️ Network Architecture](#️-network-architecture)
- [📊 VLAN & IP Addressing Plan](#-vlan--ip-addressing-plan)
- [🛠️ Technologies & Tools](#️-technologies--tools)
- [🔐 Network Security](#-network-security)
- [🐍 Python Network Assurance](#-python-network-assurance)
- [🛠️ Fault Simulation & Troubleshooting](#️-fault-simulation--troubleshooting)
- [🏆 Certification & Credentials](#-certification--credentials)
- [📁 Repository Contents](#-repository-contents)
- [📄 Report Structure](#-report-structure)
- [👤 Individual Contribution & Team](#-individual-contribution--team)
- [💡 Learning Outcomes](#-learning-outcomes)
- [🙏 Acknowledgement](#-acknowledgement)
- [🔗 Reference Links](#-reference-links)

---

## 👤 Student Details

| Field | Details |
| :--- | :--- |
| **Name** | Vaibhav Raj Trivedi |
| **Roll Number** | **2410030723** |
| **Institute** | IILM University, Greater Noida, U.P. |
| **Programme** | B.Tech Computer Science and Engineering |
| **Semester** | 5th Semester |
| **Section** | **3CSE15** |
| **Batch** | 2024–2028 |
| **Academic Year** | 2026–27 |
| **Internship** | Cisco-AICTE Virtual Internship Program 2026 |
| **Domain** | Computer Networking & Network Reliability Engineering |
| **Project** | SmartBranch 360 |
| **Role** | Project Lead / Individual Project Developer |
| **Institutional Email** | `vaibhav.trivedi.cs28@iilm.edu` |

---

## 📌 About the Internship

The **Cisco-AICTE Virtual Internship Program 2026** is a collaborative industry-academia initiative organized under the statutory patronage of the **All India Council for Technical Education (AICTE)**, Ministry of Education, Government of India, in partnership with **Cisco Systems** and the **Cisco Networking Academy**. 

Facilitated at **IILM University, Greater Noida**, under the mentorship of Academy Instructor **Mr. Abhinav Raghav**, the program provided comprehensive theoretical foundations and rigorous hands-on laboratory experience in enterprise routing, switching, network security, packet analysis, and programmatic assurance.

### Verified Coursework & Timeline
- **Authoritative Program Period:** **15 May 2026 – 19 June 2026**
- **Coursework Completion Date:** **16 June 2026**
- **Mentoring Institution:** School of Computer Science and Engineering, IILM University
- **Instructor / Mentor:** Mr. Abhinav Raghav

### Cisco Networking Academy Completed Curriculum
1. **Getting Started with Cisco Packet Tracer**  
   *Focus:* Discrete-event network simulation, graphical modeling, and packet inspection.
2. **Exploring Networking with Cisco Packet Tracer**  
   *Focus:* Protocol analysis, Layer 2 switching, Layer 3 routing, and connectivity testing.
3. **Networking Essentials**  
   *Focus:* Enterprise network architectures, IP subnetting, Cisco IOS CLI, network services, and security.

---

## 🌐 About SmartBranch 360

**SmartBranch 360** is an enterprise-grade branch office network architecture designed, configured, and experimentally validated in **Cisco Packet Tracer 8.x**. Modern enterprise branch offices host diverse user populations—corporate workstations, untrusted visitor guests, local server infrastructure, and administrative workstations. 

Operating these assets on flat, unsegmented local area networks creates broadcast congestion, security vulnerabilities, and configuration drift. SmartBranch 360 solves these operational liabilities by delivering:
- **Collapsed-Core Hierarchy:** Core router (R1), distribution switch (SW1), and access switch (SW2) forming a scalable, resilient switching and routing fabric.
- **IEEE 802.1Q VLAN Segmentation:** Strict hardware-enforced broadcast domain isolation across four dedicated VLANs.
- **Router-on-a-Stick (RoAS) Inter-VLAN Routing:** Subinterfaces on Router R1 facilitating controlled inter-subnet traffic flow.
- **Centralized Network Services:** Native Cisco IOS DHCP server pools with scope exclusions, dual-zone authoritative DNS, and an internal HTTP intranet portal.
- **Simulated Internet Egress:** Port Address Translation (NAT/PAT Overload) translating internal subnets to public WAN transit addressing.
- **Multi-Layer Security:** Inbound extended Access Control Lists (ACLs) isolating visitor traffic and encrypted SSH version 2 management plane hardening.
- **Intentional Fault Simulation:** Systematic introduction, diagnosis, and remediation of five multi-layer operational faults across Layers 2 through 7.
- **Automated Network Assurance:** Independent development of `python_checker.py` to audit configurations against YAML specifications and dynamically generate remediation syntax.

---

## 🎯 Objectives

- **Enterprise Topology Design:** Construct a scalable collapsed-core branch topology connecting 8 corporate PCs, central server, wireless access point, two Catalyst switches, and a Cisco ISR router to a simulated ISP.
- **Layer 2 Segmentation:** Provision isolated IEEE 802.1Q broadcast domains for Employee (VLAN 10), Guest (VLAN 20), Server (VLAN 30), and Management (VLAN 99).
- **Trunking & Link Aggregation:** Establish 802.1Q gigabit trunk links between SW1, SW2, and R1 with strict allowed-VLAN lists.
- **Inter-VLAN Routing:** Implement Router-on-a-Stick routing via 802.1Q subinterfaces on Router R1 (`Gi0/0.10` through `Gi0/0.99`).
- **Dynamic Address Leasing:** Deploy Cisco IOS DHCP server pools with reserved exclusion boundaries (`.1`–`.20`) to eliminate IP address conflicts.
- **Intranet & Name Resolution:** Station internal HTTP web services and dual-zone authoritative DNS on Server SRV1 (`10.10.30.10`).
- **Edge Translation & Egress:** Configure dynamic NAT/PAT overload on R1 `Gi0/1` and default static routing to simulated external Internet (`8.8.8.8`).
- **Perimeter & Lateral Security:** Enforce inbound extended ACL `GUEST_ISOLATION` on `Gi0/0.20`, blocking guest access to internal subnets while permitting outbound WAN browsing.
- **Management Plane Hardening:** Enforce SSH version 2 with 1024-bit RSA keys on dedicated management VLAN 99, disabling unencrypted Telnet.
- **End-to-End Testing:** Execute a comprehensive multi-host test matrix verifying 100% intra-VLAN, inter-VLAN, DHCP, DNS, HTTP, NAT, and ACL compliance.
- **Systematic Fault Injection:** Intentionally inject, diagnose, and remediate five operational faults across Layers 2 through 7.
- **Programmatic Configuration Assurance:** Build a standalone Python assurance engine (`python_checker.py`) to validate configurations against `requirements.yaml`.

---

## ⏱️ Internship & Project Timeline

```text
15 May 2026                                16 June 2026                  19 June 2026
    |--------------------------------------------|-----------------------------|
    |  Cisco NetAcad Coursework & Lab Exercises  |  Project Documentation,     |
    |  Packet Tracer Simulation & Modeling       |  Presentation & Validation  |
    |  SmartBranch 360 Implementation            |  Final Academic Submission  |
```

The internship followed a structured timeline from **15 May 2026 to 19 June 2026**, with all Cisco Networking Academy coursework, credential examinations, and project validation successfully completed on **16 June 2026**.

---

## 🗓️ Phase-wise Project Development

The engineering lifecycle of SmartBranch 360 progressed chronologically across fifteen structured implementation phases:

| Phase | Work Completed | Description |
| :---: | :--- | :--- |
| **1** | **Requirements Analysis** | Analyzed branch user profiles, isolation boundaries, bandwidth demands, and WAN uplink requirements. |
| **2** | **Topology Modeling** | Designed the physical layout in Cisco Packet Tracer with core router, switches, AP, server, and workstations. |
| **3** | **VLAN Provisioning** | Created VLANs 10, 20, 30, and 99 on SW1 and SW2; established 802.1Q gigabit inter-switch trunk links. |
| **4** | **IPv4 Addressing Plan** | Engineered a deterministic RFC 1918 `10.10.x.0/24` subnet matrix and `200.0.0.0/30` WAN point-to-point transit link. |
| **5** | **Inter-VLAN Routing** | Configured 802.1Q subinterfaces on Router R1 (`Gi0/0.10`–`.99`) to terminate default gateways for each VLAN. |
| **6** | **DHCP Services** | Configured Cisco IOS DHCP pools (`EMPLOYEE`, `GUEST`, `SERVER`) with default routers, DNS pointers, and exclusions (`.1`–`.20`). |
| **7** | **Server & DNS Services** | Configured static IP `10.10.30.10` on SRV1, deployed branch HTTP portal, and configured authoritative A-records. |
| **8** | **NAT/PAT Overload** | Implemented dynamic Port Address Translation on R1 `Gi0/1` and default static routing to simulated ISP (`8.8.8.8`). |
| **9** | **Security ACLs** | Authored and bound inbound extended ACL `GUEST_ISOLATION` on `Gi0/0.20` to prevent lateral guest traversal. |
| **10** | **SSH Management** | Hardened management plane with SSH v2, 1024-bit RSA key pairs, and local authentication on dedicated VLAN 99. |
| **11** | **Network Testing** | Executed multi-host connectivity matrix verifying intra-VLAN, inter-VLAN, DHCP, DNS, HTTP, NAT, and ACL filtering. |
| **12** | **Fault Injection** | Injected five realistic multi-layer faults across Layer 2 switching, Layer 3 routing, DHCP, DNS, and NAT. |
| **13** | **Fault Troubleshooting** | Methodically diagnosed root causes using Cisco IOS show commands and verified recovery via targeted CLI fixes. |
| **14** | **Python Assurance Engine** | Developed `python_checker.py` in Python 3.12 to audit YAML models and CLI show runs, achieving 25/25 checks PASS. |
| **15** | **Documentation & Demo** | Authored comprehensive technical report, executive viva slide deck, demonstration runbook, and GitHub README. |

---

## 🏗️ Network Architecture

The architecture follows a collapsed-core topology where distribution and core functions are integrated on high-capacity devices:

```text
               +------------------------------------+
               |        Simulated ISP Router        |
               |        Loopback0: 8.8.8.8/32       |
               +-----------------+------------------+
                                 | Gi0/0 (200.0.0.1/30)
                                 | WAN Transit Link (200.0.0.0/30)
                                 | Gi0/1 (200.0.0.2/30)
               +-----------------+------------------+
               |       Core Router R1 (ISR 2911)    |
               |   - Subinterfaces Gi0/0.10–.99     |
               |   - Cisco IOS DHCP Server          |
               |   - NAT/PAT Overload on Gi0/1      |
               |   - Inbound ACL: GUEST_ISOLATION   |
               +-----------------+------------------+
                                 | Gi0/0 (802.1Q Trunk)
                                 | Gi0/1
               +-----------------+------------------+
               |   Distribution Switch SW1 (2960)   |
               |   - Trunk Links to R1 & SW2        |
               |   - VLANs 10, 20, 30, 99           |
               +--------+--------+--------+---------+
                        |        |        |
         +--------------+        |        +---------------+
         | Fa0/1–Fa0/4           | Fa0/10                 | Fa0/5
+--------+--------+    +---------+--------+     +---------+--------+
| Corporate Staff |    | Central Server   |     | Wireless AP1     |
| Workstations    |    | SRV1 (VLAN 30)   |     | (VLAN 20 Guest)  |
| PC0–PC3         |    | HTTP & Local DNS |     | Visitor Laptops  |
| (VLAN 10)       |    | 10.10.30.10      |     | & Mobile Devices |
+-----------------+    +------------------+     +------------------+
                                 | Gi0/2 (802.1Q Trunk)
                                 | Gi0/2
               +-----------------+------------------+
               |     Access Switch SW2 (2960)       |
               |   - Access Ports in VLAN 10        |
               |   - Management SVI (VLAN 99)       |
               +-----------------+------------------+
                                 | Fa0/1–Fa0/4
                       +---------+--------+
                       | Corporate Staff  |
                       | Workstations     |
                       | PC4–PC7 (VLAN 10)|
                       +------------------+
```

### Physical & Logical Device Inventory

| Device Name | Hardware Platform | Interfaces Used | Operational Role |
| :--- | :--- | :--- | :--- |
| **Router R1** | Cisco 2911 ISR | `Gi0/0` (LAN RoAS), `Gi0/1` (WAN) | Core default gateway, 802.1Q RoAS, DHCP server, NAT/PAT edge, security ACLs. |
| **Switch SW1** | Catalyst 2960-24TT | `Gi0/1`, `Gi0/2`, `Fa0/1–24` | Distribution hub; 802.1Q trunking; connects PC0–PC3, SRV1, and AP1. |
| **Switch SW2** | Catalyst 2960-24TT | `Gi0/2`, `Fa0/1–24` | Access-layer switch providing wired access to corporate workstations PC4–PC7. |
| **Server SRV1** | Server-PT | `FastEthernet0` | Static IP `10.10.30.10/24`; hosts HTTP intranet portal and dual-zone authoritative DNS. |
| **Access Point AP1** | AccessPoint-PT | `Port 0`, `Port 1` (SSID: `Guest`) | Bridges wireless visitor devices directly into isolated Guest VLAN 20. |
| **ISP Router** | Cisco 2911 ISR | `Gi0/0`, `Loopback0` (`8.8.8.8/32`) | Simulates upstream ISP provider over `200.0.0.0/30` point-to-point transit link. |

---

## 📊 VLAN & IP Addressing Plan

The addressing scheme utilizes RFC 1918 Class A private space (`10.10.0.0/16`), deterministically mapping the third octet to the VLAN ID:

| VLAN ID | Segment Name | Subnet (CIDR) | Subnet Mask | Default Gateway | Allocation Method |
| :---: | :--- | :--- | :--- | :--- | :--- |
| **VLAN 10** | Corporate Employees | `10.10.10.0/24` | `255.255.255.0` | `10.10.10.1` (`Gi0/0.10`) | DHCP: `10.10.10.21`–`.254` (`.1`–`.20` Reserved) |
| **VLAN 20** | Visitor Guests | `10.10.20.0/24` | `255.255.255.0` | `10.10.20.1` (`Gi0/0.20`) | DHCP: `10.10.20.21`–`.254` (`.1`–`.20` Reserved) |
| **VLAN 30** | Central Server Farm | `10.10.30.0/24` | `255.255.255.0` | `10.10.30.1` (`Gi0/0.30`) | Static: SRV1 assigned `10.10.30.10/24` |
| **VLAN 99** | Management Plane | `10.10.99.0/24` | `255.255.255.0` | `10.10.99.1` (`Gi0/0.99`) | Static: SW1 (`.2`), SW2 (`.3`), Admin PC (`.10`) |
| **WAN Link** | ISP Transit Uplink | `200.0.0.0/30` | `255.255.255.252` | `200.0.0.1` (ISP `Gi0/0`) | Static: R1 `Gi0/1` assigned `200.0.0.2/30` |
| **Loopback0**| Simulated Internet | `8.8.8.8/32` | `255.255.255.255` | N/A | Simulated Public Host on ISP Router |

---

## 🛠️ Technologies & Tools

- **Network Simulation:** Cisco Packet Tracer 8.x
- **Device Operating System:** Cisco IOS Software (15.x CLI)
- **Layer 2 Protocols:** IEEE 802.1Q VLAN Trunking, Access Port Hardening, SVI Management
- **Layer 3 Routing:** Router-on-a-Stick (RoAS) Subinterfaces, Static Default Routing (`0.0.0.0/0`)
- **Network Services:** Cisco IOS DHCP Server Pools, Authoritative DNS Service, HTTP Intranet Web Server
- **Edge Translation:** Port Address Translation (NAT/PAT Overload via `ip nat inside source`)
- **Security & Filtering:** Named Extended Access Control Lists (`GUEST_ISOLATION`), Standard ACL 1 for NAT
- **Management Cryptography:** SSH version 2, RSA 1024-bit asymmetric key generation, VTY transport restrictions
- **Assurance & Automation:** Python 3.12, PyYAML, Regular Expression CLI Parsing

---

## 🔐 Network Security

1. **Broadcast Boundary Isolation:** 802.1Q VLAN tagging ensures complete hardware-enforced Layer 2 isolation between employee data, visitor traffic, server resources, and administrative management.
2. **Inbound Extended ACL (`GUEST_ISOLATION`):**  
   Applied inbound on Router subinterface `Gi0/0.20` to block unauthorized guest traversal at the earliest Layer 3 ingress:
   ```cisco
   ip access-list extended GUEST_ISOLATION
    remark Deny guest traffic to Corporate Employee VLAN 10
    deny ip 10.10.20.0 0.0.0.255 10.10.10.0 0.0.0.255
    remark Deny guest traffic to Central Server VLAN 30
    deny ip 10.10.20.0 0.0.0.255 10.10.30.0 0.0.0.255
    remark Deny guest traffic to Management Plane VLAN 99
    deny ip 10.10.20.0 0.0.0.255 10.10.99.0 0.0.0.255
    remark Permit outbound Internet web traffic to WAN
    permit ip 10.10.20.0 0.0.0.255 any
   ```
3. **Dedicated Management Plane (VLAN 99):** Switch SVIs (`10.10.99.2`, `10.10.99.3`) and the router management IP are completely isolated from user data planes.
4. **SSH Version 2 Hardening:** Plaintext Telnet is strictly disabled across all VTY lines (`transport input ssh`), enforcing encrypted administrative access with local privilege 15 authentication and 1024-bit RSA key pairs.

---

## 🐍 Python Network Assurance

To bridge simulation modeling with modern **Network Reliability Engineering (NRE)** and NetDevOps practices, I independently engineered **`python_checker.py`**, an automated configuration assurance tool.

```text
+-----------------------+     +-----------------------+
|   requirements.yaml   |     |  Cisco IOS Show Runs  |
+-----------+-----------+     +-----------+-----------+
            |                             |
            +-------------->+<------------+
                            |
           +----------------v-----------------+
           |        python_checker.py         |
           | - VLAN Integrity Audit           |
           | - 802.1Q Trunk Allowed Audit     |
           | - Gateway Subinterface Audit     |
           | - DHCP Pool & Exclusion Audit    |
           | - DNS Daemon & Record Audit      |
           | - NAT/PAT Overload Audit         |
           | - ACL Filtering Rule Audit       |
           | - SSH v2 & RSA Key Audit         |
           +----------------+-----------------+
                            |
            +---------------+---------------+
            |                               |
    +-------v--------+             +--------v--------+
    | Compliance Log |             | CLI Remediation |
    | [PASS] 25/25   |             | Syntax Engine   |
    +----------------+             +-----------------+
```

### Audited Parameters & Verification Results
- **Dual Ingestion Engine:** Parses structured YAML architecture declarations and raw Cisco IOS show commands (`show run`, `show interfaces trunk`).
- **Severity Tagging:** Categorizes findings as `[PASS]` (compliant), `[WARNING]` (minor drift), or `[FAIL]` (service-impacting failure).
- **Automated Remediation:** Dynamically outputs the exact Cisco IOS configuration syntax required to restore failed parameters to full compliance.
- **Empirical Baseline Score:** **25 / 25 checks evaluated as `[PASS]` (100.0% Compliance)** on the production configuration.
- **Fault Detection Rate:** **5 / 5 simulated faults detected and diagnosed (100.0%)** with automated remediation generation.

---

## 🛠️ Fault Simulation & Troubleshooting

Five operational faults were intentionally introduced into the network, diagnosed using Cisco IOS show commands, and resolved:

| Fault | Layer / Area | Problem / Symptom | Root Cause Analysis | Remediation Syntax & Verification |
| :---: | :--- | :--- | :--- | :--- |
| **Fault 1** | **Layer 2 Switching** | VLAN 20 endpoints cannot acquire DHCP leases; 100% loss to default gateway `10.10.20.1`. | VLAN 20 inadvertently pruned from SW1 `Gi0/2` trunk allowed list (`switchport trunk allowed vlan remove 20`). | `SW1(config-if)# switchport trunk allowed vlan add 20`<br>Verified via `show interfaces trunk`. |
| **Fault 2** | **Layer 3 Host NIC** | Workstation pings local subnet (`10.10.10.2`), but fails to reach Server or Internet (`8.8.8.8`). | Host default gateway statically misconfigured to `10.10.10.254` instead of `10.10.10.1`. | Endpoint GUI: Set Default Gateway = `10.10.10.1` (or toggle DHCP). Verified via `ping 8.8.8.8`. |
| **Fault 3** | **Service (DHCP Scope)** | All VLAN 10 workstations lose off-subnet reachability upon lease renewal. | Administrative typo in router DHCP pool: `default-router 10.10.10.99` assigned to pool `EMPLOYEE`. | `R1(dhcp-config)# default-router 10.10.10.1`<br>Clients execute `ipconfig /renew`. |
| **Fault 4** | **Application (DNS)** | Workstation pings `8.8.8.8` successfully, but web browsing `server.local` or pinging `google.com` fails. | DNS daemon service disabled on branch server SRV1 (`10.10.30.10`). | SRV1 $\rightarrow$ Services $\rightarrow$ DNS $\rightarrow$ Toggle service to **On**.<br>Verified domain resolves to `8.8.8.8`. |
| **Fault 5** | **Network (NAT/PAT)** | Internal routing operational; external traffic to `8.8.8.8` times out completely. | Dynamic NAT overload source mapping statement removed from WAN router R1. | `R1(config)# ip nat inside source list 1 interface Gi0/1 overload`<br>Verified via `show ip nat statistics`. |

---

## 🏆 Certification & Credentials

All coursework and credential requirements were verified on the **Cisco Networking Academy** platform under the mentorship of **Mr. Abhinav Raghav, IILM University**:

1. **Getting Started with Cisco Packet Tracer**  
   *Issuing Organization:* Cisco Networking Academy  
   *Instructor:* Mr. Abhinav Raghav | *Completion Date:* 16 June 2026  
   *Verification Credential ID:* `31b1dd72-5542-4c2c-b203-4fdd8eed62cb`

2. **Exploring Networking with Cisco Packet Tracer**  
   *Issuing Organization:* Cisco Networking Academy  
   *Instructor:* Mr. Abhinav Raghav | *Completion Date:* 16 June 2026  
   *Verification Credential ID:* `94b24045-9aa3-42bd-8d9e-7ef003ffc23a`

3. **Networking Essentials**  
   *Issuing Organization:* Cisco Networking Academy  
   *Instructor:* Mr. Abhinav Raghav | *Completion Date:* 16 June 2026  
   *Verification Credential ID:* `a0227e1b-e2a3-4531-9b44-1dd41bb20ac0`

---

## 📁 Repository Contents

```text
college_intership_auditttt/
├── README.md                                                   # Complete GitHub internship repository documentation
├── SmartBranch360_Internship_Report_Vaibhav_Raj_Trivedi.pdf    # Final concise 16-page academic internship report (PDF)
├── SmartBranch360_Internship_Presentation_Vaibhav_Raj_Trivedi.pdf # Final 16-slide academic viva presentation (PDF)
├── Vaibhav_Raj_Trivedi_Internship_Report.docx                 # Full university format internship report (DOCX)
├── Vaibhav_Raj_Trivedi_Internship_Report.pdf                  # Full university format internship report (PDF)
├── Vaibhav Raj Trivedi _REPORT_CISCO (NETWORKING).docx        # Original technical project documentation
├── Internship Report Format updated 26-27.docx                 # IILM University official report guidelines
├── intershipss i was inrolled in with thier time perioddd.png  # Official NetAcad course timeline proof
└── certificates/                                               # Official Cisco NetAcad course certificates
    ├── Getting_Started_with_Cisco_Packet_Tracer_certificate_vaibhav-trivedi-cs28-iilm-edu_31b1dd72-5542-4c2c-b203-4fdd8eed62cb.pdf
    ├── Exploring_Networking_with_Cisco_Packet_Tracer_certificate_vaibhav-trivedi-cs28-iilm-edu_94b24045-9aa3-42bd-8d9e-7ef003ffc23a.pdf
    └── network essentials.pdf
```

---

## 📄 Report Structure

The final academic internship report is organized into the following major chapters and sections:

1. **Candidate's Declaration:** Formal declaration signed by the student author.
2. **Acknowledgement:** Formal institutional and academic acknowledgements.
3. **Internship Completion & Training Evidence:** Official Cisco NetAcad enrollment proof, course timeline screenshot, and coursework summary.
4. **Project Description:** Introduction, program overview, problem statement, objectives, and scope.
5. **Network Design & Architecture:** Collapsed-core topology, device roles, structured IPv4 addressing plan, core services, and security.
6. **Methodology & Phase-Wise Project Development:** Comprehensive lifecycle documentation across all 15 implementation phases.
7. **Python Network Assurance Checker:** Programmatic assurance engine architecture, audit rules, and 25/25 baseline validation.
8. **Fault Scenarios & Structured Troubleshooting:** Detailed analysis of Faults 1 to 5 with symptoms, root causes, and CLI fixes.
9. **Testing, Experimental Verification & Results:** End-to-end system testing matrix covering all functional areas.
10. **Individual Contribution & Team Collaboration:** Leadership responsibilities and collaborative acknowledgement.
11. **Learning Outcomes & Conclusion:** Progressive technical competencies and project conclusion.
12. **Bibliography / References:** Formal references in standard IEEE citation style.
13. **Annexures (Official Course Certificates):** High-resolution copies of all three Cisco Networking Academy certificates.

---

## 👤 Individual Contribution & Team

### Project Lead / Individual Developer
- **Vaibhav Raj Trivedi — Project Lead**  
  *Roll Number:* **2410030723** | *Section:* **3CSE15** (5th Semester)  
  *Department of Computer Science and Engineering, IILM University, Greater Noida, U.P.*  
  *Core Responsibilities:* End-to-end responsibility for collapsed-core architecture design, Cisco IOS configuration of Router R1 and Catalyst switches SW1/SW2, IEEE 802.1Q trunking, Router-on-a-Stick subinterfaces, Cisco IOS DHCP server pools, internal HTTP/DNS server deployment, NAT/PAT overload, extended ACL security policies (`GUEST_ISOLATION`), SSH version 2 hardening, five-layer fault simulation and troubleshooting, `python_checker.py` software development, and technical report/presentation compilation.

### Collaborative Peer Acknowledgement
- **Harsh Singh — Team Member**  
  *Department of Computer Science and Engineering, IILM University*  
  *Contribution:* Assisted in the execution of endpoint connectivity test matrices and verification of intra-VLAN employee workstation communication.
- **Parveen — Team Member**  
  *Department of Computer Science and Engineering, IILM University*  
  *Contribution:* Assisted in laboratory documentation review and verification of wireless access point guest onboarding test cases.

---

## 💡 Learning Outcomes

- **Layer 2 Switching & Trunking:** Mastered IEEE 802.1Q encapsulation, native VLAN security, access port hardening, and trunk allowed list optimization.
- **Layer 3 Routing & Subinterfaces:** Implemented centralized Router-on-a-Stick inter-VLAN routing and default static route forwarding.
- **Enterprise Network Services:** Deployed native Cisco IOS DHCP server pools with scope exclusions, dual-zone authoritative DNS, and dynamic NAT/PAT overload.
- **Network Security & Hardening:** Authored source-proximate named extended ACLs (`GUEST_ISOLATION`) and hardened management planes using SSH v2 (1024-bit RSA).
- **Disciplined Fault Troubleshooting:** Developed a repeatable, layer-by-layer diagnostic methodology spanning Layers 2 through 7 to minimize MTTR.
- **NetDevOps & Automated Assurance:** Gained practical experience in software-defined network assurance using Python and YAML models to validate live network state.
- **Project Leadership & Documentation:** Led technical implementation, verified multi-host test matrices, and compiled IEEE-standard engineering reports.

---

## 🙏 Acknowledgement

I express my deepest gratitude to **Mr. Abhinav Raghav**, Academy Instructor at the **Cisco Networking Academy, IILM University**, for his invaluable guidance, technical mentorship, and support throughout the Cisco-AICTE Virtual Internship Program 2026.

I also extend my sincere appreciation to the **School of Computer Science and Engineering, IILM University, Greater Noida**, for providing advanced laboratory facilities; to the **All India Council for Technical Education (AICTE)** and **Cisco Systems** for organizing this industry-aligned internship; and to my peers **Harsh Singh** and **Parveen** for their collaborative support during laboratory testing.

---

## 🔗 Reference Links

- [Cisco Networking Academy Official Portal](https://www.netacad.com/)
- [Cisco Packet Tracer Platform](https://www.netacad.com/courses/packet-tracer)
- [All India Council for Technical Education (AICTE) Internship Portal](https://internship.aicte-india.org/)
- [IILM University Official Website](https://www.iilm.edu/)
- [RFC 1918 — Address Allocation for Private Internets (IETF)](https://datatracker.ietf.org/doc/html/rfc1918)
- [RFC 2131 — Dynamic Host Configuration Protocol (IETF)](https://datatracker.ietf.org/doc/html/rfc2131)
- [RFC 3022 — Traditional IP Network Address Translator (Traditional NAT)](https://datatracker.ietf.org/doc/html/rfc3022)
- [IEEE Std 802.1Q — Bridges and Bridged Networks](https://standards.ieee.org/ieee/802.1Q/6844/)
