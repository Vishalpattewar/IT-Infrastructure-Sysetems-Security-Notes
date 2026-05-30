# 🔐 Session 05 — ISO/IEC 27001 & ISO 2700x Family

## 📑 Table of Contents
- [What is ISO](#what-is-iso)
- [ISO 2700x Family Overview](#iso-2700x-family)
- [ISO/IEC 27001 Overview](#iso-27001-overview)
- [History of ISO/IEC 27001](#history)
- [How the Standard Works](#how-it-works)
- [Structure of ISO/IEC 27001](#structure)
  - [Clauses 0–5 — Introductory](#clauses-0-5)
  - [Clause 4 — Context of the Organization](#clause-4)
  - [Clause 5 — Leadership](#clause-5)
  - [Clause 6 — Planning](#clause-6)
  - [Clause 7 — Support](#clause-7)
  - [Clause 8 — Operation](#clause-8)
  - [Clause 9 — Performance Evaluation](#clause-9)
  - [Clause 10 — Improvement](#clause-10)
- [Annex A — Controls](#annex-a)
- [ISO/IEC 27001:2005 Domains — 11 Domains](#domains-2005)
- [ISO/IEC 27001:2013 Control Domains](#domains-2013)
- [ISO/IEC 27001:2022 — Latest Version](#version-2022)
- [ISMS — Information Security Management System](#isms)
- [ISO 27001 Certification Process](#certification)
- [📌 Extra Notes](#extra-notes)
  - [ISO 2700x Family — Other Key Standards](#2700x-others)
  - [Plan-Do-Check-Act (PDCA) Cycle](#pdca)
  - [Statement of Applicability (SoA)](#soa)
  - [Risk Treatment Options](#risk-treatment)
  - [ISO 27001 vs NIST CSF Comparison](#iso-vs-nist)
  - [ISO 27001 vs ISO 27002](#27001-vs-27002)
- [Abbreviations](#abbreviations)
- [Keywords & Concept Map](#keywords)
- [Quick Reference Cheatsheet](#cheatsheet)
- [Session Revision Snapshot](#snapshot)

---

## 🏛️ What is ISO <a name="what-is-iso"></a>

- **ISO = International Organization for Standardization**
- An **independent, non-governmental international organization**
- Founded: **23 February 1947**
- Headquarters: **Geneva, Switzerland**
- Membership: **167 national standards bodies** (one per country)
- India's member body: **BIS (Bureau of Indian Standards)**
- Develops and publishes **international standards** across virtually every
  industry and technology
- ISO works jointly with **IEC (International Electrotechnical Commission)**
  on IT standards — hence **ISO/IEC** joint standards

> [!NOTE]
> The name ISO comes from the Greek word **"isos"** meaning equal —
> chosen so the acronym would be the same in all languages regardless
> of translation. It is NOT an acronym for the English name.

---

## 📚 ISO 2700x Family Overview <a name="iso-2700x-family"></a>

The **ISO/IEC 2700x family** is a series of standards specifically focused
on **information security management**:

| Standard | Topic |
|---|---|
| **ISO/IEC 27000** | Overview and vocabulary — definitions for the entire family |
| **ISO/IEC 27001** | Information Security Management System (ISMS) — **requirements** |
| **ISO/IEC 27002** | Code of practice — **guidance** for implementing 27001 controls |
| **ISO/IEC 27003** | ISMS implementation guidance |
| **ISO/IEC 27004** | Information security measurement and metrics |
| **ISO/IEC 27005** | Information security risk management |
| **ISO/IEC 27006** | Requirements for audit and certification bodies |
| **ISO/IEC 27007** | Guidelines for auditing ISMS |
| **ISO/IEC 27017** | Cloud security controls |
| **ISO/IEC 27018** | Protection of PII in public clouds |
| **ISO/IEC 27031** | ICT readiness for business continuity |
| **ISO/IEC 27035** | Incident management |
| **ISO/IEC 27701** | Privacy information management — extends 27001 for GDPR |

> [!IMPORTANT]
> **ISO/IEC 27001** is the **only certifiable standard** in the 2700x
> family. All others are guidance documents. You get certified to
> 27001 — not to 27002, 27005, or any other in the family.

---

## 🏢 ISO/IEC 27001 Overview <a name="iso-27001-overview"></a>

### Key Facts

| Attribute | Detail |
|---|---|
| **Full Name** | ISO/IEC 27001 — Information Security Management Systems |
| **Type** | International Standard — Requirements |
| **Published by** | ISO and IEC jointly |
| **Purpose** | Specify requirements for establishing, implementing, maintaining, and continually improving an ISMS |
| **Certification** | ✅ Yes — organizations can be audited and certified |
| **Applicability** | Any organization — any size, any sector, any country |
| **Approach** | Risk-based — identify risks and apply controls to treat them |
| **Current Version** | ISO/IEC 27001:2022 |
| **Key Companion** | ISO/IEC 27002 — guidance for control implementation |

### What ISO 27001 Requires
- Establish, implement, maintain, and **continually improve** an ISMS
- Conduct **risk assessments** to identify information security risks
- Select and implement **controls** to treat identified risks
- Produce documented **policies and procedures**
- Define **objectives** and measure performance
- Conduct **internal audits** and **management reviews**
- Address **nonconformities** and take corrective actions

---

## 📜 History of ISO/IEC 27001 <a name="history"></a>

```
1992 → UK Department of Trade and Industry (DTI) publishes
        Code of Practice for Information Security Management

1995 → British Standards Institution (BSI) publishes
        BS 7799 Part 1
        (Code of Practice for Information Security Management)

1998 → BSI publishes BS 7799 Part 2
        (Specification for ISMS — the certifiable part)

1999 → BS 7799 Part 1 revised and expanded

2000 → BS 7799 Part 1 adopted as ISO/IEC 17799:2000
        (International Code of Practice)

2002 → BS 7799 Part 2:2002 published
        (Updated ISMS specification)

2005 → ISO/IEC 27001:2005 published
        (First ISO ISMS standard — replaced BS 7799 Part 2)
        ISO/IEC 17799:2005 also published

2007 → ISO/IEC 17799 renumbered to ISO/IEC 27002:2007

2013 → ISO/IEC 27001:2013 published
        (Major revision — 14 domains, 114 controls)
        ISO/IEC 27002:2013 published

2022 → ISO/IEC 27001:2022 published (October 2022)
        (Latest version — 4 themes, 93 controls)
        ISO/IEC 27002:2022 published (February 2022)
```

> [!TIP]
> Key history facts for MCQs:
> - **BS 7799** = British precursor to ISO 27001
> - **First ISO version = 27001:2005**
> - **2013 version = 14 domains, 114 controls**
> - **2022 version = 4 themes, 93 controls** (current)

---

## ⚙️ How the Standard Works <a name="how-it-works"></a>

### Core Concept — Risk-Based Approach
ISO 27001 works on a **risk-based model**:

```
1. Identify information assets
        ↓
2. Identify threats and vulnerabilities
        ↓
3. Assess the risk (likelihood × impact)
        ↓
4. Decide how to treat the risk
   (Accept / Avoid / Transfer / Mitigate)
        ↓
5. Select and implement controls from Annex A
        ↓
6. Monitor and review controls
        ↓
7. Continually improve the ISMS
```

### The ISMS Lifecycle
- ISO 27001 is NOT a one-time exercise — it requires **continual
  improvement**
- Built on the **PDCA cycle (Plan-Do-Check-Act)**
- Certification is valid for **3 years** — with annual surveillance audits
- Organizations must show continuous improvement to maintain certification

### What ISO 27001 Does NOT Do
- Does NOT specify which controls must be implemented — that depends on
  the organization's **risk assessment**
- Does NOT guarantee zero breaches — it provides a **management framework**
- Does NOT apply to a specific technology — it is **technology neutral**

> [!IMPORTANT]
> ISO 27001 is **technology neutral and sector neutral** — it applies
> to any type of organization regardless of size, industry, or technology
> used. A hospital, a bank, and a software company can all be ISO 27001
> certified.

---

## 📐 Structure of ISO/IEC 27001 <a name="structure"></a>

ISO 27001 follows the **High-Level Structure (HLS)** — also called
**Annex SL** — a common framework shared by all ISO management system
standards (also used by ISO 9001, ISO 14001, etc.)

### Full Structure Overview

```
ISO/IEC 27001
│
├── Clause 0  → Introduction
├── Clause 1  → Scope
├── Clause 2  → Normative References
├── Clause 3  → Terms and Definitions
├── Clause 4  → Context of the Organization  [MANDATORY]
├── Clause 5  → Leadership                   [MANDATORY]
├── Clause 6  → Planning                     [MANDATORY]
├── Clause 7  → Support                      [MANDATORY]
├── Clause 8  → Operation                    [MANDATORY]
├── Clause 9  → Performance Evaluation       [MANDATORY]
├── Clause 10 → Improvement                  [MANDATORY]
└── Annex A   → Reference Control Objectives and Controls
```

> [!IMPORTANT]
> **Clauses 4–10 are MANDATORY** for certification. Clauses 0–3 are
> introductory. Annex A is **normative** (referenced in Clause 6.1.3)
> but individual controls are selected based on risk assessment.

---

### 📋 Clauses 0–3 — Introductory <a name="clauses-0-5"></a>

| Clause | Content |
|---|---|
| **Clause 0** | Introduction — explains the standard's purpose and approach |
| **Clause 1** | Scope — defines what the standard covers |
| **Clause 2** | Normative References — references to ISO/IEC 27000 for definitions |
| **Clause 3** | Terms and Definitions — refers to ISO/IEC 27000 vocabulary |

---

### 📋 Clause 4 — Context of the Organization <a name="clause-4"></a>

**Purpose:** Understand the organization and its context before building
the ISMS

| Requirement | Description |
|---|---|
| **4.1** | Understand the organization — internal and external issues |
| **4.2** | Understand needs and expectations of interested parties |
| **4.3** | Determine the scope of the ISMS |
| **4.4** | ISMS — establish, implement, maintain, continually improve |

> [!NOTE]
> **Clause 4.3 — Scope** is critical — organizations can choose to certify
> only a part of their operations (e.g., one department or one data center).
> The scope must be documented and justified.

---

### 📋 Clause 5 — Leadership <a name="clause-5"></a>

**Purpose:** Ensure top management is committed to and involved in the ISMS

| Requirement | Description |
|---|---|
| **5.1** | Leadership and commitment — top management must demonstrate commitment |
| **5.2** | Policy — establish an information security policy |
| **5.3** | Roles, responsibilities, and authorities — assign who does what |

> [!IMPORTANT]
> ISO 27001 requires **top management commitment** — security cannot just
> be an IT department responsibility. The standard explicitly requires
> leadership involvement and a signed information security policy.

---

### 📋 Clause 6 — Planning <a name="clause-6"></a>

**Purpose:** Plan how to address risks and opportunities

| Requirement | Description |
|---|---|
| **6.1.1** | Actions to address risks and opportunities |
| **6.1.2** | Information security risk assessment — define process, criteria, conduct assessment |
| **6.1.3** | Information security risk treatment — select controls, produce Statement of Applicability (SoA) |
| **6.2** | Information security objectives — set measurable security objectives |
| **6.3** | Planning of changes — manage changes to the ISMS |

> [!IMPORTANT]
> **Clause 6.1.3** requires producing a **Statement of Applicability (SoA)**
> — one of the most important documents in ISO 27001. It lists all Annex A
> controls, states which are included/excluded, and justifies each decision.

---

### 📋 Clause 7 — Support <a name="clause-7"></a>

**Purpose:** Provide resources and support for the ISMS

| Requirement | Description |
|---|---|
| **7.1** | Resources — provide necessary human and financial resources |
| **7.2** | Competence — ensure people have required skills and training |
| **7.3** | Awareness — all relevant staff must be aware of the security policy |
| **7.4** | Communication — plan internal and external communications |
| **7.5** | Documented information — create and control required documents |

---

### 📋 Clause 8 — Operation <a name="clause-8"></a>

**Purpose:** Implement and control the ISMS processes

| Requirement | Description |
|---|---|
| **8.1** | Operational planning and control — implement plans from Clause 6 |
| **8.2** | Information security risk assessment — conduct assessments at planned intervals |
| **8.3** | Information security risk treatment — implement the risk treatment plan |

---

### 📋 Clause 9 — Performance Evaluation <a name="clause-9"></a>

**Purpose:** Monitor, measure, analyze, and evaluate the ISMS

| Requirement | Description |
|---|---|
| **9.1** | Monitoring, measurement, analysis, and evaluation |
| **9.2** | Internal audit — conduct at planned intervals |
| **9.3** | Management review — top management reviews ISMS performance |

> [!TIP]
> **Internal Audit (9.2) + Management Review (9.3)** are two of the most
> commonly tested clauses. Both are mandatory and both feed into
> Clause 10 (Improvement).

---

### 📋 Clause 10 — Improvement <a name="clause-10"></a>

**Purpose:** Continually improve the ISMS

| Requirement | Description |
|---|---|
| **10.1** | Continual improvement — always improving ISMS effectiveness |
| **10.2** | Nonconformity and corrective action — address failures, find root cause, fix |

---

## 🛡️ Annex A — Controls <a name="annex-a"></a>

- **Annex A** provides a reference set of **information security controls**
- Organizations select controls based on their **risk assessment results**
- Not all controls are mandatory — selection depends on applicable risks
- The **Statement of Applicability (SoA)** documents which controls are
  included and why

### Annex A Across Versions

| Version | Structure | Controls |
|---|---|---|
| **27001:2005** | 11 Domains | 133 controls |
| **27001:2013** | 14 Domains / Clauses | 114 controls |
| **27001:2022** | 4 Themes | 93 controls |

---

## 📋 ISO/IEC 27001:2005 Domains — 11 Domains <a name="domains-2005"></a>

The original 2005 version organized controls into **11 domains**:

| # | Domain | Key Focus |
|---|---|---|
| **A.5** | Security Policy | Information security policy — management direction |
| **A.6** | Organization of Information Security | Internal organization, external parties |
| **A.7** | Asset Management | Asset inventory, classification, ownership |
| **A.8** | Human Resources Security | Pre-employment, during employment, termination |
| **A.9** | Physical and Environmental Security | Secure areas, equipment security |
| **A.10** | Communications and Operations Management | Operational procedures, malware, backup, monitoring |
| **A.11** | Access Control | User access management, network access, OS access |
| **A.12** | Information Systems Acquisition, Development & Maintenance | Security in development, cryptographic controls |
| **A.13** | Information Security Incident Management | Reporting events, management of incidents |
| **A.14** | Business Continuity Management | BCM process, continuity planning, testing |
| **A.15** | Compliance | Legal compliance, technical compliance, audit |

> [!TIP]
> Memory trick for 11 domains (2005):
> **"Some Organizations Always Have Physical Communications,
> Access Information, Incidents, Business Compliance"**
> Security Policy → Organization → Asset → Human Resources →
> Physical → Communications → Access → IS Acquisition →
> Incidents → Business Continuity → Compliance

---

## 📋 ISO/IEC 27001:2013 Control Domains <a name="domains-2013"></a>

The 2013 version reorganized into **14 domains** with **114 controls**:

| # | Domain | Controls |
|---|---|---|
| **A.5** | Information Security Policies | 2 |
| **A.6** | Organization of Information Security | 7 |
| **A.7** | Human Resource Security | 6 |
| **A.8** | Asset Management | 10 |
| **A.9** | Access Control | 14 |
| **A.10** | Cryptography | 2 |
| **A.11** | Physical and Environmental Security | 15 |
| **A.12** | Operations Security | 14 |
| **A.13** | Communications Security | 7 |
| **A.14** | System Acquisition, Development and Maintenance | 13 |
| **A.15** | Supplier Relationships | 5 |
| **A.16** | Information Security Incident Management | 7 |
| **A.17** | Information Security Aspects of BCM | 4 |
| **A.18** | Compliance | 8 |
| **Total** | | **114** |

> [!NOTE]
> The 2013 version added **Cryptography (A.10)** and **Supplier
> Relationships (A.15)** as separate domains — these did not exist
> as standalone domains in the 2005 version.

---

## 🆕 ISO/IEC 27001:2022 — Latest Version <a name="version-2022"></a>

- Published: **October 2022**
- Major restructuring of Annex A — from **114 controls in 14 domains**
  to **93 controls in 4 themes**
- Organizations certified to 2013 version had until **October 2025**
  to transition

### 4 Themes in ISO/IEC 27001:2022 Annex A

| Theme | Controls |
|---|---|
| **5 — Organizational Controls** | 37 controls |
| **6 — People Controls** | 8 controls |
| **7 — Physical Controls** | 14 controls |
| **8 — Technological Controls** | 34 controls |
| **Total** | **93 controls** |

### New Controls Added in 2022 (Not in 2013)
- Threat intelligence
- Information security for use of cloud services
- ICT readiness for business continuity
- Physical security monitoring
- Configuration management
- Information deletion
- Data masking
- Data leakage prevention
- Monitoring activities
- Web filtering
- Secure coding

> [!IMPORTANT]
> **Key version numbers to memorize:**
> - **2005** → 11 domains, 133 controls
> - **2013** → 14 domains, 114 controls
> - **2022** → 4 themes, 93 controls (current)

---

## 🏗️ ISMS — Information Security Management System <a name="isms"></a>

- **ISMS = Information Security Management System**
- The core output of implementing ISO 27001
- A systematic approach to managing sensitive information so it
  remains secure
- Covers **people, processes, and technology** — not just IT

### ISMS Components

| Component | Examples |
|---|---|
| **Policies** | Information security policy, acceptable use policy |
| **Procedures** | Incident response procedure, access control procedure |
| **Processes** | Risk assessment process, audit process |
| **Controls** | Technical controls, physical controls, organizational controls |
| **Records** | Risk assessment results, audit reports, training records |

### ISMS Scope
- Can cover the **entire organization** or just a **part of it**
- Must be clearly defined and documented
- Scope boundaries are audited during certification
- Physical locations, assets, technology, and processes within scope
  must be specified

---

## 🏆 ISO 27001 Certification Process <a name="certification"></a>

```
Stage 1 → Stage 1 Audit (Documentation Review)
           Certification body reviews ISMS documents
           Checks readiness for Stage 2
           Issues Stage 1 findings — organization must address gaps
                ↓
Stage 2 → Stage 2 Audit (Certification Audit)
           On-site evaluation of ISMS implementation
           Tests whether controls are actually working
           Issues certificate if compliant
                ↓
Annual  → Surveillance Audits (Year 1 and Year 2)
           Verify ISMS continues to function
           Smaller scope than full audit
                ↓
Year 3  → Recertification Audit
           Full re-evaluation — renew certificate for another 3 years
```

### Key Certification Facts

| Fact | Detail |
|---|---|
| **Certificate validity** | 3 years |
| **Surveillance audits** | Annual (Years 1 and 2) |
| **Recertification** | Every 3 years |
| **Conducted by** | Accredited Certification Bodies (not ISO itself) |
| **ISO's role** | ISO publishes the standard — does NOT conduct audits |
| **Stage 1** | Document review — readiness check |
| **Stage 2** | Implementation audit — actual certification |

> [!WARNING]
> **ISO does NOT certify organizations** — accredited third-party
> **Certification Bodies** conduct the audits and issue certificates.
> ISO only publishes the standard. This is a very common MCQ trap.

---

## 📌 Extra Notes <a name="extra-notes"></a>

> [!NOTE]
> The concepts below extend beyond the basic syllabus but are directly
> MCQ-relevant. Worth knowing cold before the exam.

---

### 📚 ISO 2700x Family — Other Key Standards <a name="2700x-others"></a>

| Standard | Key Detail |
|---|---|
| **ISO/IEC 27000** | Vocabulary — defines all terms used across the 2700x family |
| **ISO/IEC 27002** | Guidance for implementing 27001 controls — NOT certifiable |
| **ISO/IEC 27005** | Risk management — how to do the risk assessment required by 27001 |
| **ISO/IEC 27017** | Cloud security — additional controls for cloud providers and users |
| **ISO/IEC 27018** | PII protection in public clouds — relates to GDPR compliance |
| **ISO/IEC 27701** | Privacy extension to 27001 — helps demonstrate GDPR compliance |

> [!TIP]
> **ISO/IEC 27701** is particularly important — it extends 27001 to
> cover **privacy information management** and directly helps organizations
> demonstrate GDPR compliance. Organizations certified to 27001 can add
> 27701 certification for privacy.

---

### 🔄 Plan-Do-Check-Act (PDCA) Cycle <a name="pdca"></a>

ISO 27001 is built on the **PDCA cycle** — a continuous improvement model:

```
┌─────────────────────────────────────────────┐
│                                             │
│   PLAN  →  Establish ISMS                   │
│            (Clauses 4, 5, 6, 7)             │
│      ↓                                      │
│   DO    →  Implement and operate ISMS       │
│            (Clause 8)                       │
│      ↓                                      │
│   CHECK →  Monitor and review ISMS          │
│            (Clause 9)                       │
│      ↓                                      │
│   ACT   →  Maintain and improve ISMS        │
│            (Clause 10)                      │
│      ↑                                      │
│      └──────────── continual loop ──────────┘
│                                             │
└─────────────────────────────────────────────┘
```

| PDCA Phase | ISO 27001 Clauses | Activities |
|---|---|---|
| **Plan** | 4, 5, 6, 7 | Context, leadership, risk assessment, planning, support |
| **Do** | 8 | Implement controls, operate ISMS |
| **Check** | 9 | Monitor, measure, internal audit, management review |
| **Act** | 10 | Corrective actions, continual improvement |

---

### 📄 Statement of Applicability (SoA) <a name="soa"></a>

- **SoA = Statement of Applicability** — required by Clause 6.1.3
- One of the **most important ISO 27001 documents**
- Lists **all Annex A controls** and for each one states:
  - Is it **included or excluded**?
  - **Justification** for inclusion/exclusion
  - **Implementation status**

### Why SoA Matters
- Auditors review the SoA to verify risk treatment decisions
- Shows the link between risk assessment results and selected controls
- Demonstrates that exclusions are justified — not just convenient
- Required as mandatory documented information

> [!IMPORTANT]
> The **SoA is the bridge** between the risk assessment (what risks
> were found) and Annex A (what controls exist). It explains why
> certain controls are relevant and others are not.

---

### 🛠️ Risk Treatment Options <a name="risk-treatment"></a>

After assessing risks, ISO 27001 requires organizations to decide how
to treat each risk — 4 options:

| Option | Description | Example |
|---|---|---|
| **Modify (Mitigate)** | Implement controls to reduce the risk | Install firewall to reduce network attack risk |
| **Accept** | Consciously accept the risk — document the decision | Accept low-likelihood risk that's too expensive to mitigate |
| **Avoid** | Stop the activity that creates the risk | Stop using an insecure system entirely |
| **Transfer (Share)** | Move the risk to a third party | Buy cyber insurance, outsource to a managed service |

> [!NOTE]
> The four risk treatment options are sometimes called **MAAT** or
> remember them as **Modify, Accept, Avoid, Transfer**. All four are
> valid — the choice depends on cost-benefit analysis and risk tolerance.

---

### ⚖️ ISO 27001 vs NIST CSF Comparison <a name="iso-vs-nist"></a>

| Feature | ISO/IEC 27001 | NIST CSF |
|---|---|---|
| **Type** | Standard — requirements | Framework — guidance |
| **Certification** | ✅ Yes | ❌ No |
| **Mandatory** | Voluntary | Voluntary (mandatory US federal) |
| **Origin** | International (ISO/IEC) | USA (NIST) |
| **Cost** | Paid standard | Free |
| **Approach** | Prescriptive — specific requirements | Flexible — outcome-based |
| **Audit** | Third-party certification audit | No formal audit |
| **Scope** | Information security management | Cybersecurity risk management |
| **Based on** | Risk assessment | Risk-based functions |
| **Update** | 2005 → 2013 → 2022 | 2014 → 2018 → 2024 |

---

### 📘 ISO 27001 vs ISO 27002 <a name="27001-vs-27002"></a>

This is one of the most common exam confusions:

| | ISO/IEC 27001 | ISO/IEC 27002 |
|---|---|---|
| **Type** | Requirements standard | Guidance / Code of Practice |
| **Certifiable** | ✅ Yes | ❌ No |
| **Content** | ISMS requirements (Clauses 4–10) + Annex A control list | Detailed guidance for implementing each Annex A control |
| **Purpose** | WHAT the ISMS must include | HOW to implement the controls |
| **Analogy** | The exam requirements | The study guide |

> [!TIP]
> Think of it this way:
> **27001 = the LAW** (what you must do)
> **27002 = the GUIDANCE** (how to do it)
> You get certified to **27001**, you USE **27002** to help implement it.

---

## 🔤 Abbreviations <a name="abbreviations"></a>

| Abbreviation | Full Form | One-line Meaning |
|---|---|---|
| **ISO** | International Organization for Standardization | Independent international body that publishes global standards |
| **IEC** | International Electrotechnical Commission | International body for electrotechnical standards — works with ISO |
| **ISMS** | Information Security Management System | Systematic framework for managing information security risks |
| **SoA** | Statement of Applicability | Document listing all Annex A controls with inclusion/exclusion justification |
| **PDCA** | Plan-Do-Check-Act | Continuous improvement cycle underpinning ISO 27001 |
| **HLS** | High-Level Structure | Common framework shared by all ISO management system standards |
| **BIS** | Bureau of Indian Standards | India's national standards body — ISO member |
| **BSI** | British Standards Institution | UK standards body — created BS 7799 which became ISO 27001 |
| **BCM** | Business Continuity Management | Planning for continued operations during/after disruptions |
| **RTP** | Risk Treatment Plan | Document describing how identified risks will be treated |
| **CIA** | Confidentiality, Integrity, Availability | Three core information security properties protected by ISO 27001 |
| **CISO** | Chief Information Security Officer | Senior executive responsible for information security program |
| **PII** | Personally Identifiable Information | Information that can identify a natural person |

---

## 🗝️ Keywords & Concept Map <a name="keywords"></a>

**ISO/IEC 27001**
→ International standard for Information Security Management Systems
→ Published jointly by ISO and IEC
→ Only certifiable standard in the 2700x family
→ Versions: 2005 (11 domains) → 2013 (14 domains, 114 controls) →
  2022 (4 themes, 93 controls)
→ Applies to any organization — any size, sector, country

**ISMS (Information Security Management System)**
→ The systematic framework ISO 27001 requires
→ Covers people, processes, and technology
→ Built on PDCA cycle — continual improvement
→ Scope must be defined and documented
→ Certified by accredited third-party bodies — not by ISO

**Annex A**
→ Reference control set — normative but not all mandatory
→ Selection based on risk assessment results
→ 2005: 133 controls / 2013: 114 controls / 2022: 93 controls
→ SoA documents which controls are included and why

**Statement of Applicability (SoA)**
→ Most important ISO 27001 document
→ Lists all Annex A controls with include/exclude + justification
→ Required by Clause 6.1.3
→ Bridge between risk assessment and control selection

**Risk Treatment**
→ What to do with assessed risks: Modify, Accept, Avoid, Transfer
→ Documented in Risk Treatment Plan
→ Links to SoA — selected controls implement risk treatment decisions

**BS 7799**
→ British precursor to ISO 27001
→ Part 1 became ISO 17799 then ISO 27002
→ Part 2 became ISO 27001
→ Created by BSI (British Standards Institution)

---

## ⚡ Quick Reference Cheatsheet <a name="cheatsheet"></a>

### ISO 27001 Version History

| Version | Year | Domains/Themes | Controls |
|---|---|---|---|
| BS 7799 Part 2 | 1998 | — | — |
| **ISO 27001:2005** | 2005 | 11 Domains | 133 |
| **ISO 27001:2013** | 2013 | 14 Domains | 114 |
| **ISO 27001:2022** | 2022 | 4 Themes | 93 |

### ISO 27001:2005 — 11 Domains

| # | Domain |
|---|---|
| A.5 | Security Policy |
| A.6 | Organization of Information Security |
| A.7 | Asset Management |
| A.8 | Human Resources Security |
| A.9 | Physical and Environmental Security |
| A.10 | Communications and Operations Management |
| A.11 | Access Control |
| A.12 | IS Acquisition, Development & Maintenance |
| A.13 | Information Security Incident Management |
| A.14 | Business Continuity Management |
| A.15 | Compliance |

### ISO 27001:2013 — 14 Domains

| # | Domain | Controls |
|---|---|---|
| A.5 | Information Security Policies | 2 |
| A.6 | Organization of Information Security | 7 |
| A.7 | Human Resource Security | 6 |
| A.8 | Asset Management | 10 |
| A.9 | Access Control | 14 |
| A.10 | Cryptography | 2 |
| A.11 | Physical and Environmental Security | 15 |
| A.12 | Operations Security | 14 |
| A.13 | Communications Security | 7 |
| A.14 | System Acquisition, Development & Maintenance | 13 |
| A.15 | Supplier Relationships | 5 |
| A.16 | Information Security Incident Management | 7 |
| A.17 | Information Security Aspects of BCM | 4 |
| A.18 | Compliance | 8 |
| **Total** | | **114** |

### ISO 27001:2022 — 4 Themes

| Theme | Controls |
|---|---|
| 5 — Organizational | 37 |
| 6 — People | 8 |
| 7 — Physical | 14 |
| 8 — Technological | 34 |
| **Total** | **93** |

### ISO 27001 Mandatory Clauses

| Clause | Topic |
|---|---|
| 4 | Context of the Organization |
| 5 | Leadership |
| 6 | Planning |
| 7 | Support |
| 8 | Operation |
| 9 | Performance Evaluation |
| 10 | Improvement |

### PDCA Mapping to ISO 27001 Clauses

| Phase | Clauses | Activity |
|---|---|---|
| Plan | 4, 5, 6, 7 | Establish ISMS |
| Do | 8 | Implement ISMS |
| Check | 9 | Monitor and review |
| Act | 10 | Improve ISMS |

### Risk Treatment Options

| Option | Action |
|---|---|
| Modify (Mitigate) | Implement controls to reduce risk |
| Accept | Document and consciously accept risk |
| Avoid | Stop the risk-creating activity |
| Transfer (Share) | Insurance or outsourcing |

### ISO 27001 vs ISO 27002

| | 27001 | 27002 |
|---|---|---|
| Type | Requirements | Guidance |
| Certifiable | ✅ Yes | ❌ No |
| Content | WHAT to do | HOW to do it |

### ISO 27001 Certification Timeline

| Stage | Activity |
|---|---|
| Stage 1 Audit | Document review — readiness check |
| Stage 2 Audit | Implementation audit — certification |
| Year 1 & 2 | Annual surveillance audits |
| Year 3 | Recertification audit |
| Certificate validity | 3 years |

---

## 🔁 Session Revision Snapshot <a name="snapshot"></a>

### TL;DR — 5 Bullets
- ✅ ISO 27001 = international standard for ISMS — only certifiable
  standard in 2700x family — applies to any org of any size or sector
- ✅ Three versions: **2005 (11 domains, 133 controls)** →
  **2013 (14 domains, 114 controls)** → **2022 (4 themes, 93 controls)**
- ✅ Mandatory clauses are 4–10 — built on PDCA cycle —
  Clause 6.1.3 requires Statement of Applicability (SoA)
- ✅ ISO does NOT certify — accredited third-party Certification Bodies do —
  certificate valid for 3 years with annual surveillance audits
- ✅ Risk treatment options: **Modify, Accept, Avoid, Transfer** —
  selection documented in Risk Treatment Plan and reflected in SoA

### 🎯 Top MCQ-Likely Concepts from This Session
1. **Version numbers** — 2005 (11/133), 2013 (14/114), 2022 (4/93)
2. **11 domains of 2005 version** — know all by name
3. **14 domains of 2013 version** — especially the new ones (Cryptography,
   Supplier Relationships)
4. **ISO does NOT certify** — Certification Bodies do
5. **SoA = Statement of Applicability** — what it is and which clause requires it
6. **PDCA cycle** — which clauses map to which phase
7. **ISO 27001 vs ISO 27002** — requirements vs guidance, certifiable vs not
8. **Risk treatment options** — Modify, Accept, Avoid, Transfer
9. **BS 7799** — British precursor to ISO 27001
10. **Mandatory clauses = 4 to 10**

---