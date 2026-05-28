# 🔏 Session 04 — General Data Protection Regulation (GDPR)

## 📑 Table of Contents
- [What is GDPR](#what-is-gdpr)
- [GDPR Overview](#gdpr-overview)
- [Key GDPR Definitions](#key-definitions)
- [Who GDPR Applies To](#who-it-applies)
- [Types of Privacy Data GDPR Protects](#types-of-data)
  - [Personal Data](#personal-data)
  - [Special Categories of Data](#special-categories)
  - [Criminal Offence Data](#criminal-data)
- [GDPR Core Principles](#core-principles)
- [Rights of Data Subjects](#rights)
- [Key Steps to Ensure GDPR Compliance](#key-steps)
- [GDPR Roles](#gdpr-roles)
- [Legal Bases for Processing](#legal-bases)
- [Data Breach Notification Requirements](#breach-notification)
- [GDPR Penalties and Fines](#penalties)
- [📌 Extra Notes](#extra-notes)
  - [GDPR vs Prior Law — EU Directive 95/46/EC](#gdpr-vs-prior)
  - [Data Protection by Design and by Default](#privacy-by-design)
  - [Data Protection Impact Assessment (DPIA)](#dpia)
  - [Data Transfer Outside EU](#data-transfer)
  - [GDPR and India — DPDPA Connection](#india-connection)
  - [Key GDPR Articles to Know](#key-articles)
- [Abbreviations](#abbreviations)
- [Keywords & Concept Map](#keywords)
- [Quick Reference Cheatsheet](#cheatsheet)
- [Session Revision Snapshot](#snapshot)

---

## 🔰 What is GDPR <a name="what-is-gdpr"></a>

- **GDPR = General Data Protection Regulation**
- A **European Union (EU) regulation** on data protection and privacy
- Came into **force: 25 May 2018** — after a 2-year transition period
- Adopted by the **European Parliament and Council** on 27 April 2016
- Replaces the older **EU Data Protection Directive 95/46/EC**
- Applies across **all EU member states** — no need for individual country
  legislation (unlike a directive)
- Has **extraterritorial reach** — applies to ANY organization worldwide
  that processes data of EU residents

> [!IMPORTANT]
> GDPR is a **Regulation** (not a Directive) — meaning it applies
> **directly and uniformly** across all EU member states without each
> country needing to pass its own national law. This is a critical
> distinction and a common MCQ trap.

---

## 🏛️ GDPR Overview <a name="gdpr-overview"></a>

### Key Facts

| Attribute | Detail |
|---|---|
| **Full Name** | General Data Protection Regulation |
| **Regulation Number** | EU 2016/679 |
| **Adopted** | 27 April 2016 |
| **Came Into Force** | 25 May 2018 |
| **Replaces** | EU Data Protection Directive 95/46/EC |
| **Issued By** | European Parliament and Council of the EU |
| **Enforced By** | Data Protection Authorities (DPAs) in each EU member state |
| **Scope** | Any organization processing EU residents' data — worldwide |
| **Purpose** | Protect personal data and privacy of EU individuals |

### Why GDPR Was Needed
- The old Directive (1995) was created before smartphones, social media,
  cloud computing — massively outdated
- Inconsistent implementation across EU member states created legal gaps
- Massive growth in data collection by tech companies required stronger rules
- Citizens lacked meaningful control over their own data
- Cross-border data flows needed a unified regulatory framework

---

## 📖 Key GDPR Definitions <a name="key-definitions"></a>

| Term | GDPR Definition |
|---|---|
| **Personal Data** | Any information relating to an identified or identifiable natural person |
| **Data Subject** | The natural person whose personal data is being processed |
| **Data Controller** | Entity that determines the purposes and means of processing personal data |
| **Data Processor** | Entity that processes data on behalf of the controller |
| **Processing** | Any operation performed on personal data — collecting, storing, using, deleting |
| **Consent** | Freely given, specific, informed, and unambiguous indication of agreement |
| **Data Protection Authority (DPA)** | National supervisory authority enforcing GDPR in each EU member state |
| **Lead Supervisory Authority** | The DPA in the EU country where the controller has its main establishment |
| **Pseudonymisation** | Processing data so it can no longer be attributed to a person without additional info |
| **Anonymisation** | Irreversibly stripping all identifying info — anonymised data is NOT personal data |

> [!NOTE]
> **Pseudonymisation ≠ Anonymisation**
> - **Pseudonymised** data is still personal data — re-identification is possible
>   with additional information
> - **Anonymised** data is NOT personal data — re-identification is impossible
> This distinction is a very common MCQ trap.

---

## 🌍 Who GDPR Applies To <a name="who-it-applies"></a>

GDPR applies based on two criteria:

### Establishment Criterion
- Any organization **established in the EU** — regardless of where processing
  occurs

### Targeting Criterion (Extraterritorial Reach)
- Any organization **outside the EU** that:
  - **Offers goods or services** to EU residents (even if free)
  - **Monitors the behavior** of EU residents (e.g., tracking, profiling)

| Scenario | GDPR Applies? |
|---|---|
| EU company processing EU resident data | ✅ Yes |
| US company with EU website users | ✅ Yes |
| Indian company selling to EU customers | ✅ Yes |
| US company with zero EU customers | ❌ No |
| EU company processing non-EU resident data | ✅ Yes (established in EU) |

> [!WARNING]
> GDPR's extraterritorial reach is one of its most significant features —
> a company in Mumbai or New York that has EU customers MUST comply with
> GDPR. Geographic location of the company does NOT exempt it.

---

## 🗂️ Types of Privacy Data GDPR Protects <a name="types-of-data"></a>

### 🔵 Personal Data <a name="personal-data"></a>

**Any information** that can identify a natural person — directly or
indirectly:

| Category | Examples |
|---|---|
| **Identity Data** | Name, national ID number, passport number |
| **Contact Data** | Email address, phone number, home address |
| **Location Data** | GPS coordinates, IP address, postcode |
| **Online Identifiers** | Cookie IDs, device IDs, usernames |
| **Physical Data** | Photo, height, hair color |
| **Economic Data** | Income, bank account details |
| **Cultural/Social Data** | Lifestyle, social media activity |

> [!NOTE]
> Even an **IP address** is considered personal data under GDPR — because
> it can be used to identify a person. This is more expansive than many
> people expect.

---

### 🔴 Special Categories of Data <a name="special-categories"></a>

These are **sensitive personal data** types that get **extra protection**
under GDPR — processing is generally **prohibited** unless specific
exceptions apply:

| # | Special Category |
|---|---|
| 1 | **Racial or ethnic origin** |
| 2 | **Political opinions** |
| 3 | **Religious or philosophical beliefs** |
| 4 | **Trade union membership** |
| 5 | **Genetic data** |
| 6 | **Biometric data** (when used for unique identification) |
| 7 | **Health data** |
| 8 | **Sex life or sexual orientation** |

> [!IMPORTANT]
> There are **8 special categories** — memorize all of them. MCQs often
> ask "which of the following is a special category?" and include
> plausible-sounding distractors.

### Exceptions That Allow Processing Special Categories
- **Explicit consent** of the data subject
- **Employment and social security law** obligations
- **Vital interests** (life or death situations)
- **Legitimate activities** of foundations, associations with political,
  philosophical, religious, or trade union aims
- **Publicly made data** by the data subject
- **Legal claims** — establishment, exercise, or defence
- **Substantial public interest**
- **Medical purposes** — healthcare, public health
- **Public health** emergencies
- **Archiving, research, or statistics** in public interest

---

### ⚫ Criminal Offence Data <a name="criminal-data"></a>

- Data about **criminal convictions and offences** (Article 10)
- Not classified as a Special Category but receives similar protection
- Can only be processed under the **control of official authority** or when
  **authorized by EU/member state law**
- Example: Only courts and police can freely process criminal record data

---

## ⚖️ GDPR Core Principles <a name="core-principles"></a>

GDPR Article 5 defines **7 core principles** for data processing:

| # | Principle | Meaning |
|---|---|---|
| 1 | **Lawfulness, Fairness, Transparency** | Processing must have legal basis, be fair, and be transparent to data subjects |
| 2 | **Purpose Limitation** | Data collected for specified, explicit, legitimate purposes — not reused for other purposes |
| 3 | **Data Minimisation** | Only collect data that is adequate, relevant, and limited to what is necessary |
| 4 | **Accuracy** | Data must be accurate and kept up to date — inaccurate data must be corrected or erased |
| 5 | **Storage Limitation** | Data must not be kept longer than necessary for its purpose |
| 6 | **Integrity and Confidentiality** | Data must be protected against unauthorized access, loss, or destruction (security) |
| 7 | **Accountability** | Controller is responsible for and must demonstrate compliance with all principles |

> [!IMPORTANT]
> **Accountability** (Principle 7) is the most significant new principle
> added by GDPR compared to the old Directive. Organizations must not just
> comply — they must **prove** they comply. This drives all the documentation
> requirements.

> [!TIP]
> Memory trick for 7 principles:
> **"Lovely Fat Dogs Always Sleep In Apartments"**
> Lawfulness → Fairness → Data Minimisation → Accuracy →
> Storage Limitation → Integrity → Accountability

---

## 👤 Rights of Data Subjects <a name="rights"></a>

GDPR gives individuals **8 rights** over their personal data:

| Right | What It Means |
|---|---|
| **1. Right to be Informed** | Know when and how data is collected and used |
| **2. Right of Access** | Request a copy of all personal data held about them (Subject Access Request — SAR) |
| **3. Right to Rectification** | Request correction of inaccurate or incomplete data |
| **4. Right to Erasure** | Request deletion of data — "Right to be Forgotten" |
| **5. Right to Restrict Processing** | Request that processing be limited without erasing data |
| **6. Right to Data Portability** | Receive data in a structured, machine-readable format and transfer it |
| **7. Right to Object** | Object to processing — especially for direct marketing |
| **8. Rights re: Automated Decision Making** | Not be subject to solely automated decisions that significantly affect them |

> [!TIP]
> The **Right to Erasure = Right to be Forgotten** — this nickname appears
> in MCQs. It does NOT mean data must always be deleted — there are exceptions
> (legal obligation, public interest, etc.)

> [!NOTE]
> **Right to Data Portability** is new in GDPR — it did not exist in the
> old Directive. It applies only when processing is based on consent or
> contract AND is carried out by automated means.

---

## ✅ Key Steps to Ensure GDPR Compliance <a name="key-steps"></a>

### Step 1 — 🗺️ Map Your Data
- Identify what personal data you hold, where it came from, who you share
  it with
- Create a **Record of Processing Activities (RoPA)** — mandatory under
  Article 30
- Understand data flows across the organization

### Step 2 — ⚖️ Review Legal Bases
- Identify the **lawful basis** for each processing activity
- Document the chosen legal basis
- Ensure consent obtained is GDPR-compliant (freely given, specific,
  informed, unambiguous)

### Step 3 — 📄 Update Privacy Notices
- Privacy notices must be **clear, plain language, and easily accessible**
- Must explain: what data, why, how long, who it's shared with, data
  subject rights
- Layered notices recommended for complex processing

### Step 4 — 👤 Enable Data Subject Rights
- Establish processes to handle:
  - Subject Access Requests (SARs) — respond within **1 month**
  - Erasure requests
  - Rectification requests
  - Portability requests
- Train staff on how to identify and escalate these requests

### Step 5 — 🏢 Assign Roles and Responsibilities
- Appoint a **Data Protection Officer (DPO)** if required
- Define **Data Controllers** and **Data Processors**
- Establish clear accountability lines
- Update contracts with third-party processors (Data Processing Agreements)

### Step 6 — 🔒 Implement Security Measures
- **Technical measures:** Encryption, pseudonymisation, access controls,
  firewalls
- **Organisational measures:** Staff training, policies, procedures
- Ensure **Data Protection by Design and by Default**
- Conduct **Data Protection Impact Assessments (DPIAs)** for high-risk
  processing

### Step 7 — 📋 Conduct DPIAs
- Mandatory for processing likely to result in **high risk** to individuals
- Required before starting new high-risk processing activities
- Must consult the DPA if DPIA indicates high risk cannot be mitigated

### Step 8 — 🌍 Review Data Transfers
- Map all transfers of personal data **outside the EU/EEA**
- Ensure appropriate **transfer mechanisms** are in place:
  - Adequacy Decision
  - Standard Contractual Clauses (SCCs)
  - Binding Corporate Rules (BCRs)

### Step 9 — 📢 Prepare for Breaches
- Establish a **data breach response plan**
- Notify the **DPA within 72 hours** of becoming aware of a breach
- Notify affected **individuals without undue delay** if high risk to them
- Maintain a **breach register** — all breaches documented internally

### Step 10 — 📚 Train Staff and Review Regularly
- All staff handling personal data must receive GDPR training
- Regular review and update of policies and procedures
- Appoint GDPR champions or awareness leads in each department

---

## 👥 GDPR Roles <a name="gdpr-roles"></a>

### Data Controller
- Decides **why** (purpose) and **how** (means) personal data is processed
- Primary responsibility for GDPR compliance
- Must have a legal basis for processing
- Responsible for ensuring processors comply via contracts

### Data Processor
- Processes data **on behalf of** the controller
- Must only process data as instructed by the controller
- Must have a **Data Processing Agreement (DPA)** with the controller
- Also directly responsible for certain GDPR obligations

### Data Protection Officer (DPO)

| Aspect | Detail |
|---|---|
| **Mandatory When** | Public authority OR large scale processing of special categories OR large scale monitoring |
| **Role** | Advise on GDPR, monitor compliance, cooperate with DPA |
| **Independence** | Must report directly to highest management — cannot be instructed on tasks |
| **Qualification** | Expert knowledge of data protection law and practices |
| **Contact** | Details must be published and communicated to DPA |

> [!IMPORTANT]
> **DPO must be independent** — they cannot receive instructions on how to
> perform their tasks. They report directly to the highest level of
> management. If dismissed unfairly, it can be challenged as a GDPR violation.

### Data Subject
- The **natural person** whose data is being processed
- Has 8 rights under GDPR
- Can lodge complaints with the DPA
- Can claim compensation for material and non-material damage

---

## 📋 Legal Bases for Processing <a name="legal-bases"></a>

GDPR Article 6 defines **6 lawful bases** for processing personal data:

| # | Lawful Basis | When Used |
|---|---|---|
| 1 | **Consent** | Individual has given clear consent for a specific purpose |
| 2 | **Contract** | Processing necessary for a contract with the individual |
| 3 | **Legal Obligation** | Processing necessary to comply with law |
| 4 | **Vital Interests** | Processing necessary to protect someone's life |
| 5 | **Public Task** | Processing necessary for a public task or official authority |
| 6 | **Legitimate Interests** | Processing necessary for legitimate interests of controller or third party |

> [!WARNING]
> **Consent is NOT the only lawful basis** — this is a major misconception.
> Organizations often incorrectly assume they always need consent. There are
> 5 other valid bases. Also, consent must be **freely given** — it cannot be
> a condition of service if another legal basis exists.

---

## 🚨 Data Breach Notification Requirements <a name="breach-notification"></a>

### What is a Personal Data Breach?
- A breach of security leading to accidental or unlawful:
  - **Destruction** of personal data
  - **Loss** of personal data
  - **Alteration** of personal data
  - **Unauthorized disclosure** of personal data
  - **Unauthorized access** to personal data

### Notification Timeline

```
Breach Discovered
      ↓
   72 Hours
      ↓
Notify DPA (if risk to individuals)
      ↓
Without Undue Delay
      ↓
Notify Affected Individuals (if HIGH risk)
```

| Notification | Timeline | To Whom | When Required |
|---|---|---|---|
| **DPA Notification** | Within **72 hours** | Data Protection Authority | If breach likely to result in risk to rights and freedoms |
| **Individual Notification** | **Without undue delay** | Affected data subjects | Only if breach likely to result in **HIGH risk** |
| **No Notification Required** | — | — | If risk to individuals is unlikely (e.g., encrypted data lost) |

> [!IMPORTANT]
> **72 hours to notify the DPA** — this is one of the most tested numbers
> in GDPR MCQs. Not 24 hours, not 48 hours, not 7 days — **72 hours.**

### What to Include in DPA Notification
- Nature of the breach
- Categories and approximate number of data subjects affected
- Categories and approximate number of records affected
- DPO contact details
- Likely consequences of the breach
- Measures taken or proposed to address the breach

---

## 💰 GDPR Penalties and Fines <a name="penalties"></a>

GDPR has a **two-tier fine structure** — the most severe fines in data
protection history:

| Tier | Maximum Fine | Applicable Violations |
|---|---|---|
| **Lower Tier** | €10 million OR 2% of global annual turnover (whichever is higher) | Less severe violations — record keeping, DPO obligations, processor obligations |
| **Upper Tier** | €20 million OR 4% of global annual turnover (whichever is higher) | Most severe violations — core principles, data subject rights, international transfers, consent |

> [!WARNING]
> The fine is calculated as a percentage of **GLOBAL annual turnover** —
> not just EU revenue. For large tech companies this can mean billions in
> fines. The **4% / €20M** tier is the one most MCQs ask about.

### Notable GDPR Fines (Context Only — No Names Needed)
- The largest GDPR fines to date have been in the hundreds of millions of
  euros
- Violations of core principles and unlawful data transfers attract the
  highest fines
- DPAs can also issue warnings, reprimands, and temporary processing bans

---

## 📌 Extra Notes <a name="extra-notes"></a>

> [!NOTE]
> The concepts below extend beyond the basic syllabus but are directly
> MCQ-relevant. Worth knowing cold before the exam.

---

### 📜 GDPR vs Prior Law — EU Directive 95/46/EC <a name="gdpr-vs-prior"></a>

| Feature | EU Directive 95/46/EC | GDPR (EU 2016/679) |
|---|---|---|
| **Type** | Directive — needed national law | Regulation — directly applicable |
| **Year** | 1995 | 2016 (enforced 2018) |
| **Fines** | No harmonized fines | €20M / 4% global turnover |
| **DPO** | Not required | Required in many cases |
| **Data Portability** | Not included | New right added |
| **Right to Erasure** | Limited | Full Right to be Forgotten |
| **Breach Notification** | Not standardized | 72-hour rule |
| **Extraterritorial Reach** | Limited | Yes — global reach |
| **Consent** | Less strict | Freely given, specific, informed, unambiguous |

---

### 🛡️ Data Protection by Design and by Default <a name="privacy-by-design"></a>

- **Article 25** of GDPR
- **By Design:** Privacy and data protection built into systems and
  processes from the beginning — not added as an afterthought
- **By Default:** Default settings must be the most privacy-friendly option
  — maximum privacy without user action required

| Concept | Meaning | Example |
|---|---|---|
| **By Design** | Build privacy in from the start | Encrypting data at architecture stage |
| **By Default** | Most privacy-protective settings are default | App collects minimum data by default without user needing to opt out |

> [!TIP]
> **Privacy by Design** was coined by **Ann Cavoukian** — a privacy
> commissioner. GDPR made it a legal requirement. This name sometimes appears
> in MCQs.

---

### 📊 Data Protection Impact Assessment (DPIA) <a name="dpia"></a>

- **DPIA = Data Protection Impact Assessment**
- Mandatory before starting **high-risk processing activities**
- Required when processing is **likely to result in high risk** to
  individuals' rights and freedoms

### When DPIA is Mandatory
- Large-scale processing of **special categories** of data
- Systematic monitoring of a **publicly accessible area** (CCTV)
- Large-scale **profiling**
- Use of new technologies
- Processing that could result in **denial of service** to individuals

### DPIA Process Steps
```
Step 1 → Describe the processing and its purposes
Step 2 → Assess necessity and proportionality
Step 3 → Identify and assess risks to individuals
Step 4 → Identify measures to mitigate risks
Step 5 → Consult DPA if high risk cannot be mitigated
```

---

### 🌍 Data Transfer Outside EU <a name="data-transfer"></a>

Transferring personal data **outside the EU/EEA** requires one of these
mechanisms:

| Mechanism | Description |
|---|---|
| **Adequacy Decision** | European Commission declares a country has adequate protection (e.g., UK, Japan, Canada) |
| **Standard Contractual Clauses (SCCs)** | Pre-approved contractual terms ensuring adequate protection |
| **Binding Corporate Rules (BCRs)** | Internal rules for multinational companies approved by a DPA |
| **Derogations** | Specific exceptions — consent, vital interests, legal claims |

> [!IMPORTANT]
> The **US-EU Privacy Shield** was invalidated by the **Schrems II ruling
> (2020)**. Standard Contractual Clauses (SCCs) are now the primary
> mechanism for EU-US data transfers. This is MCQ-worthy.

---

### 🇮🇳 GDPR and India — DPDPA Connection <a name="india-connection"></a>

- India's **Digital Personal Data Protection Act 2023 (DPDPA)** was
  heavily influenced by GDPR
- Similar concepts: consent, data principals (= data subjects), data
  fiduciaries (= data controllers), data processors
- Key difference: DPDPA currently **does not apply extraterritorially**
  in the same broad way as GDPR
- This connection is covered more in **Session 12** of this module

> [!NOTE]
> This connection is important — GDPR principles appear in India's DPDPA
> with slightly different terminology. Understanding GDPR well means you
> partially understand DPDPA already.

---

### 📑 Key GDPR Articles to Know <a name="key-articles"></a>

| Article | Topic |
|---|---|
| **Article 4** | Definitions (personal data, processing, controller, processor etc.) |
| **Article 5** | Principles of processing (7 core principles) |
| **Article 6** | Lawful bases for processing (6 bases) |
| **Article 7** | Conditions for consent |
| **Article 9** | Special categories of data (8 types) |
| **Article 10** | Criminal offence data |
| **Article 13/14** | Right to be informed |
| **Article 15** | Right of access |
| **Article 16** | Right to rectification |
| **Article 17** | Right to erasure (Right to be Forgotten) |
| **Article 18** | Right to restrict processing |
| **Article 20** | Right to data portability |
| **Article 21** | Right to object |
| **Article 22** | Automated decision making |
| **Article 25** | Data protection by design and by default |
| **Article 30** | Records of processing activities (RoPA) |
| **Article 33** | Breach notification to DPA (72 hours) |
| **Article 34** | Breach notification to individuals |
| **Article 35** | Data Protection Impact Assessment (DPIA) |
| **Article 37** | Designation of DPO |
| **Article 83** | Fines — two-tier structure |

---

## 🔤 Abbreviations <a name="abbreviations"></a>

| Abbreviation | Full Form | One-line Meaning |
|---|---|---|
| **GDPR** | General Data Protection Regulation | EU regulation on data protection and privacy — enforced from May 2018 |
| **DPA** | Data Protection Authority | National body enforcing GDPR in each EU member state |
| **DPO** | Data Protection Officer | Mandatory role for certain organizations — monitors GDPR compliance |
| **DPD** | Data Protection Directive | Old EU directive (95/46/EC) replaced by GDPR |
| **DPIA** | Data Protection Impact Assessment | Risk assessment for high-risk processing activities |
| **RoPA** | Record of Processing Activities | Mandatory documentation of all processing activities (Article 30) |
| **SAR** | Subject Access Request | Formal request by individual to access their personal data |
| **SCC** | Standard Contractual Clauses | Pre-approved contracts for transferring data outside EU |
| **BCR** | Binding Corporate Rules | Internal multinational company rules for data transfers |
| **EEA** | European Economic Area | EU + Norway, Iceland, Liechtenstein — GDPR applies within EEA |
| **ICO** | Information Commissioner's Office | UK's DPA — enforces GDPR / UK GDPR in the United Kingdom |
| **CNIL** | Commission Nationale de l'Informatique et des Libertés | France's DPA |
| **CUI** | Controlled Unclassified Information | (US concept — different from GDPR but related to data protection) |
| **DPDPA** | Digital Personal Data Protection Act | India's data protection law (2023) — influenced by GDPR |

---

## 🗝️ Keywords & Concept Map <a name="keywords"></a>

**GDPR**
→ EU Regulation 2016/679 — directly applicable across all EU member states
→ Enforced from 25 May 2018 — replaced Directive 95/46/EC
→ Extraterritorial reach — applies globally to any org processing EU data
→ Enforced by national DPAs — maximum fine 4% global turnover / €20M

**Personal Data**
→ Any info relating to identified or identifiable natural person
→ Includes IP addresses, cookie IDs, photos — broader than expected
→ Special categories get extra protection (8 types)
→ Anonymised data is NOT personal data — pseudonymised data IS

**Data Controller**
→ Decides WHY and HOW data is processed
→ Primary GDPR compliance responsibility
→ Must have lawful basis for processing
→ Must ensure processors comply via Data Processing Agreements

**Data Processor**
→ Processes data ON BEHALF of controller
→ Must follow controller's instructions
→ Has direct obligations under GDPR (breach notification, security)
→ Must have signed Data Processing Agreement with controller

**7 Principles (Article 5)**
→ Lawfulness/Fairness/Transparency, Purpose Limitation, Data Minimisation
→ Accuracy, Storage Limitation, Integrity/Confidentiality, Accountability
→ Accountability is the most significant new addition from old Directive

**8 Rights of Data Subjects**
→ Informed, Access, Rectification, Erasure, Restrict, Portability, Object,
   Automated Decision Making
→ Most requests must be responded to within 1 month
→ Right to Erasure = Right to be Forgotten

**Data Breach**
→ 72 hours to notify DPA
→ Without undue delay to notify individuals (only if HIGH risk)
→ All breaches must be documented internally regardless

---

## ⚡ Quick Reference Cheatsheet <a name="cheatsheet"></a>

### 7 GDPR Principles — Quick Reference

| # | Principle | One-liner |
|---|---|---|
| 1 | Lawfulness, Fairness, Transparency | Legal basis + honest + open |
| 2 | Purpose Limitation | Use data only for stated purpose |
| 3 | Data Minimisation | Collect only what you need |
| 4 | Accuracy | Keep data correct and updated |
| 5 | Storage Limitation | Don't keep data longer than needed |
| 6 | Integrity & Confidentiality | Secure the data |
| 7 | Accountability | Prove you comply |

### 8 Special Categories of Data

| # | Special Category |
|---|---|
| 1 | Racial or ethnic origin |
| 2 | Political opinions |
| 3 | Religious or philosophical beliefs |
| 4 | Trade union membership |
| 5 | Genetic data |
| 6 | Biometric data (for unique ID) |
| 7 | Health data |
| 8 | Sex life or sexual orientation |

### 8 Data Subject Rights

| # | Right | Key Detail |
|---|---|---|
| 1 | To be Informed | Know how data is used |
| 2 | Access (SAR) | Get a copy — respond in 1 month |
| 3 | Rectification | Fix wrong data |
| 4 | Erasure | Right to be Forgotten |
| 5 | Restrict Processing | Pause but don't delete |
| 6 | Data Portability | Machine-readable copy |
| 7 | Object | Stop processing — especially marketing |
| 8 | Automated Decision Making | No solely automated significant decisions |

### 6 Legal Bases for Processing

| # | Basis | When |
|---|---|---|
| 1 | Consent | Individual agrees |
| 2 | Contract | Needed for contract |
| 3 | Legal Obligation | Required by law |
| 4 | Vital Interests | Life or death |
| 5 | Public Task | Official authority |
| 6 | Legitimate Interests | Controller's genuine interest |

### GDPR Fine Structure

| Tier | Max Fine | Violations |
|---|---|---|
| Lower | €10M or 2% turnover | Technical/procedural violations |
| Upper | €20M or 4% turnover | Core principles, rights, transfers |

### Key GDPR Timelines

| Event | Timeline |
|---|---|
| DPA breach notification | **72 hours** |
| Individual breach notification | Without undue delay (high risk only) |
| SAR response | **1 month** (extendable by 2 months) |
| GDPR enforcement start | **25 May 2018** |
| GDPR adoption | 27 April 2016 |

### Controller vs Processor

| | Controller | Processor |
|---|---|---|
| Decides | WHY and HOW | Only acts as instructed |
| Primary responsibility | ✅ Yes | Shared |
| Needs lawful basis | ✅ Yes | No — relies on controller |
| Can be fined directly | ✅ Yes | ✅ Yes (certain obligations) |

---

## 🔁 Session Revision Snapshot <a name="snapshot"></a>

### TL;DR — 5 Bullets
- ✅ GDPR = EU Regulation 2016/679 — enforced 25 May 2018 — extraterritorial
  reach — applies globally to anyone processing EU resident data
- ✅ 7 core principles: Lawfulness/Fairness/Transparency, Purpose Limitation,
  Data Minimisation, Accuracy, Storage Limitation, Integrity/Confidentiality,
  Accountability
- ✅ 8 special categories get extra protection — health, biometric, genetic,
  racial origin, political opinions, religious beliefs, trade union, sex life
- ✅ Breach notification: **72 hours** to DPA — without undue delay to
  individuals (only if HIGH risk)
- ✅ Two-tier fines: Lower = €10M/2%, Upper = **€20M/4% global turnover**

### 🎯 Top MCQ-Likely Concepts from This Session
1. **72-hour breach notification** to DPA — most tested GDPR number
2. **4% / €20M fine** — upper tier for most serious violations
3. **8 special categories** — know all 8 cold
4. **7 core principles** — especially Accountability as the new addition
5. **8 data subject rights** — especially Right to Erasure = Right to be
   Forgotten
6. **6 lawful bases** — consent is NOT the only one
7. **Pseudonymisation vs Anonymisation** — pseudonymised IS still personal
   data
8. **GDPR is a Regulation not a Directive** — applies directly without
   national legislation
9. **Controller vs Processor** — who decides vs who executes
10. **DPO independence** — reports to highest management, cannot be instructed

---