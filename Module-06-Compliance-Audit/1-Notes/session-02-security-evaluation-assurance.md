# 🔐 Session 02 — Security Evaluation & Assurance

## 📑 Table of Contents
- [What is Security Evaluation](#what-is-security-evaluation)
- [Why Security Evaluation Matters](#why-it-matters)
- [Security Evaluation Frameworks — Overview](#frameworks-overview)
- [TCSEC — Orange Book](#tcsec)
- [ITSEC](#itsec)
- [Common Criteria (CC)](#common-criteria)
- [Key CC Terminology](#cc-terminology)
- [Evaluation Process](#evaluation-process)
- [Evaluation Phases](#evaluation-phases)
- [Assurance — 7 Evaluation Levels (EAL)](#eal)
- [Evaluation Methodology — CEM](#cem)
- [📌 Extra Notes](#extra-notes)
  - [Protection Profile vs Security Target](#pp-vs-st)
  - [SFR vs SAR](#sfr-vs-sar)
  - [CC Participants](#cc-participants)
  - [TCSEC vs ITSEC vs CC Comparison](#comparison)
  - [Mutual Recognition Arrangements](#mra)
- [Abbreviations](#abbreviations)
- [Keywords & Concept Map](#keywords)
- [Quick Reference Cheatsheet](#cheatsheet)
- [Session Revision Snapshot](#snapshot)

---

## 🔰 What is Security Evaluation <a name="what-is-security-evaluation"></a>

- **Security Evaluation** = A formal, structured process of assessing whether
  an IT product, system, or component meets its defined security requirements
- It is performed by an **independent, accredited evaluation body** — not the
  developer or vendor
- The subject being evaluated is called the **TOE (Target of Evaluation)**
- The outcome is a **certificate or assurance rating** that tells buyers and
  organizations how trustworthy a product is
- Think of it as: *"Can we trust this product to do what it claims to do
  securely?"*

> [!NOTE]
> Security Evaluation is **not** the same as a security audit. Audit checks
> organizational compliance. Evaluation checks whether a **product or system**
> meets defined security properties at a technical level.

---

## ❓ Why Security Evaluation Matters <a name="why-it-matters"></a>

| Reason | Explanation |
|---|---|
| **Buyer Confidence** | Organizations can trust evaluated products |
| **Vendor Accountability** | Developers must prove security claims |
| **Standardization** | Common baseline for comparing products |
| **Government Procurement** | Many govts mandate evaluated products |
| **Risk Reduction** | Reduces risk of deploying insecure products |
| **International Recognition** | Evaluated products accepted across countries |

---

## 🗂️ Security Evaluation Frameworks — Overview <a name="frameworks-overview"></a>

Three major frameworks have shaped security evaluation globally:

| Framework | Full Name | Origin | Status |
|---|---|---|---|
| **TCSEC** | Trusted Computer System Evaluation Criteria | USA — DoD | Superseded |
| **ITSEC** | Information Technology Security Evaluation Criteria | Europe | Superseded |
| **CC** | Common Criteria | International — ISO/IEC 15408 | Current Standard |

> [!IMPORTANT]
> **Common Criteria (CC)** is the current international standard — ISO/IEC
> 15408. TCSEC and ITSEC are older frameworks but their concepts still appear
> in MCQs because CC evolved from them.

---

## 📘 TCSEC — Orange Book <a name="tcsec"></a>

- **TCSEC = Trusted Computer System Evaluation Criteria**
- Published by the **US Department of Defense (DoD)**
- Also called the **"Orange Book"** — literally named after its orange cover
- Part of the **Rainbow Series** of security standards
- Focused primarily on **confidentiality** of government/military systems
- Now **superseded by Common Criteria**

### TCSEC Divisions & Classes

| Division | Class | Name | Description |
|---|---|---|---|
| **D** | D | Minimal Protection | No security — fails all higher requirements |
| **C** | C1 | Discretionary Security Protection | Basic access control by users |
| **C** | C2 | Controlled Access Protection | Stricter access control, audit trails |
| **B** | B1 | Labeled Security Protection | Security labels on data |
| **B** | B2 | Structured Protection | Formal security model applied |
| **B** | B3 | Security Domains | High resistance to penetration |
| **A** | A1 | Verified Design | Formal mathematical verification |

> [!TIP]
> **Memory trick for TCSEC:** D → C1 → C2 → B1 → B2 → B3 → A1
> (Low to High security — D is worst, A1 is best)

---

## 📗 ITSEC <a name="itsec"></a>

- **ITSEC = Information Technology Security Evaluation Criteria**
- Developed jointly by **France, Germany, Netherlands, and the UK**
- European counterpart to TCSEC
- Introduced **Assurance Levels E0–E6** (7 levels — E0 being lowest)
- Broader than TCSEC — covers **confidentiality, integrity, AND availability**
- Also now **superseded by Common Criteria**

### ITSEC Assurance Levels

| Level | Description |
|---|---|
| **E0** | Inadequate assurance |
| **E1** | Informal security target description |
| **E2** | Informal description of design |
| **E3** | Source code or hardware drawings evaluated |
| **E4** | Formal security model |
| **E5** | Close correspondence between design and source code |
| **E6** | Formal specification of design and source code |

> [!NOTE]
> ITSEC's E0–E6 directly influenced Common Criteria's EAL1–EAL7 levels.
> The concept is the same — just named differently.

---

## 📙 Common Criteria (CC) <a name="common-criteria"></a>

- **Common Criteria = CC = ISO/IEC 15408**
- The **current international standard** for IT security evaluation
- Replaced both TCSEC and ITSEC
- Allows IT products to be evaluated **once** and recognized in **multiple
  countries** through mutual recognition agreements
- Covers three aspects:
  - **Confidentiality**
  - **Integrity**
  - **Availability**
- CC defines a structured way to specify, implement, and evaluate security
  requirements

### CC Structure

```
Common Criteria (ISO/IEC 15408)
│
├── Part 1 → Introduction and General Model
├── Part 2 → Security Functional Requirements (SFR)
└── Part 3 → Security Assurance Requirements (SAR)
```

---

## 🔑 Key CC Terminology <a name="cc-terminology"></a>

| Term | Full Form | Meaning |
|---|---|---|
| **TOE** | Target of Evaluation | The IT product or system being evaluated |
| **ST** | Security Target | Document describing the security claims for a specific TOE |
| **PP** | Protection Profile | Generic security requirements for a category of products |
| **TSF** | TOE Security Functions | Security functions implemented by the TOE |
| **SFR** | Security Functional Requirements | What the product must do (security features) |
| **SAR** | Security Assurance Requirements | How confident we are the product does it correctly |
| **EAL** | Evaluation Assurance Level | The rating (1–7) indicating depth of evaluation |
| **CEM** | Common Evaluation Methodology | How evaluators perform the evaluation |
| **CCTL** | Common Criteria Testing Laboratory | Accredited lab that performs evaluations |

---

## 🔄 Evaluation Process <a name="evaluation-process"></a>

The CC evaluation process involves four main participants:

```
Developer/Vendor
      ↓
  Submits TOE + ST to
      ↓
Evaluation Lab (CCTL)
      ↓
  Sends findings to
      ↓
Certification Body
      ↓
  Overseen by
      ↓
National Scheme
```

### Step-by-Step Process

| Step | Who | What Happens |
|---|---|---|
| **1. Preparation** | Developer | Prepares TOE, Security Target (ST), and supporting evidence |
| **2. Submission** | Developer | Submits TOE and documentation to accredited CCTL |
| **3. Evaluation** | CCTL (Lab) | Independently evaluates TOE against claimed EAL |
| **4. Technical Report** | CCTL | Produces Evaluation Technical Report (ETR) |
| **5. Certification** | Certification Body | Reviews ETR and issues certificate if evaluation passes |
| **6. Publication** | National Scheme | Publishes certified product in Common Criteria Portal |
| **7. Post-Certification** | Developer | Maintains certificate — must re-evaluate after significant changes |

> [!WARNING]
> The **CCTL is independent** of both the developer and the certification body.
> This independence is what makes the evaluation trustworthy. If the developer
> evaluated their own product, it would be meaningless.

---

## 📊 Evaluation Phases <a name="evaluation-phases"></a>

Within the evaluation itself (what happens inside the CCTL):

| Phase | Activities |
|---|---|
| **1. Initiation** | Define scope, agree on TOE, select EAL target, establish evaluation plan |
| **2. Document Review** | Review Security Target, design documents, user guides, admin guides |
| **3. Development Analysis** | Analyze architecture, design, implementation against requirements |
| **4. Testing** | Independent testing — functional tests, penetration tests, vulnerability analysis |
| **5. Assessment** | Compile findings, determine pass/fail against each assurance component |
| **6. Reporting** | Produce Evaluation Technical Report (ETR) |

---

## 🏆 Assurance — 7 Evaluation Levels (EAL) <a name="eal"></a>

**EAL = Evaluation Assurance Level**
- Ranges from **EAL1 (lowest)** to **EAL7 (highest)**
- Higher EAL = More rigorous evaluation = More assurance
- Higher EAL does NOT automatically mean more features — it means the
  **same features are evaluated more deeply and rigorously**

| Level | Name | Description | Typical Use |
|---|---|---|---|
| **EAL1** | Functionally Tested | Basic functional testing only | Low-risk commercial products |
| **EAL2** | Structurally Tested | Developer testing + independent testing | Simple security applications |
| **EAL3** | Methodically Tested and Checked | More rigorous testing + some design review | Moderate-risk environments |
| **EAL4** | Methodically Designed, Tested and Reviewed | Full design review + independent testing | **Most common commercial level** |
| **EAL5** | Semiformally Designed and Tested | Semiformal design + rigorous testing | High-security environments |
| **EAL6** | Semiformally Verified Design and Tested | Semiformal verification + extensive testing | High-risk/government systems |
| **EAL7** | Formally Verified Design and Tested | Formal mathematical verification | Extreme security — military/classified |

> [!IMPORTANT]
> **EAL4 is the most common commercial EAL level.** It is the highest level
> achievable without fundamentally redesigning the product for evaluation.
> Most enterprise security products aim for EAL4.

> [!TIP]
> **Memory trick for EAL names:**
> ```
> EAL1 → Functionally Tested         (F)
> EAL2 → Structurally Tested         (S)
> EAL3 → Methodically Tested/Checked (M)
> EAL4 → Methodically Designed       (M)
> EAL5 → Semiformally Designed       (S)
> EAL6 → Semiformally Verified       (S)
> EAL7 → Formally Verified           (F)
> ```
> **F-S-M-M-S-S-F** — think of it as a pattern

---

## 📐 Evaluation Methodology — CEM <a name="cem"></a>

- **CEM = Common Evaluation Methodology**
- Standard: **ISO/IEC 18045**
- Defines **how** evaluators must conduct a CC evaluation
- Ensures consistency and repeatability across different evaluation labs
  worldwide
- Without CEM, two labs could evaluate the same product completely differently
  and reach different conclusions

### What CEM Defines
- Evaluation activities for each assurance component
- Work units — specific tasks evaluators must perform
- Verdict criteria — pass/fail conditions for each work unit
- Documentation requirements for evaluation evidence

> [!NOTE]
> **CC = ISO/IEC 15408** defines the **what** (requirements)
> **CEM = ISO/IEC 18045** defines the **how** (methodology)
> They work together — CC without CEM would be inconsistent globally.

---

## 📌 Extra Notes <a name="extra-notes"></a>

> [!NOTE]
> The concepts below go beyond the basic syllabus but are directly
> relevant for MCQs and deeper understanding. Worth knowing cold.

---

### 📄 Protection Profile vs Security Target <a name="pp-vs-st"></a>

These two are frequently confused in MCQs:

| | Protection Profile (PP) | Security Target (ST) |
|---|---|---|
| **Created by** | Community / Industry group | Developer / Vendor |
| **Scope** | Generic — for a category of products | Specific — for one particular TOE |
| **Purpose** | Template of requirements for a product type | Claims made for a specific product |
| **Example** | PP for Firewalls in general | ST for Cisco ASA Firewall v9.x |
| **TOE specific?** | ❌ No — generic | ✅ Yes — specific product |

> [!TIP]
> Think of PP as a **job description** (what any firewall should do) and ST
> as a **resume** (what this specific firewall claims to do).

---

### ⚙️ SFR vs SAR <a name="sfr-vs-sar"></a>

| | SFR | SAR |
|---|---|---|
| **Full Form** | Security Functional Requirements | Security Assurance Requirements |
| **Question it answers** | What does the product DO? | How confident are we it does it RIGHT? |
| **Focus** | Features and functions | Evaluation rigor and depth |
| **Example** | "Product must encrypt data at rest" | "Design must be formally verified" |
| **CC Part** | Part 2 | Part 3 |

---

### 👥 CC Participants <a name="cc-participants"></a>

| Participant | Role |
|---|---|
| **Developer/Vendor** | Creates the TOE and prepares documentation |
| **Evaluator (CCTL)** | Independently evaluates TOE at accredited lab |
| **Certification Body** | Reviews evaluation results and issues certificate |
| **National Scheme** | Oversees the entire process in a country |
| **Consumer/Buyer** | Uses certified products — trusts the certificate |

---

### 📊 TCSEC vs ITSEC vs CC Comparison <a name="comparison"></a>

| Feature | TCSEC | ITSEC | CC |
|---|---|---|---|
| **Origin** | USA (DoD) | Europe | International |
| **Standard** | DoD 5200.28-STD | ITSEC v1.2 | ISO/IEC 15408 |
| **Also Known As** | Orange Book | — | Common Criteria |
| **Rating Scale** | D, C1, C2, B1, B2, B3, A1 | E0–E6 | EAL1–EAL7 |
| **Security Focus** | Confidentiality only | CIA (all three) | CIA (all three) |
| **Status** | Superseded | Superseded | Current |
| **Recognition** | USA only | Europe only | International |

---

### 🌐 Mutual Recognition Arrangements <a name="mra"></a>

- **CCRA = Common Criteria Recognition Arrangement**
- Agreement between participating countries to **mutually recognize**
  CC evaluation certificates
- Means: A product evaluated in one country is accepted in all member
  countries — no re-evaluation needed
- Currently includes **USA, UK, Germany, France, Japan, Canada, Australia**
  and others
- Maximum mutual recognition level: **EAL2** (for full mutual recognition)
  — higher EALs may need additional country-specific review

> [!IMPORTANT]
> The CCRA is what makes Common Criteria **truly international**. Without
> mutual recognition, vendors would need separate evaluations in every country.

---

## 🔤 Abbreviations <a name="abbreviations"></a>

| Abbreviation | Full Form | One-line Meaning |
|---|---|---|
| **CC** | Common Criteria | International IT security evaluation standard — ISO/IEC 15408 |
| **TCSEC** | Trusted Computer System Evaluation Criteria | US DoD security evaluation framework — Orange Book |
| **ITSEC** | Information Technology Security Evaluation Criteria | European security evaluation framework |
| **TOE** | Target of Evaluation | The IT product or system being evaluated |
| **EAL** | Evaluation Assurance Level | Rating 1–7 indicating depth of security evaluation |
| **ST** | Security Target | Document with security claims for a specific TOE |
| **PP** | Protection Profile | Generic security requirements for a product category |
| **TSF** | TOE Security Functions | Security functions implemented within the TOE |
| **SFR** | Security Functional Requirements | What security features the product must have |
| **SAR** | Security Assurance Requirements | How rigorously the product must be evaluated |
| **CEM** | Common Evaluation Methodology | How evaluators conduct CC evaluations — ISO/IEC 18045 |
| **CCTL** | Common Criteria Testing Laboratory | Accredited independent lab that performs evaluations |
| **ETR** | Evaluation Technical Report | Report produced by CCTL summarizing evaluation results |
| **CCRA** | Common Criteria Recognition Arrangement | International mutual recognition agreement for CC certificates |
| **DoD** | Department of Defense | US government body that created TCSEC |
| **CIA** | Confidentiality, Integrity, Availability | Three core properties of information security |

---

## 🗝️ Keywords & Concept Map <a name="keywords"></a>

**Security Evaluation**
→ Formal assessment of whether an IT product meets its security claims
→ Performed by independent accredited labs (CCTL)
→ Result: Certificate + EAL rating
→ Different from audit — evaluates products, not organizations

**Common Criteria (CC)**
→ ISO/IEC 15408 — current international standard
→ Evolved from TCSEC (US) and ITSEC (Europe)
→ Three parts: General Model, SFR, SAR
→ Methodology defined by CEM (ISO/IEC 18045)

**EAL (Evaluation Assurance Level)**
→ 7 levels: EAL1 (lowest) → EAL7 (highest)
→ Higher = more rigorous evaluation, not more features
→ EAL4 = most common commercial level
→ EAL7 = formal mathematical verification — military grade

**TOE (Target of Evaluation)**
→ The specific IT product/system being evaluated
→ Described in the Security Target (ST)
→ Tested by CCTL against claimed EAL

**Protection Profile (PP)**
→ Generic requirements for a category of products
→ Created by communities, not individual vendors
→ TOE must meet PP claims if PP compliance is required

**Assurance**
→ Confidence that a product meets its security claims
→ Higher assurance = more evidence, more rigorous testing
→ Measured by EAL in Common Criteria

---

## ⚡ Quick Reference Cheatsheet <a name="cheatsheet"></a>

### EAL Levels — Complete Reference

| EAL | Name | Rigor | Typical Use |
|---|---|---|---|
| **EAL1** | Functionally Tested | Very Low | Basic commercial products |
| **EAL2** | Structurally Tested | Low | Simple security products |
| **EAL3** | Methodically Tested and Checked | Moderate | General enterprise products |
| **EAL4** | Methodically Designed, Tested and Reviewed | Medium-High | **Most commercial products** |
| **EAL5** | Semiformally Designed and Tested | High | High-security environments |
| **EAL6** | Semiformally Verified Design and Tested | Very High | Government/critical systems |
| **EAL7** | Formally Verified Design and Tested | Extreme | Military/classified systems |

### TCSEC Classes — Quick Reference

| Class | Level Name | Trust Level |
|---|---|---|
| D | Minimal Protection | ❌ Lowest |
| C1 | Discretionary Security | Low |
| C2 | Controlled Access | Low-Medium |
| B1 | Labeled Security | Medium |
| B2 | Structured Protection | Medium-High |
| B3 | Security Domains | High |
| A1 | Verified Design | ✅ Highest |

### Three Frameworks Comparison

| | TCSEC | ITSEC | CC |
|---|---|---|---|
| Origin | USA | Europe | International |
| Levels | D,C1,C2,B1,B2,B3,A1 | E0–E6 | EAL1–EAL7 |
| Focus | Confidentiality | CIA | CIA |
| Status | ❌ Superseded | ❌ Superseded | ✅ Current |

### CC Key Documents

| Document | Created By | Purpose |
|---|---|---|
| Protection Profile (PP) | Community/Industry | Generic requirements for product type |
| Security Target (ST) | Developer/Vendor | Specific claims for one product |
| Evaluation Technical Report (ETR) | CCTL | Summary of evaluation findings |
| CC Certificate | Certification Body | Formal certificate of evaluation |

### Evaluation Phases Summary

| Phase | Key Activity |
|---|---|
| Initiation | Scope, EAL target, evaluation plan |
| Document Review | ST, design docs, guides |
| Development Analysis | Architecture and design review |
| Testing | Functional + penetration testing |
| Assessment | Pass/fail determination |
| Reporting | ETR produced |

### SFR vs SAR — Quick Recall

| | SFR | SAR |
|---|---|---|
| Answers | What does it DO? | How confident are we? |
| CC Part | Part 2 | Part 3 |
| Focus | Features | Evaluation rigor |

---

## 🔁 Session Revision Snapshot <a name="snapshot"></a>

### TL;DR — 5 Bullets
- ✅ Security Evaluation = assessing whether a product meets security claims
  — done by independent labs, not developers
- ✅ Three frameworks: TCSEC (Orange Book/US) → ITSEC (Europe) → CC (Current/International)
- ✅ EAL1–EAL7: Higher number = more rigorous evaluation, NOT more features
- ✅ EAL4 is the most common commercial evaluation level
- ✅ CEM (ISO/IEC 18045) defines HOW to evaluate; CC (ISO/IEC 15408) defines WHAT to evaluate

### 🎯 Top MCQ-Likely Concepts from This Session
1. **EAL levels 1–7** — names, numbers, and what each means
2. **EAL4** — most common commercial level (very frequently tested)
3. **TCSEC classes** — D through A1, especially that D is worst and A1 is best
4. **CC vs CEM** — ISO/IEC 15408 vs ISO/IEC 18045
5. **PP vs ST** — generic vs product-specific (classic confusion trap)
6. **TCSEC = Orange Book** — this nickname appears in MCQs often
7. **SFR vs SAR** — what vs how confident
8. **TOE** — what it stands for and means
9. **CCTL independence** — why evaluator must be independent of developer

---