# 🏛️ Session 03 — NIST Framework

## 📑 Table of Contents
- [What is NIST](#what-is-nist)
- [NIST Overview](#nist-overview)
- [NIST Cybersecurity Framework (CSF)](#nist-csf)
- [CSF Core — 5 Functions](#csf-core)
  - [Identify](#identify)
  - [Protect](#protect)
  - [Detect](#detect)
  - [Respond](#respond)
  - [Recover](#recover)
- [CSF Implementation Tiers](#csf-tiers)
- [CSF Profiles](#csf-profiles)
- [Components of the Framework — Summary](#components-summary)
- [Use of Framework](#use-of-framework)
- [NIST Risk Management Framework (RMF)](#nist-rmf)
- [NIST SP 800 Series — Key Publications](#sp800)
- [📌 Extra Notes](#extra-notes)
  - [NIST CSF 2.0 — Govern Function](#csf-20)
  - [NIST SP 800-53 — Security Controls](#sp800-53)
  - [NIST SP 800-37 — RMF Steps](#sp800-37)
  - [NIST SP 800-171](#sp800-171)
  - [NIST vs ISO 27001 Comparison](#nist-vs-iso)
  - [Voluntary vs Mandatory](#voluntary-vs-mandatory)
- [Abbreviations](#abbreviations)
- [Keywords & Concept Map](#keywords)
- [Quick Reference Cheatsheet](#cheatsheet)
- [Session Revision Snapshot](#snapshot)

---

## 🔰 What is NIST <a name="what-is-nist"></a>

- **NIST = National Institute of Standards and Technology**
- A **US federal agency** under the Department of Commerce
- Founded in **1901** — one of the oldest US physical science labs
- Mission: Promote US innovation and industrial competitiveness by advancing
  measurement science, standards, and technology
- In cybersecurity context: NIST develops **frameworks, guidelines, and
  standards** that organizations use to manage cybersecurity risk
- NIST does **NOT enforce** compliance — its frameworks are generally
  **voluntary** (except when mandated for federal agencies)

> [!NOTE]
> NIST is a US government agency but its frameworks are used **globally** —
> not just in the USA. The NIST Cybersecurity Framework is adopted worldwide
> by organizations of all sizes and sectors.

---

## 🏢 NIST Overview <a name="nist-overview"></a>

### Key Facts

| Attribute | Detail |
|---|---|
| **Full Name** | National Institute of Standards and Technology |
| **Type** | US Federal Agency |
| **Under** | Department of Commerce |
| **Founded** | 1901 |
| **HQ** | Gaithersburg, Maryland, USA |
| **Cybersecurity Role** | Develops frameworks, guidelines, and standards |
| **Enforcement** | Generally voluntary (mandatory for US federal agencies) |
| **Key Output** | NIST CSF, NIST RMF, SP 800 series publications |

### Why NIST Matters for Cybersecurity

- Provides a **common language** for cybersecurity risk management
- Helps organizations of **any size, sector, or maturity level** improve
  their security posture
- Used as baseline for **government procurement** requirements
- Referenced by other frameworks (ISO, COBIT) and regulations (HIPAA, FedRAMP)
- Bridges gap between **technical teams and business leadership**

---

## 🛡️ NIST Cybersecurity Framework (CSF) <a name="nist-csf"></a>

- **NIST CSF** = The most widely used cybersecurity framework globally
- Originally published in **February 2014** as **CSF 1.0**
- Created in response to **Executive Order 13636** — "Improving Critical
  Infrastructure Cybersecurity"
- Updated to **CSF 1.1 in April 2018**
- Latest version: **CSF 2.0 — February 2024** (adds Govern function)
- Designed for **critical infrastructure** initially but adopted universally

### What CSF Provides
- A **risk-based approach** to managing cybersecurity
- Common language for internal and external communication about cyber risk
- Flexible enough to integrate with existing security programs
- Not prescriptive — organizations choose **how** to implement it

### Three Main Components of CSF

```
NIST Cybersecurity Framework
│
├── 1. Framework Core      → WHAT to do (5 Functions)
├── 2. Implementation Tiers → HOW WELL you're doing it (Tiers 1–4)
└── 3. Framework Profile   → WHERE you are vs WHERE you want to be
```

> [!IMPORTANT]
> These three components — **Core, Tiers, and Profiles** — are the backbone
> of the NIST CSF. Every MCQ about "components of the framework" is testing
> whether you know these three.

---

## ⚙️ CSF Core — 5 Functions <a name="csf-core"></a>

The **Framework Core** organizes cybersecurity activities into **5 Functions**.
Each function contains **Categories** and **Subcategories** of specific
activities.

```
IDENTIFY → PROTECT → DETECT → RESPOND → RECOVER
```

> [!TIP]
> Memory trick: **"I P D R R"** → **"I Prefer Driving Really Responsibly"**
> Or simply remember the logical flow: Know your assets → Protect them →
> Watch for issues → React when hit → Bounce back

---

### 🔍 Identify <a name="identify"></a>

- **Purpose:** Develop understanding of how to manage cybersecurity risk to
  systems, assets, data, and capabilities
- Answers: *"What do we have and what are the risks?"*
- This function is the **foundation** — you cannot protect what you don't know

**Key Activities Under Identify:**

| Category | What It Covers |
|---|---|
| **Asset Management** | Inventory of all hardware, software, data assets |
| **Business Environment** | Understanding organization's mission and critical functions |
| **Governance** | Policies, procedures, and legal requirements |
| **Risk Assessment** | Identifying threats, vulnerabilities, and risk levels |
| **Risk Management Strategy** | Priorities, constraints, and risk tolerance |
| **Supply Chain Risk** | Managing risks from third-party vendors |

---

### 🔒 Protect <a name="protect"></a>

- **Purpose:** Develop and implement appropriate safeguards to ensure delivery
  of critical services
- Answers: *"How do we prevent or limit impact of a cybersecurity event?"*
- Focuses on **limiting or containing** the impact of potential incidents

**Key Activities Under Protect:**

| Category | What It Covers |
|---|---|
| **Identity Management & Access Control** | Who can access what — authentication, authorization |
| **Awareness and Training** | Security training for all staff |
| **Data Security** | Protection of data at rest and in transit |
| **Information Protection Processes** | Security policies, backups, software development practices |
| **Maintenance** | Maintenance of systems and components |
| **Protective Technology** | Technical controls — firewalls, encryption, logging |

---

### 👁️ Detect <a name="detect"></a>

- **Purpose:** Develop and implement appropriate activities to identify the
  occurrence of a cybersecurity event
- Answers: *"How do we know when something bad is happening?"*
- Focuses on **timely discovery** of cybersecurity events

**Key Activities Under Detect:**

| Category | What It Covers |
|---|---|
| **Anomalies and Events** | Detecting unusual activity and understanding its impact |
| **Security Continuous Monitoring** | Ongoing monitoring of systems and assets |
| **Detection Processes** | Maintaining detection processes and procedures |

---

### 🚨 Respond <a name="respond"></a>

- **Purpose:** Develop and implement appropriate activities to take action
  regarding a detected cybersecurity event
- Answers: *"What do we do when we find an incident?"*
- Focuses on **containing the impact** of a cybersecurity incident

**Key Activities Under Respond:**

| Category | What It Covers |
|---|---|
| **Response Planning** | Incident response processes and procedures |
| **Communications** | Coordinating with internal and external stakeholders |
| **Analysis** | Analyzing the incident to understand its nature |
| **Mitigation** | Containing and eradicating the incident |
| **Improvements** | Learning from incidents to improve response |

---

### 🔄 Recover <a name="recover"></a>

- **Purpose:** Develop and implement appropriate activities to maintain plans
  for resilience and restore capabilities after a cybersecurity incident
- Answers: *"How do we get back to normal?"*
- Focuses on **timely restoration** of normal operations

**Key Activities Under Recover:**

| Category | What It Covers |
|---|---|
| **Recovery Planning** | Processes and procedures for restoration |
| **Improvements** | Incorporating lessons learned into recovery plans |
| **Communications** | Managing reputation and communicating recovery status |

---

## 📊 CSF Implementation Tiers <a name="csf-tiers"></a>

- **Tiers** describe how an organization's cybersecurity risk management
  practices measure up against the CSF
- Range from **Tier 1 (Partial)** to **Tier 4 (Adaptive)**
- Tiers are **NOT maturity levels** — they are descriptors of how
  **integrated and sophisticated** risk management is
- Higher tier ≠ always the goal — the right tier depends on
  **organizational risk tolerance and objectives**

| Tier | Name | Description |
|---|---|---|
| **Tier 1** | Partial | No formal process — reactive, ad hoc. Risk management not formalized |
| **Tier 2** | Risk Informed | Risk management practices exist but not organization-wide. Informal |
| **Tier 3** | Repeatable | Formally approved policies. Consistently implemented across organization |
| **Tier 4** | Adaptive | Actively adapts based on lessons learned and changing threats. Proactive |

> [!WARNING]
> Common MCQ trap: **Tiers are NOT maturity levels** — NIST explicitly says
> higher tiers are not necessarily the target for all organizations. The right
> tier is based on **risk appetite and business needs**, not ambition.

> [!TIP]
> **Memory trick for Tiers:**
> **P-R-R-A** → **"Please Remember Risk Adapts"**
> Partial → Risk Informed → Repeatable → Adaptive

---

## 👤 CSF Profiles <a name="csf-profiles"></a>

- A **Profile** represents the alignment of the Framework Core functions,
  categories, and subcategories with the organization's:
  - Business requirements
  - Risk tolerance
  - Available resources
- Two types of profiles:

| Profile Type | Description |
|---|---|
| **Current Profile** | Where the organization IS right now |
| **Target Profile** | Where the organization WANTS to be |

- The **gap between Current and Target Profile** drives the cybersecurity
  improvement roadmap
- Profiles help prioritize actions and communicate risk management internally

> [!NOTE]
> Think of it this way: **Current Profile = AS-IS state**, **Target Profile =
> TO-BE state**. The gap analysis between them tells you exactly what needs
> to be done.

---

## 🗂️ Components of the Framework — Summary <a name="components-summary"></a>

| Component | What It Is | Purpose |
|---|---|---|
| **Framework Core** | 5 Functions (IPDRR) with categories & subcategories | WHAT cybersecurity activities to perform |
| **Implementation Tiers** | 4 levels (Partial → Adaptive) | HOW WELL the organization manages cyber risk |
| **Framework Profile** | Current vs Target state | WHERE the organization is and WHERE it wants to go |

---

## 🔧 Use of Framework <a name="use-of-framework"></a>

### Who Uses NIST CSF
- US Federal agencies (mandatory via Executive Orders)
- Critical infrastructure operators (energy, water, healthcare, finance)
- Private sector organizations of all sizes
- International organizations (adopted globally)

### How Organizations Use CSF

| Use Case | How CSF Helps |
|---|---|
| **Basic Review** | Organizations new to cybersecurity use CSF to understand their current state |
| **Establish Program** | Build a new cybersecurity program from scratch using CSF as blueprint |
| **Improve Program** | Use gap analysis (Current vs Target Profile) to prioritize improvements |
| **Communicate Risk** | Common language for business leadership ↔ technical teams |
| **Procurement** | Require vendors to demonstrate CSF alignment |
| **Regulatory Alignment** | Map CSF to compliance requirements (HIPAA, PCI DSS etc.) |

### Step-by-Step Process for Using CSF

```
Step 1 → Prioritize and Scope
         Identify business objectives and critical functions

Step 2 → Orient
         Identify related systems, assets, regulatory requirements

Step 3 → Create Current Profile
         Document current cybersecurity outcomes

Step 4 → Conduct Risk Assessment
         Analyze threats and vulnerabilities

Step 5 → Create Target Profile
         Define desired cybersecurity outcomes

Step 6 → Determine, Analyze, Prioritize Gaps
         Compare Current and Target Profiles

Step 7 → Implement Action Plan
         Execute improvements based on gap analysis
```

---

## 🔁 NIST Risk Management Framework (RMF) <a name="nist-rmf"></a>

- **NIST RMF** = A structured process for integrating security and privacy
  risk management into the **system development lifecycle (SDLC)**
- Defined in **NIST SP 800-37**
- Mandatory for **US federal information systems**
- 7 steps (updated from original 6 with addition of Prepare step)

### RMF 7 Steps

| Step | Name | What Happens |
|---|---|---|
| **1** | **Prepare** | Establish context, priorities, and risk management roles |
| **2** | **Categorize** | Classify the system based on impact level (Low/Moderate/High) |
| **3** | **Select** | Choose appropriate security controls from SP 800-53 |
| **4** | **Implement** | Actually put the selected controls in place |
| **5** | **Assess** | Determine if controls are implemented correctly and working |
| **6** | **Authorize** | Senior official accepts residual risk and authorizes system operation |
| **7** | **Monitor** | Ongoing monitoring of controls and risk posture |

> [!TIP]
> **Memory trick for RMF Steps:**
> **P-C-S-I-A-A-M** →
> **"Please Create Secure Infrastructure And Always Monitor"**

---

## 📚 NIST SP 800 Series — Key Publications <a name="sp800"></a>

The **SP 800 series** = NIST Special Publication 800 series — computer
security guidelines

| Publication | Topic |
|---|---|
| **SP 800-12** | Introduction to Computer Security |
| **SP 800-30** | Guide for Conducting Risk Assessments |
| **SP 800-37** | Risk Management Framework (RMF) |
| **SP 800-39** | Managing Information Security Risk |
| **SP 800-53** | Security and Privacy Controls for Federal Information Systems |
| **SP 800-53A** | Assessing Security and Privacy Controls |
| **SP 800-61** | Computer Security Incident Handling Guide |
| **SP 800-92** | Guide to Computer Security Log Management |
| **SP 800-115** | Technical Guide to Information Security Testing |
| **SP 800-137** | Continuous Monitoring of Federal Information Systems |
| **SP 800-171** | Protecting Controlled Unclassified Information (CUI) |

> [!NOTE]
> You don't need to memorize all of them — but **SP 800-37 (RMF)** and
> **SP 800-53 (Controls)** are the most heavily tested in MCQs.

---

## 📌 Extra Notes <a name="extra-notes"></a>

> [!NOTE]
> The concepts below extend beyond the core syllabus but are directly
> MCQ-relevant. Cross-referenced from NIST official documentation and
> standard cybersecurity literature.

---

### 🆕 NIST CSF 2.0 — Govern Function <a name="csf-20"></a>

- **CSF 2.0** was released in **February 2024**
- Major change: Added a **6th function — GOVERN**
- CSF 2.0 now has **6 Functions: Govern, Identify, Protect, Detect,
  Respond, Recover**

```
CSF 1.1:  IDENTIFY → PROTECT → DETECT → RESPOND → RECOVER (5)
CSF 2.0:  GOVERN + IDENTIFY → PROTECT → DETECT → RESPOND → RECOVER (6)
```

### GOVERN Function

| Category | What It Covers |
|---|---|
| **Organizational Context** | Mission, stakeholder expectations, legal requirements |
| **Risk Management Strategy** | Risk tolerance, priorities, and strategy |
| **Roles & Responsibilities** | Who is accountable for what |
| **Policies** | Cybersecurity policy established and communicated |
| **Oversight** | Results of cybersecurity activities inform risk strategy |
| **Supply Chain Risk Management** | Cybersecurity in supply chain managed as risk |

> [!IMPORTANT]
> In CSF 2.0, **GOVERN is the overarching function** — it provides context
> and direction for all other five functions. It sits above and around the
> other five rather than being sequential.

---

### 🔐 NIST SP 800-53 — Security Controls <a name="sp800-53"></a>

- **SP 800-53** = Security and Privacy Controls for Information Systems
- Provides a **catalog of security controls** organized into **20 control
  families**
- Used as the control selection source in the **RMF (Step 3 — Select)**
- Control impact levels: **Low, Moderate, High**

### SP 800-53 Control Families (20 Families)

| ID | Family Name |
|---|---|
| AC | Access Control |
| AT | Awareness and Training |
| AU | Audit and Accountability |
| CA | Assessment, Authorization, Monitoring |
| CM | Configuration Management |
| CP | Contingency Planning |
| IA | Identification and Authentication |
| IR | Incident Response |
| MA | Maintenance |
| MP | Media Protection |
| PE | Physical and Environmental Protection |
| PL | Planning |
| PM | Program Management |
| PS | Personnel Security |
| PT | Personally Identifiable Information Processing |
| RA | Risk Assessment |
| SA | System and Services Acquisition |
| SC | System and Communications Protection |
| SI | System and Information Integrity |
| SR | Supply Chain Risk Management |

> [!TIP]
> You don't need to memorize all 20 — but knowing the **most common ones**
> (AC, AU, IA, IR, RA, SC, SI) will cover most MCQs.

---

### 🔄 NIST SP 800-37 — RMF Steps Detail <a name="sp800-37"></a>

More detail on the most tested RMF step — **Categorize (Step 2)**:

### FIPS 199 — System Categorization

| Impact Level | Definition |
|---|---|
| **Low** | Limited adverse effect on operations, assets, or individuals |
| **Moderate** | Serious adverse effect |
| **High** | Severe or catastrophic adverse effect |

- Categorization uses **FIPS 199** (Federal Information Processing Standard)
- Based on three security objectives: **Confidentiality, Integrity, Availability**
- The **highest impact level** across all three determines the overall system
  category

---

### 🏭 NIST SP 800-171 <a name="sp800-171"></a>

- Focused on protecting **CUI = Controlled Unclassified Information**
- Applies to **non-federal organizations** (contractors, suppliers) that
  handle federal CUI
- Contains **110 security requirements** across 14 families
- Basis for **CMMC (Cybersecurity Maturity Model Certification)** — required
  for US defense contractors

---

### ⚖️ NIST vs ISO 27001 Comparison <a name="nist-vs-iso"></a>

| Feature | NIST CSF | ISO 27001 |
|---|---|---|
| **Origin** | USA (NIST) | International (ISO/IEC) |
| **Type** | Framework / Guidance | Standard (certifiable) |
| **Certification** | ❌ No formal certification | ✅ Yes — can be certified |
| **Mandatory** | Voluntary (except US federal) | Voluntary globally |
| **Prescriptiveness** | Flexible — outcome-based | More prescriptive — control-based |
| **Cost** | Free to use | Paid standard document |
| **Audience** | All organizations | All organizations |
| **Focus** | Cybersecurity risk management | Information security management |
| **Update Cycle** | As needed | Periodic (2005, 2013, 2022) |

---

### ✅ Voluntary vs Mandatory <a name="voluntary-vs-mandatory"></a>

| Organization Type | NIST CSF Status |
|---|---|
| US Federal Agencies | **Mandatory** — per Executive Orders |
| US Critical Infrastructure | **Strongly recommended** |
| US Defense Contractors | **Mandatory via CMMC** (based on SP 800-171) |
| Private Sector (US) | **Voluntary** |
| International Organizations | **Voluntary** |

> [!WARNING]
> MCQ trap: NIST CSF is often described as voluntary but it is
> **mandatory for US federal agencies**. Both statements are true depending
> on context — know BOTH.

---

## 🔤 Abbreviations <a name="abbreviations"></a>

| Abbreviation | Full Form | One-line Meaning |
|---|---|---|
| **NIST** | National Institute of Standards and Technology | US federal agency that develops cybersecurity standards and frameworks |
| **CSF** | Cybersecurity Framework | NIST's risk-based framework for managing cybersecurity — 5/6 functions |
| **RMF** | Risk Management Framework | NIST's structured process for integrating security into system lifecycle |
| **SP** | Special Publication | NIST's numbered series of computer security guidelines |
| **IPDRR** | Identify, Protect, Detect, Respond, Recover | The 5 core functions of NIST CSF 1.1 |
| **CUI** | Controlled Unclassified Information | Sensitive but unclassified federal information |
| **CMMC** | Cybersecurity Maturity Model Certification | US DoD certification for defense contractors — based on SP 800-171 |
| **FIPS** | Federal Information Processing Standards | US government standards for federal computer systems |
| **SDLC** | System Development Lifecycle | Full lifecycle of a system from conception to decommission |
| **FedRAMP** | Federal Risk and Authorization Management Program | US program for cloud service authorization for federal use |
| **EO** | Executive Order | Presidential directive — EO 13636 triggered NIST CSF creation |
| **CIS** | Center for Internet Security | Organization that maps controls to NIST CSF (covered in Session 10) |

---

## 🗝️ Keywords & Concept Map <a name="keywords"></a>

**NIST CSF**
→ Risk-based cybersecurity framework — not prescriptive
→ Three components: Core (IPDRR), Tiers (1–4), Profiles (Current vs Target)
→ Created 2014, updated 2018 (v1.1), 2024 (v2.0 adds Govern)
→ Voluntary globally — mandatory for US federal agencies

**Framework Core**
→ 5 Functions: Identify → Protect → Detect → Respond → Recover
→ Each function has Categories and Subcategories
→ CSF 2.0 adds Govern as a 6th overarching function
→ Represents WHAT activities to perform

**Implementation Tiers**
→ 4 levels: Partial (1) → Risk Informed (2) → Repeatable (3) → Adaptive (4)
→ Describe HOW WELL risk management is integrated
→ NOT maturity levels — higher tier is not always the goal
→ Right tier depends on risk tolerance and business needs

**Framework Profile**
→ Current Profile = AS-IS cybersecurity state
→ Target Profile = TO-BE desired state
→ Gap between them = improvement roadmap
→ Helps communicate risk and prioritize investments

**NIST RMF**
→ 7 steps: Prepare → Categorize → Select → Implement → Assess → Authorize → Monitor
→ Defined in SP 800-37
→ Mandatory for US federal information systems
→ Uses SP 800-53 as control catalog (Step 3 — Select)

**SP 800-53**
→ Catalog of 20 security and privacy control families
→ Used in RMF Step 3 — Select controls
→ Three impact levels: Low, Moderate, High
→ Most comprehensive security control catalog in existence

---

## ⚡ Quick Reference Cheatsheet <a name="cheatsheet"></a>

### CSF 5 Functions — Complete Reference

| Function | Question It Answers | Key Activities |
|---|---|---|
| **Identify** | What do we have and what are the risks? | Asset inventory, risk assessment, governance |
| **Protect** | How do we prevent incidents? | Access control, training, data security, encryption |
| **Detect** | How do we know something is happening? | Monitoring, anomaly detection, detection processes |
| **Respond** | What do we do when hit? | Incident response, communications, mitigation |
| **Recover** | How do we get back to normal? | Recovery planning, improvements, communications |

### CSF Implementation Tiers

| Tier | Name | Key Characteristic |
|---|---|---|
| **1** | Partial | Ad hoc, reactive, no formal process |
| **2** | Risk Informed | Risk awareness exists, not org-wide |
| **3** | Repeatable | Formally approved, consistently applied |
| **4** | Adaptive | Proactive, continuously improving |

### NIST RMF — 7 Steps

| Step | Name | Key Output |
|---|---|---|
| 1 | Prepare | Risk management context established |
| 2 | Categorize | System impact level (Low/Mod/High) |
| 3 | Select | Baseline security controls chosen |
| 4 | Implement | Controls deployed in system |
| 5 | Assess | Controls verified as working |
| 6 | Authorize | ATO (Authority to Operate) issued |
| 7 | Monitor | Ongoing control effectiveness tracked |

### NIST CSF Versions

| Version | Year | Key Change |
|---|---|---|
| **CSF 1.0** | 2014 | Original — 5 functions |
| **CSF 1.1** | 2018 | Enhanced supply chain, authentication guidance |
| **CSF 2.0** | 2024 | Added GOVERN as 6th function |

### NIST vs ISO 27001 — Quick MCQ Reference

| | NIST CSF | ISO 27001 |
|---|---|---|
| Certification? | ❌ No | ✅ Yes |
| Cost? | Free | Paid |
| Mandatory? | US Federal only | Voluntary |
| Type | Framework | Standard |

### Three CSF Components

| Component | One-liner |
|---|---|
| **Core** | WHAT — 5 functions of cybersecurity activities |
| **Tiers** | HOW WELL — 4 levels of risk management sophistication |
| **Profiles** | WHERE — current vs target state gap |

---

## 🔁 Session Revision Snapshot <a name="snapshot"></a>

### TL;DR — 5 Bullets
- ✅ NIST = US federal agency under Dept of Commerce — develops voluntary
  cybersecurity standards (mandatory for US federal agencies)
- ✅ NIST CSF has 3 components: Core (IPDRR), Tiers (1–4), Profiles
  (Current vs Target)
- ✅ CSF Core = 5 Functions: Identify → Protect → Detect → Respond → Recover
  (CSF 2.0 adds Govern)
- ✅ Tiers are NOT maturity levels — right tier depends on risk tolerance
- ✅ NIST RMF = 7 steps (Prepare, Categorize, Select, Implement, Assess,
  Authorize, Monitor) — defined in SP 800-37

### 🎯 Top MCQ-Likely Concepts from This Session
1. **5 CSF Functions in order** — IPDRR and what each does
2. **3 CSF Components** — Core, Tiers, Profiles — most tested concept
3. **Tiers are NOT maturity levels** — classic trap question
4. **CSF 2.0 adds GOVERN** — very likely in recent exams
5. **SP 800-37 = RMF** and **SP 800-53 = Controls** — number-to-topic mapping
6. **NIST is voluntary** BUT mandatory for US federal agencies
7. **RMF 7 Steps** — especially Categorize (Step 2) and Select (Step 3)
8. **NIST vs ISO** — NIST has no certification, ISO does

---