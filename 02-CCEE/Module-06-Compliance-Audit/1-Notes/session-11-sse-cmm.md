# 🔐 Session 11 — SSE-CMM

## 📑 Table of Contents
- [What is SSE-CMM](#what-is-sse-cmm)
- [SSE-CMM Overview](#sse-cmm-overview)
- [History and the Need](#history)
- [SSE-CMM Architecture](#architecture)
  - [Process Areas](#process-areas)
  - [Two Dimensions](#two-dimensions)
- [SSE-CMM Domain — 11 Security PAs](#domain)
- [SSE-CMM Project PAs](#project-pas)
- [SSE-CMM Organization PAs](#org-pas)
- [Capability Levels](#capability-levels)
- [Using the SSE-CMM](#using-sse-cmm)
- [SSE-CMM Pilots](#pilots)
- [📌 Extra Notes](#extra-notes)
  - [SSE-CMM vs SW-CMM vs CMMI](#sse-vs-cmmi)
  - [ISO/IEC 21827 — SSE-CMM as Standard](#iso-21827)
  - [Systems Security Engineering — SSE](#sse)
  - [PA vs BP — Process Area vs Base Practice](#pa-vs-bp)
  - [Generic Practices — GPs](#generic-practices)
  - [SSE-CMM and Other Frameworks](#sse-others)
  - [Appraisal Methods — SSAM](#ssam)
  - [SSE-CMM Goals](#sse-cmm-goals)
- [Abbreviations](#abbreviations)
- [Keywords & Concept Map](#keywords)
- [Quick Reference Cheatsheet](#cheatsheet)
- [Session Revision Snapshot](#snapshot)

---

## 🔰 What is SSE-CMM <a name="what-is-sse-cmm"></a>

- **SSE-CMM = Systems Security Engineering Capability Maturity Model**
- A **framework for measuring and improving the capability** of
  organizations to perform **Systems Security Engineering (SSE)**
- Describes the **essential characteristics** of an organization's
  security engineering process
- Does NOT define HOW to do security engineering — defines WHAT
  processes a mature security engineering organization must perform
- Applicable to:
  - **Security engineering organizations** — companies building
    secure systems
  - **Security product developers** — vendors building security tools
  - **Service organizations** — security service providers
  - **Government agencies** — acquiring secure systems
  - **Evaluators** — assessing security of systems

> [!NOTE]
> SSE-CMM is **not a step-by-step security implementation guide** —
> it is a **measurement model** that tells organizations how capable
> and mature their security engineering processes are. Think of it
> as an audit framework for security engineering processes.

---

## 🏢 SSE-CMM Overview <a name="sse-cmm-overview"></a>

### Key Facts

| Attribute | Detail |
|---|---|
| **Full Name** | Systems Security Engineering Capability Maturity Model |
| **Purpose** | Measure and improve capability of security engineering processes |
| **Developed By** | International Systems Security Engineering Association (ISSEA) |
| **Based On** | SW-CMM (Software Capability Maturity Model) by SEI/Carnegie Mellon |
| **ISO Standard** | **ISO/IEC 21827** — SSE-CMM adopted as international standard |
| **Current Version** | Version 3.0 |
| **Applicability** | Security engineers, product developers, service providers, evaluators |
| **Process Areas** | 22 total (11 Security + 6 Project + 5 Organization) |
| **Capability Levels** | 5 levels (1–5) |

---

## 📜 History and the Need <a name="history"></a>

### The Problem SSE-CMM Solves

Before SSE-CMM:
- No common framework for **measuring security engineering capability**
- Organizations building secure systems had no standard way to
  demonstrate their process maturity
- Customers and government agencies had no objective way to **evaluate
  the capability** of security engineering organizations
- Security engineering was **ad hoc** — different organizations had
  vastly different processes with no way to compare them
- Process improvement in security engineering was difficult without
  a defined measurement model

### Development History

```
1993 → US National Security Agency (NSA) initiates research
        to define security engineering processes

1994 → SSE-CMM Project formally initiated
        Collaboration between US government and industry
        Based on SEI's Software CMM (SW-CMM)

1996 → SSE-CMM Version 1.1 published
        First public release
        11 security process areas defined

1999 → SSE-CMM Version 2.0 published
        Refined process areas
        Enhanced capability levels

2003 → SSE-CMM Version 3.0 published
        Current version
        Adopted as ISO/IEC 21827

2008 → ISO/IEC 21827:2008 published
        SSE-CMM formally becomes international standard
        Version 3.0 content adopted
```

> [!IMPORTANT]
> The **NSA (National Security Agency)** initiated the SSE-CMM
> project — it has roots in US government and defense needs. The
> framework was developed collaboratively with industry to create
> an objective measure of security engineering capability.

### Why SSE-CMM Was Needed

| Need | How SSE-CMM Addresses It |
|---|---|
| **Consistent security engineering** | Defines essential security engineering practices |
| **Process improvement** | Provides capability levels to measure and improve |
| **Customer confidence** | Allows buyers to evaluate supplier security engineering capability |
| **Objective evaluation** | Standard framework for independent assessment |
| **Common language** | Creates shared vocabulary for security engineering |
| **Government procurement** | Provides basis for security engineering requirements in contracts |

---

## 🏗️ SSE-CMM Architecture <a name="architecture"></a>

SSE-CMM has a **two-dimensional architecture**:

```
┌─────────────────────────────────────────────────────┐
│                                                     │
│   DOMAIN DIMENSION          CAPABILITY DIMENSION    │
│   (WHAT is done)            (HOW WELL it is done)   │
│                                                     │
│   Process Areas (PAs)       Capability Levels 1-5   │
│   → Base Practices (BPs)    → Generic Practices (GPs)│
│                                                     │
└─────────────────────────────────────────────────────┘
```

### Two Dimensions <a name="two-dimensions"></a>

| Dimension | Name | What It Covers |
|---|---|---|
| **Domain Dimension** | WHAT is done | Process Areas (PAs) and their Base Practices (BPs) — the specific activities of security engineering |
| **Capability Dimension** | HOW WELL it is done | Capability Levels (1–5) and Generic Practices (GPs) — how institutionalized and capable the processes are |

> [!IMPORTANT]
> The **two-dimensional structure** is fundamental to understanding
> SSE-CMM:
> - **Domain** = the specific security engineering activities
>   (WHAT the organization does)
> - **Capability** = how mature and capable those activities are
>   (HOW WELL the organization does them)

---

### 📋 Process Areas <a name="process-areas"></a>

- **Process Area (PA)** = a cluster of related security engineering
  practices that together achieve a specific goal
- Each PA contains **Base Practices (BPs)** — specific activities
  that must be performed
- SSE-CMM has **22 Process Areas total**:

| Category | Count | Prefix |
|---|---|---|
| **Security Process Areas** | 11 | PA01–PA11 |
| **Project Process Areas** | 6 | PA12–PA17 |
| **Organization Process Areas** | 5 | PA18–PA22 |
| **Total** | **22** | |

---

## 🔐 SSE-CMM Domain — 11 Security PAs <a name="domain"></a>

The **11 Security Process Areas** are the core of SSE-CMM — they
define what security engineering organizations must do:

| PA | Name | Description |
|---|---|---|
| **PA01** | Administer Security Controls | Manage and administer security mechanisms and controls |
| **PA02** | Assess Impact | Determine potential impact of threats and vulnerabilities |
| **PA03** | Assess Security Risk | Identify and assess risks to system security |
| **PA04** | Assess Threat | Identify and assess threats to system assets |
| **PA05** | Assess Vulnerability | Identify and assess vulnerabilities in systems |
| **PA06** | Build Assurance Argument | Develop evidence-based arguments that the system is secure |
| **PA07** | Coordinate Security | Coordinate security activities across the project |
| **PA08** | Monitor Security Posture | Monitor and manage the security posture of the system |
| **PA09** | Provide Security Input | Provide security guidance and input to the development process |
| **PA10** | Specify Security Needs | Define and document security requirements |
| **PA11** | Verify and Validate Security | Confirm that security requirements are met |

> [!TIP]
> **Memory trick for key Security PAs:**
> Think of the security engineering lifecycle:
> **Specify needs → Assess threats → Assess vulnerabilities →
> Assess risk → Assess impact → Build assurance → Provide input →
> Administer controls → Monitor posture → Coordinate → Verify**

---

## 📋 SSE-CMM Project PAs <a name="project-pas"></a>

The **6 Project Process Areas** support security engineering
within a project context:

| PA | Name | Description |
|---|---|---|
| **PA12** | Ensure Quality | Ensure the quality of security engineering products and services |
| **PA13** | Manage Configurations | Control and manage changes to system configurations |
| **PA14** | Manage Project Risk | Identify and manage project-level risks |
| **PA15** | Monitor and Control Technical Effort | Track and control technical work progress |
| **PA16** | Plan Technical Effort | Plan technical work activities |
| **PA17** | Define Project's Needs and Responsibilities | Define project scope, needs, and team responsibilities |

---

## 🏢 SSE-CMM Organization PAs <a name="org-pas"></a>

The **5 Organization Process Areas** support security engineering
at the organizational level:

| PA | Name | Description |
|---|---|---|
| **PA18** | Define Organization's Systems Engineering Process | Establish the standard security engineering process |
| **PA19** | Improve Organization's Systems Engineering Process | Continuously improve the engineering process |
| **PA20** | Manage Product Line Evolution | Manage and evolve the organization's product lines |
| **PA21** | Manage Systems Engineering Support Environment | Manage tools and infrastructure supporting engineering |
| **PA22** | Provide Ongoing Skills and Knowledge | Ensure staff have current security engineering skills |

> [!NOTE]
> The Project and Organization PAs are **NOT security-specific** —
> they are general engineering management practices that support
> the 11 security-specific PAs. However, in SSE-CMM, they are
> considered essential for mature security engineering organizations.

---

## 📊 Capability Levels <a name="capability-levels"></a>

SSE-CMM defines **5 Capability Levels** — measuring HOW WELL
an organization's security engineering processes are performed:

| Level | Name | Description | Key Characteristic |
|---|---|---|---|
| **Level 1** | Performed Informally | Base Practices are performed but may be incomplete or inconsistent | Individual heroics — depends on people, not process |
| **Level 2** | Planned and Tracked | Practices are planned, performed, tracked, and verified — project level | Project-level discipline applied |
| **Level 3** | Well Defined | Practices are defined, documented, and use a standard process — organization level | Organizational standard process used |
| **Level 4** | Quantitatively Controlled | Quantitative measures are collected and used to control processes | Data-driven management |
| **Level 5** | Continuously Improving | Process continuously improved using quantitative data | Continuous improvement culture |

> [!IMPORTANT]
> **There is NO Level 0** in SSE-CMM capability levels — unlike
> COBIT's maturity model which starts at 0. SSE-CMM levels run
> from **1 to 5**. Level 1 does not mean no process — it means
> the base practices ARE performed but informally.

### Capability Level Detail

#### Level 1 — Performed Informally
- Base Practices ARE performed (this is what distinguishes it
  from "not performing" security engineering)
- Processes are **reactive and ad hoc**
- Results depend on **individual skill and heroics**
- Not planned, tracked, or consistently applied
- The starting point — even informal performance counts as Level 1

#### Level 2 — Planned and Tracked
- Practices are **planned** before execution
- Progress is **tracked** against plans
- Results are **verified** for correctness
- Applied at the **project level** — may vary between projects
- Configuration management and requirements management established

#### Level 3 — Well Defined
- A **standard organizational process** is defined and documented
- All projects use the standard process (with allowed tailoring)
- Processes are described in sufficient detail
- Coordination across projects is enabled
- This is the level most organizations target as a meaningful goal

#### Level 4 — Quantitatively Controlled
- **Quantitative measures** collected from processes
- Process performance is **statistically managed**
- Variation in processes is understood and controlled
- Predictions about process performance can be made
- Requires sophisticated measurement infrastructure

#### Level 5 — Continuously Improving
- Organization uses quantitative data to **continuously improve**
  its security engineering processes
- New technologies and methods are proactively identified and
  evaluated
- Defect causes are identified and eliminated systematically
- Process improvement is an organizational discipline

---

## 🔧 Using the SSE-CMM <a name="using-sse-cmm"></a>

SSE-CMM can be used in multiple ways by different stakeholders:

### By Security Engineering Organizations
- **Self-assessment** — evaluate current security engineering
  capability level
- **Process improvement** — identify gaps and plan improvements
- **Demonstration** — show customers the maturity of their
  security engineering processes

### By Customers / Acquirers
- **Supplier evaluation** — assess the security engineering
  capability of potential suppliers
- **Contract requirements** — specify minimum SSE-CMM capability
  levels in contracts
- **Risk reduction** — select suppliers with proven security
  engineering maturity

### By Evaluators / Assessors
- **Independent appraisal** — conduct formal appraisals of
  organizations using the SSAM (SSE-CMM Appraisal Method)
- **Certification support** — provide evidence for ISO/IEC 21827
  compliance

### By Government Agencies
- **Procurement** — require certain SSE-CMM capability levels
  from defense and security contractors
- **Policy** — incorporate SSE-CMM into security policy requirements
- **Research** — advance the state of security engineering practice

### SSE-CMM Use Cases Summary

| Stakeholder | Primary Use |
|---|---|
| **Security Engineering Org** | Self-assess and improve processes |
| **Customer/Acquirer** | Evaluate supplier capability |
| **Evaluator** | Conduct formal appraisals |
| **Government** | Procurement requirements |
| **Researcher** | Advance security engineering science |

---

## 🧪 SSE-CMM Pilots <a name="pilots"></a>

### What Were the SSE-CMM Pilots?

- **Pilots** = real-world organizations that tested and validated
  the SSE-CMM framework before and during its development
- Essential for validating that the model accurately describes
  security engineering in practice
- Pilots helped refine process areas, base practices, and capability
  levels based on actual organizational experience

### Types of Pilots

| Pilot Type | Purpose |
|---|---|
| **Development Pilots** | Organizations developing secure systems — test security PAs |
| **Evaluation Pilots** | Organizations evaluating systems — test evaluation-related PAs |
| **Acquisition Pilots** | Government agencies acquiring secure systems — test procurement use |
| **Service Provider Pilots** | Security service providers — test service-oriented PAs |

### Pilot Outcomes
- Validated that the 11 security PAs accurately capture
  security engineering activities
- Refined the capability level definitions based on actual
  organizational maturity
- Demonstrated that SSE-CMM could be applied across different
  types of organizations and sectors
- Led to revisions in Version 2.0 and Version 3.0

> [!NOTE]
> The pilots were critical to SSE-CMM's credibility — they proved
> the model worked in practice across diverse organizations before
> it was adopted as ISO/IEC 21827. This empirical validation is
> what distinguishes SSE-CMM from purely theoretical frameworks.

---

## 📌 Extra Notes <a name="extra-notes"></a>

> [!NOTE]
> Everything in this section goes beyond the core syllabus but is
> directly MCQ-relevant. Cross-referenced from ISSEA SSE-CMM
> documentation, ISO/IEC 21827, and systems security engineering
> literature. Zero internet needed after reading this.

---

### 📊 SSE-CMM vs SW-CMM vs CMMI <a name="sse-vs-cmmi"></a>

SSE-CMM is based on the **SW-CMM** and related to **CMMI**:

| Feature | SW-CMM | SSE-CMM | CMMI |
|---|---|---|---|
| **Full Name** | Software Capability Maturity Model | Systems Security Engineering CMM | Capability Maturity Model Integration |
| **Developed By** | SEI / Carnegie Mellon | ISSEA (NSA initiated) | SEI / Carnegie Mellon |
| **Focus** | Software development process | Security engineering process | Multiple disciplines (SW, SE, services) |
| **Levels** | 5 (1–5) | 5 (1–5) | 5 (1–5) |
| **Adopted As** | Not an ISO standard | ISO/IEC 21827 | Not an ISO standard (CMMI Institute) |
| **Status** | Superseded by CMMI | Current — ISO/IEC 21827 | Current |
| **Domain** | Software processes | Security engineering processes | Multiple process disciplines |

> [!IMPORTANT]
> **SSE-CMM is directly based on SW-CMM** — it adopted the same
> capability level structure (5 levels) and the concept of Process
> Areas. The key difference is the **domain**: SW-CMM covers
> software processes, SSE-CMM covers security engineering processes.
> CMMI later integrated and superseded SW-CMM.

---

### 🌐 ISO/IEC 21827 — SSE-CMM as Standard <a name="iso-21827"></a>

- **ISO/IEC 21827** = the international standard based on SSE-CMM
- Published: **ISO/IEC 21827:2002** (first edition)
- Updated: **ISO/IEC 21827:2008** (second edition — current)
- Content is essentially SSE-CMM Version 3.0
- Formal title: **"Information Technology — Systems Security Engineering —
  Capability Maturity Model (SSE-CMM)"**

### Significance of ISO/IEC 21827
- Makes SSE-CMM an **internationally recognized standard**
- Organizations can claim ISO/IEC 21827 compliance
- Used in government procurement globally
- Provides framework for security engineering appraisals
- Referenced by other security standards and frameworks

> [!TIP]
> When MCQs ask about the ISO standard for security engineering
> capability maturity — the answer is **ISO/IEC 21827**. This
> is distinct from:
> - ISO/IEC 27001 (ISMS)
> - ISO/IEC 15408 (Common Criteria)
> - ISO/IEC 18045 (CEM)

---

### 🔧 Systems Security Engineering — SSE <a name="sse"></a>

SSE-CMM is about **Systems Security Engineering** — what is it?

- **SSE = Systems Security Engineering**
- A disciplined approach to designing, building, and operating
  **trustworthy, dependable, and secure systems**
- Part of the broader **Systems Engineering** discipline
- SSE activities are integrated throughout the **system lifecycle**:

```
Concept → Development → Production → Utilization → Support → Retirement
   ↑___________↑____________↑___________↑____________↑__________↑
   SSE activities span the entire system lifecycle
```

### Core SSE Activities
- **Risk** — identify and manage security risks
- **Engineering** — design and build security into systems
- **Assurance** — provide evidence that security requirements are met

> [!NOTE]
> SSE is NOT just about implementing security controls after a
> system is built. It is about **integrating security engineering
> throughout the entire system lifecycle** — from concept to
> retirement. This "security by design" philosophy is fundamental
> to SSE and SSE-CMM.

---

### 📋 PA vs BP — Process Area vs Base Practice <a name="pa-vs-bp"></a>

These two terms are frequently confused:

| Term | Definition | Level |
|---|---|---|
| **PA (Process Area)** | A cluster of related practices achieving a specific goal — there are 22 PAs | Higher-level grouping |
| **BP (Base Practice)** | A specific activity within a PA that must be performed — there are many BPs per PA | Specific activity |

### Example — PA03 Assess Security Risk

```
PA03 — Assess Security Risk (Process Area)
│
├── BP.03.01 — Identify security risks
├── BP.03.02 — Analyze security risks
├── BP.03.03 — Evaluate security risks
└── BP.03.04 — Monitor changes to security risks
```

> [!TIP]
> Think of PAs as **chapters** in a book and BPs as **sections**
> within those chapters. You assess an organization's capability
> at the PA level, but you look at specific BPs to determine
> if the PA is being performed.

---

### ⚙️ Generic Practices — GPs <a name="generic-practices"></a>

- **Generic Practices (GPs)** = practices associated with the
  **Capability Dimension** — they apply to ALL Process Areas
- GPs define HOW WELL processes are performed — not what is done
- Each Capability Level has associated GPs that must be satisfied
- GPs address: planning, tracking, verifying, defining, measuring,
  and improving processes

### GP Examples by Capability Level

| Level | Example Generic Practices |
|---|---|
| **Level 1** | Perform Base Practices (just do the activity) |
| **Level 2** | Plan performance / Track performance / Verify performance / Manage configuration of work products |
| **Level 3** | Define standard process / Use well-defined process / Coordinate practices |
| **Level 4** | Establish measurable quality goals / Quantitatively manage process performance |
| **Level 5** | Improve organizational capability / Improve process effectiveness |

> [!NOTE]
> The relationship between PAs and GPs is what creates the
> **two-dimensional matrix** of SSE-CMM:
> - Each row = a Process Area (PA)
> - Each column = a Capability Level
> - Each cell = Generic Practices applied to a PA at that level

---

### 🔗 SSE-CMM and Other Frameworks <a name="sse-others"></a>

| Framework | Relationship to SSE-CMM |
|---|---|
| **Common Criteria (ISO/IEC 15408)** | CC evaluates PRODUCTS — SSE-CMM evaluates ORGANIZATIONS/PROCESSES — complementary |
| **ISO/IEC 27001** | 27001 specifies ISMS requirements — SSE-CMM measures security engineering process capability |
| **NIST SP 800-160** | Both address systems security engineering — NIST 800-160 provides engineering guidance |
| **CMMI** | SSE-CMM follows the same CMM structure — CMMI covers broader engineering disciplines |
| **CIS Controls** | CIS = what controls to implement — SSE-CMM = how capable is the security engineering process |

> [!IMPORTANT]
> **CC vs SSE-CMM — critical distinction:**
> - **Common Criteria** evaluates the **security of a PRODUCT**
>   (the TOE — what the product does)
> - **SSE-CMM** evaluates the **capability of an ORGANIZATION's
>   PROCESSES** (how the organization builds secure products)
> These are complementary — a product can be CC-evaluated AND
> the organization that built it can be SSE-CMM appraised.

---

### 🔍 Appraisal Methods — SSAM <a name="ssam"></a>

- **SSAM = SSE-CMM Appraisal Method**
- The formal method for assessing an organization's SSE-CMM
  capability level
- Produces an **appraisal rating** for each Process Area
- Conducted by **trained SSE-CMM appraisers**

### SSAM Process

```
Step 1 → Plan the appraisal
          Define scope, select PAs to assess, form appraisal team

Step 2 → Prepare for appraisal
          Collect evidence — documentation, artifacts

Step 3 → Conduct appraisal
          Interviews, document reviews, process observations

Step 4 → Analyze findings
          Map evidence to Base Practices and Generic Practices

Step 5 → Report results
          Capability levels determined for each assessed PA
          Findings and recommendations documented
```

### SSAM Output
- **Capability Level rating** for each assessed Process Area
- Findings — strengths and weaknesses in security engineering processes
- Recommendations for improvement

> [!NOTE]
> SSAM is to SSE-CMM what a **SCAMPI appraisal** is to CMMI.
> Both are formal appraisal methods that validate an organization's
> claimed capability level. Without a formal appraisal, an
> organization can self-assess but cannot formally claim a
> capability level.

---

### 🎯 SSE-CMM Goals <a name="sse-cmm-goals"></a>

The overarching goals of SSE-CMM:

| Goal | Description |
|---|---|
| **Establish a standard** | Create a common framework for security engineering process definition |
| **Enable process improvement** | Give organizations a roadmap for improving security engineering |
| **Support evaluation** | Provide basis for evaluating security engineering organizations |
| **Advance the discipline** | Mature the field of systems security engineering as a profession |
| **Enable trust** | Allow customers to trust that security engineering organizations have capable processes |
| **Government procurement** | Support US and international government security procurement decisions |

---

## 🔤 Abbreviations <a name="abbreviations"></a>

| Abbreviation | Full Form | One-line Meaning |
|---|---|---|
| **SSE-CMM** | Systems Security Engineering Capability Maturity Model | Framework for measuring and improving security engineering process capability |
| **SSE** | Systems Security Engineering | Disciplined approach to building secure systems throughout the lifecycle |
| **CMM** | Capability Maturity Model | Framework measuring process maturity — 5 capability levels |
| **ISSEA** | International Systems Security Engineering Association | Organization maintaining SSE-CMM |
| **SEI** | Software Engineering Institute | Carnegie Mellon institute that developed SW-CMM — basis for SSE-CMM |
| **SW-CMM** | Software Capability Maturity Model | Predecessor CMM focused on software development — basis for SSE-CMM |
| **CMMI** | Capability Maturity Model Integration | Evolved CMM covering multiple disciplines — succeeded SW-CMM |
| **PA** | Process Area | Cluster of related security engineering practices |
| **BP** | Base Practice | Specific activity within a Process Area |
| **GP** | Generic Practice | Practice applied to all PAs — measures HOW WELL |
| **SSAM** | SSE-CMM Appraisal Method | Formal method for assessing SSE-CMM capability levels |
| **NSA** | National Security Agency | US agency that initiated SSE-CMM development |
| **ISO/IEC 21827** | — | International standard based on SSE-CMM |
| **TOE** | Target of Evaluation | Common Criteria term — system being evaluated (not SSE-CMM specific) |
| **SCAMPI** | Standard CMMI Appraisal Method for Process Improvement | CMMI's formal appraisal method — analogous to SSAM |
| **SDLC** | System Development Life Cycle | Full lifecycle of a system — SSE spans the entire SDLC |

---

## 🗝️ Keywords & Concept Map <a name="keywords"></a>

**SSE-CMM**
→ Measures and improves security engineering process capability
→ Developed by ISSEA — initiated by NSA
→ Based on SW-CMM from SEI/Carnegie Mellon
→ Adopted as ISO/IEC 21827
→ 22 PAs: 11 Security + 6 Project + 5 Organization
→ 5 Capability Levels (1–5)

**Two-Dimensional Architecture**
→ Domain Dimension = WHAT is done (PAs + BPs)
→ Capability Dimension = HOW WELL it is done (Levels + GPs)
→ Every PA assessed at every Capability Level
→ Creates a matrix of security engineering capability

**22 Process Areas**
→ 11 Security PAs (PA01–PA11) — core security engineering
→ 6 Project PAs (PA12–PA17) — project management support
→ 5 Organization PAs (PA18–PA22) — organizational support
→ Each PA has multiple Base Practices (BPs)

**5 Capability Levels**
→ Level 1 = Performed Informally (ad hoc)
→ Level 2 = Planned and Tracked (project level)
→ Level 3 = Well Defined (organizational standard)
→ Level 4 = Quantitatively Controlled (data-driven)
→ Level 5 = Continuously Improving (optimization)
→ Starts at 1 (NOT 0) — informal performance still counts

**SSE-CMM vs Common Criteria**
→ CC evaluates PRODUCTS (security features of the system)
→ SSE-CMM evaluates ORGANIZATIONS (security engineering capability)
→ Complementary — a CC-evaluated product may come from an
  SSE-CMM-appraised organization

**ISO/IEC 21827**
→ SSE-CMM adopted as international standard
→ Published 2002 (first), 2008 (current)
→ Provides international recognition of SSE-CMM

---

## ⚡ Quick Reference Cheatsheet <a name="cheatsheet"></a>

### SSE-CMM Key Numbers

| Metric | Value |
|---|---|
| Total Process Areas | **22** |
| Security Process Areas | **11** (PA01–PA11) |
| Project Process Areas | **6** (PA12–PA17) |
| Organization Process Areas | **5** (PA18–PA22) |
| Capability Levels | **5** (Level 1–5) |
| Current Version | **3.0** |
| ISO Standard | **ISO/IEC 21827:2008** |

### 11 Security Process Areas

| PA | Name |
|---|---|
| PA01 | Administer Security Controls |
| PA02 | Assess Impact |
| PA03 | Assess Security Risk |
| PA04 | Assess Threat |
| PA05 | Assess Vulnerability |
| PA06 | Build Assurance Argument |
| PA07 | Coordinate Security |
| PA08 | Monitor Security Posture |
| PA09 | Provide Security Input |
| PA10 | Specify Security Needs |
| PA11 | Verify and Validate Security |

### 5 Capability Levels

| Level | Name | Key Characteristic |
|---|---|---|
| **1** | Performed Informally | Ad hoc — individual dependent |
| **2** | Planned and Tracked | Project-level discipline |
| **3** | Well Defined | Organizational standard process |
| **4** | Quantitatively Controlled | Data-driven management |
| **5** | Continuously Improving | Optimization culture |

### Two Dimensions

| Dimension | Covers | Components |
|---|---|---|
| **Domain** | WHAT is done | Process Areas (PAs) + Base Practices (BPs) |
| **Capability** | HOW WELL it is done | Levels (1–5) + Generic Practices (GPs) |

### SSE-CMM vs CMM Family

| Model | Focus | Levels | ISO |
|---|---|---|---|
| **SW-CMM** | Software development | 1–5 | No |
| **SSE-CMM** | Security engineering | 1–5 | ISO/IEC 21827 |
| **CMMI** | Multiple disciplines | 1–5 | No |

### SSE-CMM vs Common Criteria

| | Common Criteria | SSE-CMM |
|---|---|---|
| **Evaluates** | Products (TOE) | Organizations (processes) |
| **Output** | EAL rating | Capability Level per PA |
| **ISO Standard** | ISO/IEC 15408 | ISO/IEC 21827 |
| **Relationship** | What the product does | How capable is the builder |

### Capability Levels — No Level 0

```
Level 5 — Continuously Improving
Level 4 — Quantitatively Controlled
Level 3 — Well Defined
Level 2 — Planned and Tracked
Level 1 — Performed Informally
          ↑ (Starting point — NOT Level 0)
```

### Who Uses SSE-CMM

| Stakeholder | Primary Use |
|---|---|
| Security Eng Org | Self-assess and improve |
| Customer/Acquirer | Evaluate supplier capability |
| Evaluator | Formal SSAM appraisals |
| Government | Procurement requirements |

### SSE-CMM History Timeline

| Year | Event |
|---|---|
| 1993 | NSA initiates SSE-CMM research |
| 1994 | SSE-CMM project formally started |
| 1996 | Version 1.1 published |
| 1999 | Version 2.0 published |
| 2003 | Version 3.0 published (current) |
| 2008 | ISO/IEC 21827:2008 published |

---

## 🔁 Session Revision Snapshot <a name="snapshot"></a>

### TL;DR — 5 Bullets
- ✅ SSE-CMM = Systems Security Engineering Capability Maturity Model
  — measures and improves security engineering process capability —
  developed by ISSEA — initiated by NSA — based on SW-CMM
- ✅ Two dimensions: **Domain** (WHAT — 22 PAs + BPs) and
  **Capability** (HOW WELL — 5 levels + GPs) — creates a
  matrix of security engineering maturity
- ✅ 22 Process Areas: **11 Security** (PA01–PA11) + 6 Project +
  5 Organization — each PA has Base Practices (BPs)
- ✅ 5 Capability Levels: **1 (Performed Informally) → 2 (Planned
  and Tracked) → 3 (Well Defined) → 4 (Quantitatively Controlled)
  → 5 (Continuously Improving)** — starts at 1 NOT 0
- ✅ SSE-CMM adopted as **ISO/IEC 21827** — evaluates ORGANIZATIONS
  (process capability) vs Common Criteria which evaluates PRODUCTS
  (security features)

### 🎯 Top MCQ-Likely Concepts from This Session
1. **SSE-CMM full name** — Systems Security Engineering CMM
2. **22 total PAs** — 11 Security + 6 Project + 5 Organization
3. **11 Security PAs** — know all names (PA01–PA11)
4. **5 Capability Levels** — names and characteristics — starts at 1
5. **Two dimensions** — Domain (WHAT) vs Capability (HOW WELL)
6. **ISO/IEC 21827** — SSE-CMM adopted as ISO standard
7. **NSA initiated** SSE-CMM — based on SW-CMM (SEI/Carnegie Mellon)
8. **SSE-CMM vs Common Criteria** — organizations vs products
9. **Level 1 = Performed Informally** — NOT Level 0 — very common trap
10. **PA vs BP vs GP** — Process Area vs Base Practice vs Generic Practice
11. **SSAM** — the appraisal method for SSE-CMM
12. **Pilots** — validated the model before ISO adoption

---