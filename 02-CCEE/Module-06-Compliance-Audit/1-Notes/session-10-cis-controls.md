# 🛡️ Session 10 — CIS Controls & Benchmarks

## 📑 Table of Contents
- [What is CIS](#what-is-cis)
- [CIS Overview](#cis-overview)
- [CIS Critical Security Controls](#cis-controls)
- [CIS Controls Versions](#controls-versions)
- [CIS Controls v8 — 18 Controls](#controls-v8)
- [CIS Implementation Groups (IGs)](#implementation-groups)
- [CIS Compliance](#cis-compliance)
- [CIS Benchmarks](#cis-benchmarks)
  - [Benchmark Categories](#benchmark-categories)
  - [Benchmark Levels](#benchmark-levels)
- [CIS SecureSuite](#cis-securesuite)
- [📌 Extra Notes](#extra-notes)
  - [History — SANS Top 20 to CIS Controls](#history)
  - [CIS Controls v7.1 vs v8 Comparison](#v7-vs-v8)
  - [CIS RAM — Risk Assessment Method](#cis-ram)
  - [CIS CSAT — Controls Self Assessment Tool](#cis-csat)
  - [CIS vs NIST CSF Mapping](#cis-vs-nist)
  - [CIS vs ISO 27001 Mapping](#cis-vs-iso)
  - [CIS Community Defense Model (CDM)](#cdm)
  - [CIS Hardened Images](#hardened-images)
  - [Top Attacks Mitigated by CIS Controls](#top-attacks)
- [Abbreviations](#abbreviations)
- [Keywords & Concept Map](#keywords)
- [Quick Reference Cheatsheet](#cheatsheet)
- [Session Revision Snapshot](#snapshot)

---

## 🔰 What is CIS <a name="what-is-cis"></a>

- **CIS = Center for Internet Security**
- A **nonprofit organization** focused on making the connected world
  a safer place
- Founded: **2000**
- Headquarters: **East Greenbush, New York, USA**
- Mission: Identify, develop, validate, promote, and sustain best
  practice solutions for cyber defense
- Develops and maintains:
  - **CIS Controls** — prioritized set of cybersecurity best practices
  - **CIS Benchmarks** — security configuration guidelines for
    specific technologies
  - **CIS SecureSuite** — tools and resources for implementing CIS
    guidance
- Works collaboratively with IT professionals, government, academia,
  and industry globally

> [!NOTE]
> CIS is a **nonprofit** — not a government agency, not a standards
> body like ISO, and not a regulatory body. Its guidance is **voluntary**
> but widely adopted by organizations globally including US government
> agencies, financial institutions, and healthcare organizations.

---

## 🏢 CIS Overview <a name="cis-overview"></a>

### Key Facts

| Attribute | Detail |
|---|---|
| **Full Name** | Center for Internet Security |
| **Type** | Nonprofit organization |
| **Founded** | 2000 |
| **Headquarters** | East Greenbush, New York, USA |
| **Key Products** | CIS Controls, CIS Benchmarks, CIS SecureSuite |
| **Controls Current Version** | CIS Controls v8 (May 2021) |
| **Benchmarks** | 100+ configuration guides for specific technologies |
| **Mandatory** | Voluntary — but widely adopted and referenced |
| **Relationship** | Complements NIST CSF, ISO 27001, NIST SP 800-53 |

### Why CIS Matters
- Provides **prioritized, actionable** cybersecurity guidance
- Based on **real-world threat data** — not just theoretical frameworks
- Free to use — no cost barrier for adoption
- Mapped to major compliance frameworks — helps satisfy multiple
  requirements simultaneously
- Developed through **community consensus** — global IT security
  professionals contribute
- Benchmarks provide **specific, technology-level** hardening guidance
  that broader frameworks lack

---

## 🛡️ CIS Critical Security Controls <a name="cis-controls"></a>

- **CIS Controls** = a prioritized set of cybersecurity best practices
  and defensive actions
- Originally called **SANS Top 20** — later renamed CIS Controls
- Address the **most common and impactful** cyber attacks
- Based on actual attack data — controls prioritized by what stops
  the most attacks
- **Free to use** — available for download from CIS website
- Current version: **CIS Controls v8 (May 2021)**

### Core Philosophy
- **Offense informs defense** — controls derived from analysis of
  actual attacker techniques
- **Prioritization** — not all controls are equal — focus on what
  matters most first
- **Community-developed** — contributions from thousands of security
  professionals globally
- **Actionable** — specific enough to implement — not just principles

> [!IMPORTANT]
> The CIS Controls are **prioritized by effectiveness** — they are
> not equal in importance. Controls that stop the most attacks are
> listed first. This prioritization is fundamental to the CIS
> philosophy and the basis for the Implementation Groups.

---

## 📜 CIS Controls Versions <a name="controls-versions"></a>

```
2008 → SANS Top 20 published
        Originally called "The Twenty Critical Security Controls
        for Effective Cyber Defense"
        Developed by SANS Institute

2009 → Renamed to "Consensus Audit Guidelines (CAG)"

2013 → Ownership transferred to Council on Cybersecurity

2015 → Council on Cybersecurity becomes Center for Internet Security
        Controls renamed to "CIS Critical Security Controls"
        Version 6.0 published

2016 → CIS Controls Version 6.1 published

2018 → CIS Controls Version 7.0 published
        Major update — 20 controls maintained

2019 → CIS Controls Version 7.1 published
        Minor refinements

2021 → CIS Controls Version 8 published (May 2021)
        Major revision — reduced from 20 to 18 controls
        Introduced Implementation Groups (IGs)
        Activity-based rather than device-based approach
```

> [!TIP]
> **Key version facts for MCQs:**
> - Originally **SANS Top 20** — transferred to CIS
> - **v7.1** = 20 controls
> - **v8** = 18 controls (current — May 2021)
> - The reduction from 20 to 18 is a very common MCQ trap

---

## 📋 CIS Controls v8 — 18 Controls <a name="controls-v8"></a>

CIS Controls v8 organizes **18 controls** into three categories
based on Implementation Groups:

### All 18 CIS Controls

| Control | Name | Description |
|---|---|---|
| **CIS 1** | Inventory and Control of Enterprise Assets | Actively manage all hardware assets — know what you own |
| **CIS 2** | Inventory and Control of Software Assets | Actively manage all software — only authorized software runs |
| **CIS 3** | Data Protection | Develop processes to identify, classify, handle, retain, and dispose of data |
| **CIS 4** | Secure Configuration of Enterprise Assets and Software | Establish and maintain secure configurations for hardware and software |
| **CIS 5** | Account Management | Use processes and tools to assign and manage authorization to credentials |
| **CIS 6** | Access Control Management | Use processes and tools to create, assign, manage, and revoke access |
| **CIS 7** | Continuous Vulnerability Management | Continuously acquire, assess, and take action on vulnerability info |
| **CIS 8** | Audit Log Management | Collect, alert, review, and retain audit logs |
| **CIS 9** | Email and Web Browser Protections | Improve protections and detection for email and web threats |
| **CIS 10** | Malware Defenses | Control installation, spread, and execution of malicious code |
| **CIS 11** | Data Recovery | Establish and maintain data recovery practices |
| **CIS 12** | Network Infrastructure Management | Establish and maintain network infrastructure security |
| **CIS 13** | Network Monitoring and Defense | Operate processes and tools to monitor and defend the network |
| **CIS 14** | Security Awareness and Skills Training | Establish and maintain security awareness program |
| **CIS 15** | Service Provider Management | Develop a process to evaluate service providers with access to assets |
| **CIS 16** | Application Software Security | Manage the security lifecycle of in-house software |
| **CIS 17** | Incident Response Management | Establish a program for incident response |
| **CIS 18** | Penetration Testing | Test effectiveness of defenses through penetration testing |

> [!TIP]
> **Memory trick for first 6 controls (most foundational):**
> **"I Invented Data Security Accounts Access"**
> CIS 1 = Inventory assets → CIS 2 = Inventory software →
> CIS 3 = Data protection → CIS 4 = Secure config →
> CIS 5 = Account management → CIS 6 = Access control

---

## 🏗️ CIS Implementation Groups (IGs) <a name="implementation-groups"></a>

**Implementation Groups (IGs)** = a self-assessment guide for
prioritizing CIS Controls implementation based on organization
size, resources, and risk profile

- Introduced formally in **CIS Controls v7** — refined in v8
- Three groups: **IG1, IG2, IG3**
- NOT a maturity model — a **risk-based prioritization tool**

| Group | Target Organization | Description | Safeguards |
|---|---|---|---|
| **IG1** | Small organizations — limited IT/security resources | Basic cyber hygiene — essential controls for all organizations | 56 safeguards |
| **IG2** | Medium organizations — dedicated IT staff, some compliance requirements | Addresses more sophisticated threats — builds on IG1 | 74 additional safeguards (130 total) |
| **IG3** | Large organizations — security experts, complex compliance, sensitive data | Addresses advanced attacks — full CIS Controls implementation | 23 additional safeguards (153 total) |

> [!IMPORTANT]
> **IG1 is considered "essential cyber hygiene"** — the minimum
> every organization should implement regardless of size. IG1
> contains 56 safeguards covering the most fundamental security
> practices. Organizations should complete IG1 before moving to IG2.

### IG1 Characteristics
- Protects against the **most common and low-sophistication attacks**
- Focuses on fundamental security practices
- Does NOT require specialized security expertise to implement
- Appropriate for organizations with limited IT budgets
- Considered the **minimum security standard** for all organizations

### IG Hierarchy

```
IG3 (153 total safeguards — all 18 controls fully implemented)
│
├── IG2 (130 safeguards — builds on IG1)
│
└── IG1 (56 safeguards — essential cyber hygiene — ALL orgs)
```

> [!NOTE]
> IGs are **cumulative** — IG2 includes all IG1 safeguards plus
> additional ones. IG3 includes all IG1 and IG2 safeguards.
> An IG3 organization implements ALL safeguards across all
> 18 controls.

---

## ✅ CIS Compliance <a name="cis-compliance"></a>

- CIS Controls are **not a compliance mandate** — there is no
  regulatory body requiring CIS Controls adoption
- However CIS Controls are:
  - **Referenced in regulatory frameworks** — NIST, HIPAA, PCI DSS
  - **Required by some government contracts** — US federal agencies
    increasingly reference CIS
  - **Used as evidence** of due care in legal proceedings
  - **Insurance requirements** — some cyber insurers require CIS
    Controls implementation

### How Organizations Use CIS for Compliance

| Use Case | How CIS Helps |
|---|---|
| **Framework Mapping** | CIS Controls mapped to NIST CSF, ISO 27001, HIPAA, PCI DSS |
| **Gap Analysis** | CIS CSAT tool identifies gaps in current implementation |
| **Due Diligence** | Demonstrating cyber hygiene to customers and partners |
| **Insurance** | Meeting cyber insurance requirements |
| **Audit Evidence** | CIS Benchmark compliance as evidence in audits |
| **Government** | US government agencies often reference CIS |

### CIS Controls and US Government
- **FISMA** (Federal Information Security Management Act) — CIS
  Controls align with NIST SP 800-53 requirements
- **EO 13800** (Trump Executive Order on Cybersecurity) — referenced
  NIST CSF which maps to CIS Controls
- **CISA** (Cybersecurity and Infrastructure Security Agency) —
  frequently recommends CIS Controls for critical infrastructure

---

## 📊 CIS Benchmarks <a name="cis-benchmarks"></a>

- **CIS Benchmarks** = detailed, technology-specific security
  configuration guidelines
- Over **100+ benchmarks** covering specific operating systems,
  applications, cloud environments, and devices
- Developed through **community consensus** — security experts
  globally contribute
- **Free to download** from CIS website
- Provide specific, actionable configuration recommendations
- Represent the **internationally recognized standard** for
  secure configuration

### 📁 Benchmark Categories <a name="benchmark-categories"></a>

| Category | Examples |
|---|---|
| **Operating Systems** | Windows 10/11, Windows Server, Ubuntu, RHEL, macOS, Debian |
| **Cloud Providers** | AWS, Microsoft Azure, Google Cloud Platform (GCP), Oracle Cloud |
| **Mobile Devices** | Apple iOS/iPadOS, Android |
| **Desktop Software** | Microsoft Office, Chrome, Firefox |
| **Server Software** | Apache, Nginx, IIS, Tomcat |
| **Databases** | MySQL, PostgreSQL, Oracle, SQL Server, MongoDB |
| **Network Devices** | Cisco, Juniper, Check Point, Palo Alto |
| **Virtualization** | VMware, Docker, Kubernetes |
| **Multi-Function Print Devices** | HP, Xerox, Ricoh |

> [!NOTE]
> CIS Benchmarks are the **most specific** of all CIS products —
> while CIS Controls say "implement secure configurations" (CIS
> Control 4), CIS Benchmarks tell you exactly WHICH settings to
> configure on a specific version of Windows or AWS. They are
> the implementation guidance for CIS Control 4.

---

### 🔒 Benchmark Levels <a name="benchmark-levels"></a>

Each CIS Benchmark recommendation is assigned one of two levels:

| Level | Name | Description | Applicability |
|---|---|---|---|
| **Level 1** | Basic Security | Minimum security baseline — practical and prudent | All organizations — essential |
| **Level 2** | Advanced Security | Defense-in-depth — may impact functionality | High security environments — sensitive data |

> [!IMPORTANT]
> **Level 1 = essential baseline for ALL organizations**
> **Level 2 = additional hardening for sensitive environments**
> Level 2 recommendations may impact system functionality or
> usability — they represent a more restrictive configuration.
> Organizations should implement Level 1 first, then assess
> whether Level 2 is appropriate.

### Benchmark Recommendation Types

| Type | Symbol | Meaning |
|---|---|---|
| **Scored** | ✔ | Failure to implement affects the benchmark score |
| **Not Scored** | ✗ | Recommended but not included in benchmark score |

---

## 🔧 CIS SecureSuite <a name="cis-securesuite"></a>

- **CIS SecureSuite** = a membership program providing tools and
  resources for CIS Controls and Benchmarks implementation
- Includes:
  - **CIS-CAT Pro** — automated benchmark scanning tool
  - **CIS CSAT** — Controls Self-Assessment Tool
  - **CIS WorkBench** — platform for customizing and deploying
    benchmarks
  - **Priority Guidance** — customized guidance based on IGs
- Membership tiers: Associate (free) and Member (paid)

### CIS-CAT Pro
- Automated tool that scans systems against CIS Benchmarks
- Produces compliance reports showing pass/fail for each
  benchmark recommendation
- Used by IT teams to verify configuration compliance
- Integrates with SIEM and vulnerability management tools

---

## 📌 Extra Notes <a name="extra-notes"></a>

> [!NOTE]
> Everything in this section goes beyond the core syllabus but is
> directly MCQ-relevant. Cross-referenced from CIS official
> documentation and cybersecurity best practice literature.
> Zero internet needed after reading this.

---

### 📜 History — SANS Top 20 to CIS Controls <a name="history"></a>

Full evolution of CIS Controls:

```
2008 → SANS Institute publishes "Twenty Critical Security Controls"
        Also known as SANS Top 20
        Developed in response to major data breaches at US
        government agencies — especially Department of Defense

2009 → Renamed "Consensus Audit Guidelines (CAG)"
        Endorsed by NSA and US government agencies

2011 → Stewardship transferred to Council on Cybersecurity (CCS)
        Removed from direct SANS control

2013 → Council on Cybersecurity takes full ownership
        Controls renamed "Critical Security Controls (CSC)"

2015 → Council on Cybersecurity becomes Center for Internet Security
        Controls become "CIS Critical Security Controls"
        Version 6.0 published under CIS

2021 → CIS Controls v8 published
        SANS involvement formally historical — CIS is now the owner
```

> [!TIP]
> The key history fact: **CIS Controls were originally called SANS
> Top 20** — developed by the SANS Institute. The transfer to CIS
> happened gradually between 2011–2015. MCQs may reference either
> name.

---

### 📊 CIS Controls v7.1 vs v8 Comparison <a name="v7-vs-v8"></a>

| Feature | CIS Controls v7.1 | CIS Controls v8 |
|---|---|---|
| **Year** | 2019 | 2021 |
| **Number of Controls** | 20 | 18 |
| **Number of Sub-Controls/Safeguards** | 171 | 153 |
| **Approach** | Device-centric | Activity/outcome-based |
| **Implementation Groups** | IGs introduced | IGs refined |
| **Cloud/Mobile** | Limited coverage | Enhanced coverage |
| **Merged Controls** | — | Controls 4+5 merged; 14+16 merged |
| **Removed** | — | Application Whitelisting merged into others |

### What Changed from v7.1 to v8
- **Control 20 (Penetration Testing)** moved from last to
  **Control 18** — same concept, renumbered
- **Application Whitelisting** (v7 Control 2) merged into
  CIS Control 2 (Software Asset Inventory)
- **Wireless Access Control** (v7 Control 15) merged into
  network controls
- Enhanced coverage of cloud services, remote work, and mobile
  environments

> [!NOTE]
> The most tested fact: **v7.1 had 20 controls, v8 has 18 controls.**
> The reduction came from merging related controls — not removing
> security requirements. All previous concepts still exist — just
> reorganized.

---

### 📊 CIS RAM — Risk Assessment Method <a name="cis-ram"></a>

- **CIS RAM = CIS Risk Assessment Method**
- A free risk assessment method developed by CIS
- Helps organizations implement the **Risk Assessments** required
  by CIS Control 18 (previously various controls)
- Based on information security risk assessment principles
- Provides a structured approach to:
  - Identifying information security risks
  - Evaluating likelihood and impact
  - Prioritizing risk treatment based on CIS Controls
  - Demonstrating due care to auditors and regulators

### CIS RAM Editions
- **CIS RAM for IG1** — for small organizations implementing
  essential cyber hygiene
- **CIS RAM for Enterprise** — for larger organizations with
  more complex risk profiles

> [!NOTE]
> CIS RAM works directly with the Implementation Groups —
> IG1 organizations use CIS RAM IG1 edition. This alignment
> makes CIS RAM a natural companion to CIS Controls
> implementation.

---

### 🔧 CIS CSAT — Controls Self Assessment Tool <a name="cis-csat"></a>

- **CIS CSAT = CIS Controls Self-Assessment Tool**
- Free web-based tool from CIS
- Allows organizations to assess their current implementation
  of CIS Controls
- Provides a **maturity score** for each CIS Control
- Generates reports showing gaps and prioritized recommendations
- Maps to Implementation Groups — shows IG1, IG2, IG3 progress
- Used to track improvement over time

### CSAT Maturity Levels

| Level | Name | Description |
|---|---|---|
| **1** | Initial | Safeguard not implemented |
| **2** | Developing | Partially implemented |
| **3** | Defined | Fully implemented — documented process |
| **4** | Managed | Metrics collected and reviewed |
| **5** | Optimizing | Continuously improved |

---

### 🔗 CIS vs NIST CSF Mapping <a name="cis-vs-nist"></a>

CIS Controls map directly to NIST CSF functions:

| NIST CSF Function | Relevant CIS Controls |
|---|---|
| **Identify** | CIS 1 (Asset Inventory), CIS 2 (Software Inventory), CIS 3 (Data Protection), CIS 15 (Service Providers) |
| **Protect** | CIS 4 (Secure Config), CIS 5 (Accounts), CIS 6 (Access), CIS 9 (Email/Web), CIS 10 (Malware), CIS 14 (Awareness) |
| **Detect** | CIS 7 (Vulnerability Mgmt), CIS 8 (Audit Logs), CIS 13 (Network Monitoring) |
| **Respond** | CIS 17 (Incident Response) |
| **Recover** | CIS 11 (Data Recovery) |

> [!TIP]
> NIST CSF provides the **governance framework** (what to do).
> CIS Controls provide **specific technical actions** (how to do it).
> Together they complement each other — NIST CSF for strategy,
> CIS Controls for implementation. Many organizations use both.

---

### 🔗 CIS vs ISO 27001 Mapping <a name="cis-vs-iso"></a>

| ISO 27001 Domain (2013) | Relevant CIS Controls |
|---|---|
| A.8 Asset Management | CIS 1, CIS 2 |
| A.9 Access Control | CIS 5, CIS 6 |
| A.10 Cryptography | CIS 3 |
| A.11 Physical Security | CIS 4 |
| A.12 Operations Security | CIS 7, CIS 8, CIS 10 |
| A.13 Communications Security | CIS 12, CIS 13 |
| A.14 System Development | CIS 16 |
| A.16 Incident Management | CIS 17 |
| A.18 Compliance | CIS 18 |

> [!NOTE]
> Organizations certified to ISO 27001 can use CIS Controls to
> provide the **specific technical implementation** of ISO 27001
> Annex A controls. CIS Controls fill in the "how" where ISO
> 27001 only says "what." Using CIS Benchmarks alongside ISO
> 27001 provides both strategic and technical coverage.

---

### 🛡️ CIS Community Defense Model (CDM) <a name="cdm"></a>

- **CDM = CIS Community Defense Model**
- A data-driven model that shows which CIS Controls and
  Safeguards are most effective against specific attack types
- Based on analysis of real-world attack patterns from threat
  intelligence data
- Answers: *"Which CIS Controls should we prioritize to defend
  against the most common attacks?"*

### Top Attack Types Addressed by CDM

| Attack Type | Most Effective Controls |
|---|---|
| **Malware** | CIS 10, CIS 2, CIS 4 |
| **Ransomware** | CIS 11, CIS 10, CIS 8 |
| **Web Application Attacks** | CIS 16, CIS 4, CIS 7 |
| **Insider Threats** | CIS 6, CIS 5, CIS 8 |
| **Targeted Intrusions (APT)** | CIS 18, CIS 13, CIS 7 |

---

### 🖼️ CIS Hardened Images <a name="hardened-images"></a>

- **CIS Hardened Images** = pre-configured virtual machine images
  already configured to CIS Benchmark standards
- Available on major cloud marketplaces (AWS, Azure, GCP)
- Organizations can deploy these images instead of manually
  hardening systems
- Reduces time and effort for CIS Benchmark compliance
- Available for common operating systems (Linux, Windows Server)
- CIS Level 1 and Level 2 images available

> [!TIP]
> CIS Hardened Images are particularly relevant for **cloud
> deployments** — organizations building in AWS, Azure, or GCP
> can use pre-hardened images as the base for their systems
> instead of manually applying hundreds of benchmark settings.

---

### 🎯 Top Attacks Mitigated by CIS Controls <a name="top-attacks"></a>

Research shows CIS Controls implementation mitigates a high
percentage of common attack techniques:

| Attack Technique | Primary Mitigating Controls |
|---|---|
| **Phishing** | CIS 9 (Email protections), CIS 14 (Awareness training) |
| **Drive-by Downloads** | CIS 9 (Web browser protection), CIS 10 (Malware defenses) |
| **Unpatched Software** | CIS 7 (Vulnerability management), CIS 2 (Software inventory) |
| **Default Credentials** | CIS 4 (Secure configuration), CIS 5 (Account management) |
| **Stolen Credentials** | CIS 5 (Account management), CIS 6 (Access control) |
| **Ransomware** | CIS 11 (Data recovery), CIS 10 (Malware), CIS 8 (Audit logs) |
| **SQL Injection** | CIS 16 (Application security), CIS 4 (Secure config) |
| **Lateral Movement** | CIS 6 (Access control), CIS 12 (Network management) |

> [!NOTE]
> The **first 6 CIS Controls (IG1)** alone — basic cyber hygiene —
> have been shown to mitigate the majority of common cyberattacks.
> This is why CIS emphasizes implementing IG1 completely before
> moving to more advanced controls.

---

## 🔤 Abbreviations <a name="abbreviations"></a>

| Abbreviation | Full Form | One-line Meaning |
|---|---|---|
| **CIS** | Center for Internet Security | Nonprofit that develops CIS Controls and CIS Benchmarks |
| **CIS CSC** | CIS Critical Security Controls | Prioritized set of 18 cybersecurity best practices |
| **IG** | Implementation Group | Risk-based prioritization tier for CIS Controls (IG1/IG2/IG3) |
| **CDM** | Community Defense Model | CIS model showing which controls defend against which attacks |
| **CIS RAM** | CIS Risk Assessment Method | Free risk assessment methodology aligned to CIS Controls |
| **CIS CSAT** | CIS Controls Self-Assessment Tool | Web tool for assessing CIS Controls implementation maturity |
| **CAG** | Consensus Audit Guidelines | Early name for CIS Controls (2009) |
| **SANS** | SysAdmin, Audit, Network, Security | Institute that originally developed the Top 20 controls |
| **FISMA** | Federal Information Security Management Act | US law requiring federal agencies to secure information systems |
| **CISA** | Cybersecurity and Infrastructure Security Agency | US federal agency promoting CIS Controls for critical infrastructure |
| **BIN** | Bank Identification Number | First 6 digits of a PAN identifying the card issuer |
| **CCS** | Council on Cybersecurity | Interim steward of controls before CIS took ownership |
| **ASV** | Approved Scanning Vendor | PCI term — not CIS specific |
| **CIS-CAT** | CIS Configuration Assessment Tool | Automated tool that scans systems against CIS Benchmarks |

---

## 🗝️ Keywords & Concept Map <a name="keywords"></a>

**CIS (Center for Internet Security)**
→ Nonprofit — founded 2000 — East Greenbush, New York
→ Develops CIS Controls (v8 — 18 controls) and CIS Benchmarks (100+)
→ Voluntary — no regulatory mandate
→ Free to use — community-developed
→ Complements NIST CSF, ISO 27001, PCI DSS, HIPAA

**CIS Controls**
→ 18 prioritized security best practices (v8 — 2021)
→ Originally SANS Top 20 — transferred to CIS (2015)
→ Offense-informed — based on real attack data
→ Organized into 3 Implementation Groups (IG1/IG2/IG3)
→ IG1 = essential cyber hygiene — 56 safeguards — all orgs

**Implementation Groups (IGs)**
→ IG1 = small orgs — 56 safeguards — essential baseline
→ IG2 = medium orgs — 130 safeguards — builds on IG1
→ IG3 = large orgs — 153 safeguards — full implementation
→ Cumulative — IG3 includes all IG1 + IG2 safeguards
→ NOT a maturity model — a prioritization tool

**CIS Benchmarks**
→ Technology-specific hardening guides
→ 100+ benchmarks for OS, cloud, apps, databases, network devices
→ Two levels: Level 1 (essential baseline) / Level 2 (advanced)
→ Free to download — community developed
→ Complement CIS Control 4 (Secure Configuration)

**CIS Controls History**
→ 2008 — SANS Top 20
→ 2009 — CAG (Consensus Audit Guidelines)
→ 2015 — CIS Critical Security Controls (v6)
→ 2019 — v7.1 (20 controls)
→ 2021 — v8 (18 controls — current)

---

## ⚡ Quick Reference Cheatsheet <a name="cheatsheet"></a>

### CIS Controls v8 — All 18 Controls

| # | Control | IG |
|---|---|---|
| 1 | Inventory and Control of Enterprise Assets | IG1 |
| 2 | Inventory and Control of Software Assets | IG1 |
| 3 | Data Protection | IG1 |
| 4 | Secure Configuration of Enterprise Assets and Software | IG1 |
| 5 | Account Management | IG1 |
| 6 | Access Control Management | IG1 |
| 7 | Continuous Vulnerability Management | IG1 |
| 8 | Audit Log Management | IG1 |
| 9 | Email and Web Browser Protections | IG1 |
| 10 | Malware Defenses | IG1 |
| 11 | Data Recovery | IG1 |
| 12 | Network Infrastructure Management | IG2 |
| 13 | Network Monitoring and Defense | IG2 |
| 14 | Security Awareness and Skills Training | IG1 |
| 15 | Service Provider Management | IG2 |
| 16 | Application Software Security | IG2 |
| 17 | Incident Response Management | IG2 |
| 18 | Penetration Testing | IG3 |

### Implementation Groups Summary

| IG | Target | Safeguards | Focus |
|---|---|---|---|
| **IG1** | Small orgs — limited resources | 56 | Essential cyber hygiene |
| **IG2** | Medium orgs — dedicated IT | 130 total | Sophisticated threats |
| **IG3** | Large orgs — security experts | 153 total | Advanced persistent threats |

### CIS Controls Version History

| Version | Year | Controls | Notes |
|---|---|---|---|
| SANS Top 20 | 2008 | 20 | Original name |
| v6.0 | 2015 | 20 | First CIS-branded version |
| v7.1 | 2019 | 20 | Last 20-control version |
| **v8** | **2021** | **18** | **Current — activity-based** |

### CIS Benchmark Levels

| Level | Name | Applies To | Impact |
|---|---|---|---|
| **Level 1** | Essential baseline | All organizations | Minimal functionality impact |
| **Level 2** | Advanced security | High-security environments | May impact functionality |

### CIS vs NIST CSF Mapping (Summary)

| NIST Function | Primary CIS Controls |
|---|---|
| Identify | CIS 1, 2, 3, 15 |
| Protect | CIS 4, 5, 6, 9, 10, 14 |
| Detect | CIS 7, 8, 13 |
| Respond | CIS 17 |
| Recover | CIS 11 |

### CIS Controls Name Evolution

```
2008 → SANS Top 20
2009 → Consensus Audit Guidelines (CAG)
2013 → Critical Security Controls (CSC)
2015 → CIS Critical Security Controls
2021 → CIS Controls v8 (current)
```

### v7.1 vs v8 Key Differences

| Feature | v7.1 | v8 |
|---|---|---|
| Controls | 20 | 18 |
| Safeguards | 171 | 153 |
| Approach | Device-centric | Activity-based |
| Year | 2019 | 2021 |

### Top Attacks and Mitigating CIS Controls

| Attack | Key Controls |
|---|---|
| Phishing | CIS 9, CIS 14 |
| Ransomware | CIS 11, CIS 10, CIS 8 |
| Default credentials | CIS 4, CIS 5 |
| Unpatched software | CIS 7, CIS 2 |
| Insider threats | CIS 6, CIS 5, CIS 8 |

---

## 🔁 Session Revision Snapshot <a name="snapshot"></a>

### TL;DR — 5 Bullets
- ✅ CIS = nonprofit organization — founded 2000 — develops CIS
  Controls (v8 — 18 controls) and CIS Benchmarks (100+) — free
  and voluntary — community-developed
- ✅ CIS Controls v8 (2021) = 18 controls — down from 20 in v7.1 —
  organized into 3 Implementation Groups — IG1 (56 safeguards)
  = essential cyber hygiene for ALL organizations
- ✅ Implementation Groups: IG1 (small — 56), IG2 (medium — 130),
  IG3 (large — 153) — cumulative — IG3 includes all IGs —
  NOT a maturity model but a prioritization tool
- ✅ CIS Benchmarks = technology-specific hardening guides (100+) —
  two levels: Level 1 (essential baseline) / Level 2 (advanced) —
  specific enough to tell you EXACTLY what to configure
- ✅ CIS Controls were originally **SANS Top 20** — transferred to
  CIS in 2015 — offense-informed defense — prioritized by what
  stops the most real-world attacks

### 🎯 Top MCQ-Likely Concepts from This Session
1. **CIS = Center for Internet Security** — nonprofit — founded 2000
2. **v8 = 18 controls** (NOT 20 — that was v7.1) — May 2021
3. **Originally SANS Top 20** — transferred to CIS 2015
4. **IG1 = essential cyber hygiene** — 56 safeguards — ALL orgs
5. **IG1/IG2/IG3** — small/medium/large — cumulative safeguards
6. **CIS Benchmarks Level 1 vs Level 2** — essential vs advanced
7. **IGs are NOT a maturity model** — prioritization tool
8. **CIS Controls = free** — no cost to use
9. **CIS Control 4** = Secure Configuration — what Benchmarks implement
10. **NIST CSF + CIS Controls** — complementary — CSF for strategy,
    CIS for implementation
11. **153 total safeguards in IG3** — full implementation

---