# Session 01 — Information Security, Security Attacks & Threats

## 📑 Table of Contents

- [1. Information Security](#1-information-security)
  - [1.1 Definition & Scope](#11-definition--scope)
  - [1.2 The CIA Triad](#12-the-cia-triad)
  - [1.3 Extended Security Properties](#13-extended-security-properties)
  - [1.4 Parkerian Hexad](#14-parkerian-hexad)
  - [1.5 McCumber Cube](#15-mccumber-cube)
  - [1.6 Key Terminology — Assets, Vulnerability, Threat, Risk, Exploit](#16-key-terminology--assets-vulnerability-threat-risk-exploit)
  - [1.7 Security Controls](#17-security-controls)
  - [1.8 Defence in Depth](#18-defence-in-depth)
  - [1.9 Information Security vs Cybersecurity vs Network Security](#19-information-security-vs-cybersecurity-vs-network-security)
- [2. Security Attacks & Threats](#2-security-attacks--threats)
  - [2.1 RFC 2828 / X.800 Definitions](#21-rfc-2828--x800-definitions)
  - [2.2 Passive vs Active Attacks](#22-passive-vs-active-attacks)
  - [2.3 Inside vs Outside Attacks](#23-inside-vs-outside-attacks)
  - [2.4 Categories of Active Attacks](#24-categories-of-active-attacks)
  - [2.5 Categories of Passive Attacks](#25-categories-of-passive-attacks)
  - [2.6 Threat Actors / Sources](#26-threat-actors--sources)
  - [2.7 Vulnerability Classification](#27-vulnerability-classification)
  - [2.8 Risk — Formula & Components](#28-risk--formula--components)
- [3. 📌 Extra Notes](#3--extra-notes)
  - [3.1 DAD Triad](#31-dad-triad)
  - [3.2 STRIDE Threat Model](#32-stride-threat-model)
  - [3.3 PASTA Model](#33-pasta-model)
  - [3.4 CVSS & CVE](#34-cvss--cve)
  - [3.5 OSI Security Architecture — X.800 Deep Dive](#35-osi-security-architecture--x800-deep-dive)
  - [3.6 APT — Advanced Persistent Threat](#36-apt--advanced-persistent-threat)
  - [3.7 Zero-Day Vulnerability](#37-zero-day-vulnerability)
  - [3.8 Threat Intelligence Types](#38-threat-intelligence-types)
  - [3.9 ISO/IEC 27001 vs NIST CSF — Quick Contrast](#39-isoiec-27001-vs-nist-csf--quick-contrast)
  - [3.10 Common Attack Taxonomy — Motive / Means / Opportunity](#310-common-attack-taxonomy--motive--means--opportunity)
- [4. Abbreviations Table](#4-abbreviations-table)
- [5. Keywords + Concept Map](#5-keywords--concept-map)
- [6. Quick Reference Cheatsheet](#6-quick-reference-cheatsheet)
- [7. Session Revision Snapshot](#7-session-revision-snapshot)

---

## 1. Information Security

### 1.1 Definition & Scope

**Information Security (InfoSec)** is the practice of protecting information and information systems from unauthorized access, use, disclosure, disruption, modification, or destruction — regardless of the form the information takes (digital, physical, verbal).

> [!IMPORTANT]
> InfoSec protects information **in all forms** — not just digital.
> Cybersecurity is a **subset** of InfoSec that focuses on digital/cyber assets.

The three pillars that every security decision maps back to:
- **People** — the weakest link; social engineering targets this layer
- **Process** — policies, procedures, standards, guidelines
- **Technology** — tools, controls, hardware/software mechanisms

---

### 1.2 The CIA Triad

The **CIA Triad** is the foundational model for all information security goals.

| Property | Definition | Violated By | Example Control |
|----------|-----------|-------------|-----------------|
| **Confidentiality** | Ensuring information is accessible only to those authorized to access it | Eavesdropping, data theft, sniffing | Encryption, access controls, ACLs |
| **Integrity** | Safeguarding accuracy and completeness of information; preventing unauthorized modification | Tampering, man-in-the-middle, bit flipping | Hashing (SHA), digital signatures, checksums |
| **Availability** | Ensuring authorized users have access to information when needed | DoS/DDoS, ransomware, hardware failure | Redundancy, backups, failover, UPS |

> [!NOTE]
> In exam MCQs, map every attack to the CIA property it violates:
> - Ransomware → **Availability** (and sometimes Confidentiality)
> - Data tampering → **Integrity**
> - Shoulder surfing → **Confidentiality**
> - Website defacement → **Integrity**
> - DDoS → **Availability**

---

### 1.3 Extended Security Properties

Beyond CIA, these four properties are frequently tested:

| Property | Definition |
|----------|-----------|
| **Authentication** | Verifying the identity of a user, process, or device — "Are you who you claim to be?" |
| **Non-repudiation** | Assurance that the sender cannot deny sending a message, and the receiver cannot deny receiving it |
| **Accountability** | Actions of an entity can be traced uniquely to that entity (audit logs, access logs) |
| **Authorization** | Determining what an authenticated entity is permitted to do (permissions, rights, privileges) |

> [!TIP]
> **Non-repudiation** is primarily achieved through **digital signatures**.
> Authentication + Integrity + Non-repudiation together = the value of PKI.

---

### 1.4 Parkerian Hexad

Donn Parker expanded the CIA Triad into **6 properties** (Parkerian Hexad):

| # | Property | Meaning |
|---|----------|---------|
| 1 | Confidentiality | Same as CIA |
| 2 | Integrity | Same as CIA |
| 3 | Availability | Same as CIA |
| 4 | **Possession / Control** | Ownership of the physical medium holding data — losing a USB drive violates this even if data is encrypted |
| 5 | **Authenticity** | Data is genuine and not forged |
| 6 | **Utility** | Data is in a usable form — encrypted data you lost the key for has zero utility |

> [!NOTE]
> The difference between **Confidentiality** and **Possession**: If you lose an encrypted USB, confidentiality may be intact, but **possession** is violated.
> The difference between **Integrity** and **Authenticity**: Integrity = data not altered; Authenticity = data came from a genuine source.

---

### 1.5 McCumber Cube

The **McCumber Cube** (John McCumber, 1991) is a 3D model used to evaluate information security. It has three axes:

**Axis 1 — Goals (CIA):**
- Confidentiality, Integrity, Availability

**Axis 2 — Information States:**
- **Storage (at rest)** — data stored on disk, database
- **Transmission (in transit)** — data moving across a network
- **Processing (in use)** — data being actively computed/used

**Axis 3 — Security Countermeasures:**
- **Policies & Procedures** — rules and guidelines
- **Human Factors** — awareness, training
- **Technology** — hardware/software controls

> [!NOTE]
> The cube has **3 × 3 × 3 = 27 cells**. Each cell represents a unique combination of a security goal, information state, and countermeasure type.
> MCQ trap: McCumber Cube = **27 cells**, not 9.

---

### 1.6 Key Terminology — Assets, Vulnerability, Threat, Risk, Exploit

These five terms are foundational and frequently confused in MCQs:

| Term | Definition | Example |
|------|-----------|---------|
| **Asset** | Anything of value to the organization that needs protection | Database, server, employee data, reputation |
| **Vulnerability** | A weakness or flaw in a system that can be exploited | Unpatched software, weak password policy, open port |
| **Threat** | Any potential event or actor that could exploit a vulnerability and harm an asset | Hacker, malware, natural disaster, insider |
| **Threat Agent / Actor** | The entity that carries out the threat | Script kiddie, nation-state, disgruntled employee |
| **Exploit** | The actual technique or code used to take advantage of a vulnerability | Buffer overflow code, SQL injection payload |
| **Risk** | The likelihood that a threat will exploit a vulnerability × the impact | High-risk = high probability × high impact |
| **Attack** | An intentional action taken by a threat agent to harm an asset | Port scanning, phishing, DDoS |
| **Countermeasure / Control** | A safeguard put in place to reduce risk | Firewall, encryption, training |
| **Exposure** | The state of being open to harm due to a vulnerability | A server on the internet with port 23 open |

> [!IMPORTANT]
> Relationship chain to memorize:
> **Threat Agent** → exploits → **Vulnerability** → to attack → **Asset** → causing → **Risk/Impact**
> A **threat** requires a **vulnerability** to become an **attack**.
> No vulnerability = no attack (in theory).

---

### 1.7 Security Controls

Security controls are safeguards or countermeasures. They are classified by **function** and by **type**:

#### By Function

| Function | Description | Examples |
|----------|-------------|---------|
| **Preventive** | Stop an attack before it happens | Firewall, encryption, access control, MFA |
| **Detective** | Identify and record an attack in progress or after | IDS, audit logs, CCTV, honeypots |
| **Corrective** | Reduce impact after an attack; restore systems | Backup restore, patch management, incident response |
| **Deterrent** | Discourage attackers from attempting an attack | Warning banners, legal notices, security guards |
| **Compensating** | Alternative controls when primary controls aren't feasible | Manual review when automated scanning isn't possible |
| **Directive** | Guide people to comply with security policy | Policies, procedures, awareness training |

#### By Type / Layer

| Type | Description | Examples |
|------|-------------|---------|
| **Administrative** | Management-level controls (policies, procedures) | Acceptable use policy, security awareness training |
| **Technical / Logical** | Software and hardware-based controls | Firewalls, IDS/IPS, encryption, antivirus |
| **Physical** | Physical access and environmental controls | Locks, biometrics, security guards, CCTV |

> [!TIP]
> MCQ favourite: A **firewall** is a **preventive + technical** control.
> An **IDS** is a **detective + technical** control.
> A **security policy** is a **directive + administrative** control.

---

### 1.8 Defence in Depth

**Defence in Depth (DiD)** is a layered security strategy — multiple overlapping security controls so that if one fails, others still protect the asset.

Layers (outside to inside):
```
Internet
   ↓
[ Perimeter — Firewall, DMZ ]
   ↓
[ Network — IDS/IPS, VLANs, NAC ]
   ↓
[ Host — Antivirus, Host Firewall, Patch Management ]
   ↓
[ Application — Input validation, WAF, Secure Coding ]
   ↓
[ Data — Encryption, Access Controls, DLP ]
   ↓
[ Physical — Locks, Biometrics, CCTV ]
```

> [!NOTE]
> Defence in Depth is also called **"castle approach"** — like a castle with moat + walls + guards + vault.
> The concept originates from **NSA** guidelines and is referenced in NIST SP 800-53.

---

### 1.9 Information Security vs Cybersecurity vs Network Security

| Term | Scope | Focus |
|------|-------|-------|
| **Information Security** | Broadest — all information in any form | Protecting data regardless of format (physical, digital, verbal) |
| **Cybersecurity** | Digital systems, cyberspace | Protecting networks, devices, programs from digital attacks |
| **Network Security** | Network infrastructure | Protecting the usability and integrity of networks and data in transit |

> [!NOTE]
> Venn diagram: Network Security ⊂ Cybersecurity ⊂ Information Security

---

## 2. Security Attacks & Threats

### 2.1 RFC 2828 / X.800 Definitions

Two key standards define security terminology formally:

- **RFC 2828** — Internet Security Glossary (IETF)
- **X.800** — Security Architecture for OSI (ITU-T) — also known as **ITU-T Recommendation X.800**

| Term | RFC 2828 / X.800 Definition |
|------|-----------------------------|
| **Threat** | A potential for violation of security — a possible danger that might exploit a vulnerability |
| **Attack** | An assault on system security that derives from an intelligent threat — a deliberate attempt to evade security services |
| **Security Attack** | Any action that compromises the security of information |
| **Security Mechanism** | A mechanism designed to detect, prevent, or recover from a security attack |
| **Security Service** | A processing or communication service that enhances the security of the data processing systems |

**X.800 defines 5 Security Services:**

| Service | Description |
|---------|-------------|
| **Authentication** | Assurance that the communicating entity is who it claims to be |
| **Access Control** | Protection against unauthorized use of resources |
| **Data Confidentiality** | Protection of data from unauthorized disclosure |
| **Data Integrity** | Assurance that data received is exactly what was sent — no modification |
| **Non-repudiation** | Protection against denial of a transmitted message by either party |

> [!IMPORTANT]
> X.800 Security Services are a very common MCQ source.
> Note: **Availability** is listed as a 6th service in extended X.800 interpretations (protection against DoS attacks).

---

### 2.2 Passive vs Active Attacks

This is one of the **highest-frequency MCQ topics** in any cryptography/security exam.

| Dimension | Passive Attack | Active Attack |
|-----------|---------------|---------------|
| **Goal** | Gain information without altering system/data | Modify data, disrupt service, or gain unauthorized access |
| **Nature** | Eavesdropping / monitoring | Masquerade, replay, modification, DoS |
| **Detection** | Very hard to detect — no trace left | Easier to detect — causes visible changes |
| **Prevention** | Encryption (primary defence) | Encryption + integrity checks + authentication |
| **CIA Violated** | Confidentiality | Integrity, Availability, sometimes Confidentiality |
| **Examples** | Traffic analysis, sniffing, shoulder surfing | Replay attack, spoofing, DDoS, data tampering |

> [!IMPORTANT]
> Key MCQ trap:
> - **Passive attacks** are hard to **detect** but easy to **prevent** (via encryption)
> - **Active attacks** are hard to **prevent** completely but easier to **detect**

---

### 2.3 Inside vs Outside Attacks

| Type | Attacker Position | Risk Level | Example |
|------|------------------|------------|---------|
| **Inside attack** | Internal — authorized user, employee, contractor | Higher — already past perimeter | Disgruntled employee exfiltrating data |
| **Outside attack** | External — no authorized access | Lower starting point but still dangerous | Hacker scanning external IPs |

> [!NOTE]
> Insider threats are statistically more damaging because insiders already have access and knowledge of systems. They bypass perimeter controls entirely.

---

### 2.4 Categories of Active Attacks

| Attack | Description | CIA Impact |
|--------|-------------|------------|
| **Masquerade (Spoofing)** | Attacker pretends to be a legitimate entity | Authentication, Integrity |
| **Replay Attack** | Valid data transmission is maliciously re-transmitted | Authentication, Integrity |
| **Modification of Messages** | Content of a legitimate message is altered | Integrity |
| **Denial of Service (DoS)** | Prevents legitimate use of services or resources | Availability |
| **Distributed DoS (DDoS)** | DoS launched from multiple compromised sources | Availability |
| **Repudiation** | Denying participation in a communication | Non-repudiation |
| **Man-in-the-Middle (MitM)** | Attacker intercepts and possibly alters communication between two parties | Confidentiality, Integrity |
| **Session Hijacking** | Attacker takes over an established session | Confidentiality, Integrity |
| **Privilege Escalation** | Gaining higher access than authorized | Confidentiality, Integrity |

---

### 2.5 Categories of Passive Attacks

| Attack | Description |
|--------|-------------|
| **Eavesdropping / Sniffing** | Capturing data packets in transit — using tools like Wireshark |
| **Traffic Analysis** | Even if content is encrypted, analyzing patterns (timing, frequency, size, source/destination) to infer information |
| **Shoulder Surfing** | Physically observing someone entering credentials |
| **Dumpster Diving** | Recovering discarded documents or media containing sensitive info |

> [!NOTE]
> **Traffic Analysis** is a passive attack that works **even when messages are encrypted**. Encryption hides content but not the fact that communication is happening.
> MCQ trap: Encryption alone does **not** prevent traffic analysis.

---

### 2.6 Threat Actors / Sources

| Actor Type | Motivation | Skill Level |
|-----------|------------|-------------|
| **Script Kiddie** | Fame, mischief | Low — uses pre-built tools |
| **Hacker (ethical)** | Discovery, improvement | High |
| **Cracker / Black Hat** | Financial gain, malice | High |
| **Insider Threat** | Revenge, financial gain, espionage | Varies |
| **Hacktivist** | Political/ideological motivation | Medium–High (e.g., Anonymous) |
| **Cybercriminal** | Financial gain | Medium–High |
| **Nation-State / APT** | Espionage, sabotage, warfare | Very High — highly funded |
| **Cyber Terrorist** | Fear, disruption, ideology | Varies |
| **Competitor** | Corporate espionage | Medium |

---

### 2.7 Vulnerability Classification

| Type | Description | Example |
|------|-------------|---------|
| **Design Vulnerability** | Flaw in the design/architecture of the system | Weak cipher algorithm choice |
| **Implementation Vulnerability** | Flaw in how a correctly designed system was built | Buffer overflow in C code |
| **Configuration Vulnerability** | Misconfiguration of a correctly implemented system | Default passwords left unchanged |
| **Physical Vulnerability** | Physical access risk | Unlocked server room |
| **Human Vulnerability** | Human error or susceptibility to manipulation | Clicking phishing links |

---

### 2.8 Risk — Formula & Components

**Risk Formula:**

```
Risk = Threat × Vulnerability × Impact
```

or, in simpler form:

```
Risk = Likelihood of Threat × Magnitude of Impact
```

| Component | Description |
|-----------|-------------|
| **Threat** | The source of potential harm |
| **Vulnerability** | Weakness that can be exploited |
| **Impact** | The damage caused if the threat exploits the vulnerability |
| **Likelihood** | Probability that a threat will occur |
| **Residual Risk** | Risk remaining after controls are applied |
| **Risk Appetite** | The level of risk an organization is willing to accept |

**Risk Treatment Options:**

| Option | Description |
|--------|-------------|
| **Risk Avoidance** | Stop doing the risky activity altogether |
| **Risk Mitigation / Reduction** | Apply controls to reduce likelihood or impact |
| **Risk Transfer** | Shift risk to a third party (e.g., insurance, outsourcing) |
| **Risk Acceptance** | Acknowledge the risk and accept the consequences |

> [!TIP]
> MCQ trap: Risk **cannot be eliminated entirely** — only reduced to an acceptable level. The remaining risk is called **residual risk**.

---

## 3. 📌 Extra Notes

> [!NOTE]
> Everything in this section goes beyond the core syllabus but is directly MCQ-relevant. Cross-referenced from Stallings, NIST publications, and RFC standards.

---

### 3.1 DAD Triad

> [!NOTE]
> The **DAD Triad** is the attacker's perspective — the mirror image of CIA:

| DAD | Attacks CIA | Method |
|-----|-------------|--------|
| **Disclosure** | Confidentiality | Sniffing, unauthorized access |
| **Alteration** | Integrity | Tampering, MitM |
| **Destruction / Denial** | Availability | DoS, ransomware, physical damage |

---

### 3.2 STRIDE Threat Model

> [!NOTE]
> **STRIDE** was developed by **Microsoft** (Praerit Garg & Loren Kohnfelder, 1999). It is used during threat modelling of applications/systems.

| Letter | Threat | CIA/Other Violated |
|--------|--------|--------------------|
| **S** | Spoofing | Authentication |
| **T** | Tampering | Integrity |
| **R** | Repudiation | Non-repudiation |
| **I** | Information Disclosure | Confidentiality |
| **D** | Denial of Service | Availability |
| **E** | Elevation of Privilege | Authorization |

> [!TIP]
> STRIDE maps directly to X.800 security properties — making it a bridge between threat modelling and security services.

---

### 3.3 PASTA Model

> [!NOTE]
> **PASTA** = **Process for Attack Simulation and Threat Analysis**
> A **7-stage, risk-centric** threat modelling framework (unlike STRIDE which is component-centric).

Stages:
1. Define objectives
2. Define technical scope
3. Application decomposition
4. Threat analysis
5. Vulnerability and weakness analysis
6. Attack modelling
7. Risk and impact analysis

> PASTA is used when the organization needs a business-risk-aligned view of threats, not just technical vulnerabilities.

---

### 3.4 CVSS & CVE

> [!NOTE]
> These are standard systems for tracking and scoring vulnerabilities — MCQ-relevant in any security exam.

| Term | Full Form | Description |
|------|-----------|-------------|
| **CVE** | Common Vulnerabilities and Exposures | A publicly maintained dictionary of known vulnerabilities; each gets a unique ID like `CVE-2021-44228` (Log4Shell) |
| **CVSS** | Common Vulnerability Scoring System | A framework for rating the severity of vulnerabilities on a scale of **0.0 to 10.0** |
| **NVD** | National Vulnerability Database | NIST's repository of CVE data with CVSS scores |
| **CWE** | Common Weakness Enumeration | Classification of software weaknesses (root causes) — different from CVE (instances) |

**CVSS Score Ranges:**

| Score | Severity |
|-------|----------|
| 0.0 | None |
| 0.1 – 3.9 | Low |
| 4.0 – 6.9 | Medium |
| 7.0 – 8.9 | High |
| 9.0 – 10.0 | Critical |

> [!TIP]
> CVE = **specific instance** of a known vulnerability.
> CWE = **category/type** of weakness.
> CVSS = **scoring system** for severity.
> These three are different things — a very common MCQ trap.

---

### 3.5 OSI Security Architecture — X.800 Deep Dive

> [!NOTE]
> **X.800** (ITU-T) defines a systematic framework for security in open systems. Stallings uses this extensively.

**Three main dimensions of X.800:**

1. **Security Attacks** — Passive and Active (covered above)
2. **Security Mechanisms** — How to implement security
3. **Security Services** — What security goals are achieved

**X.800 Security Mechanisms (8 specific):**

| Mechanism | Description |
|-----------|-------------|
| **Encipherment** | Encryption to provide confidentiality |
| **Digital Signature** | Data appended to a message to prove authenticity and non-repudiation |
| **Access Control** | Enforcing access rights to resources |
| **Data Integrity** | Mechanisms to verify data has not been altered |
| **Authentication Exchange** | Ensuring identity through challenge-response or similar |
| **Traffic Padding** | Inserting bits to frustrate traffic analysis |
| **Routing Control** | Selecting routes for secure transmission |
| **Notarization** | Using a trusted third party to assure properties of a data exchange |

> [!IMPORTANT]
> **Traffic Padding** is a mechanism specifically against **traffic analysis** (passive attack) — a very specific and commonly tested point.

---

### 3.6 APT — Advanced Persistent Threat

> [!NOTE]
> APTs are a category of threat actor commonly tested in modern security exams.

| Characteristic | Description |
|----------------|-------------|
| **Advanced** | Uses sophisticated, custom-built tools and zero-days |
| **Persistent** | Long-term campaign — weeks, months, years inside a network |
| **Threat** | Human-directed, intentional attack (not automated malware) |
| **Target** | Governments, defense, critical infrastructure, large corporations |
| **Attribution** | Often nation-state backed (e.g., APT28 = Russia, APT41 = China) |

Stages of an APT attack (aligned with Cyber Kill Chain):
1. Reconnaissance
2. Weaponization
3. Delivery (phishing, watering hole)
4. Exploitation
5. Installation (backdoor/RAT)
6. Command & Control (C2)
7. Actions on Objectives (exfiltration, destruction)

---

### 3.7 Zero-Day Vulnerability

> [!NOTE]

| Term | Definition |
|------|-----------|
| **Zero-Day Vulnerability** | A flaw that is unknown to the vendor — **no patch exists** at the time of discovery |
| **Zero-Day Exploit** | An exploit written specifically for a zero-day vulnerability |
| **Zero-Day Attack** | An attack leveraging a zero-day exploit |

- Called "zero-day" because the vendor has had **zero days** to fix it.
- After the vendor releases a patch, it is no longer a zero-day.
- Zero-days are sold on dark web markets — nation-states are major buyers.

---

### 3.8 Threat Intelligence Types

> [!NOTE]
> Threat intelligence is processed information about threats used to make security decisions.

| Type | Description | Audience |
|------|-------------|---------|
| **Strategic** | High-level, long-term trends; geopolitical context | C-suite, executives |
| **Tactical** | TTPs (Tactics, Techniques, Procedures) of threat actors | Security managers, architects |
| **Operational** | Specific details about planned or ongoing attacks | Incident response teams |
| **Technical** | IoCs — IP addresses, hashes, domains, signatures | SOC analysts, SIEM tools |

> **TTP** = Tactics, Techniques, Procedures (used in MITRE ATT&CK framework)
> **IoC** = Indicator of Compromise (e.g., malicious IP, file hash)

---

### 3.9 ISO/IEC 27001 vs NIST CSF — Quick Contrast

> [!NOTE]
> Both are framework-level standards — MCQ-relevant for their key differences.

| Dimension | ISO/IEC 27001 | NIST CSF |
|-----------|--------------|----------|
| **Origin** | International (ISO/IEC) | USA (NIST) |
| **Type** | Certifiable standard | Voluntary framework |
| **Focus** | ISMS — management system for InfoSec | Cybersecurity risk management framework |
| **Structure** | Clauses + Annex A controls (93 controls in 2022 version) | 5 Core Functions: Identify, Protect, Detect, Respond, Recover |
| **Audience** | Any organization globally | Primarily US critical infrastructure, but globally adopted |
| **Certification** | Yes — organizations can be ISO 27001 certified | No formal certification |
| **Latest Version** | ISO/IEC 27001:2022 | NIST CSF 2.0 (2024) |

> [!TIP]
> The **5 NIST CSF functions** in order: **Identify → Protect → Detect → Respond → Recover**
> ISO 27001:2022 reduced controls from **114 (in 2013 version) to 93**, organized in 4 themes.

---

### 3.10 Common Attack Taxonomy — Motive / Means / Opportunity

> [!NOTE]
> In forensics and security, every attack is analyzed through three lenses:

| Component | Description |
|-----------|-------------|
| **Motive** | Why the attack was carried out (financial, ideological, personal) |
| **Means** | Skills, tools, and resources the attacker had |
| **Opportunity** | Time and access required; vulnerability that enabled the attack |

All three must be present for an attack to occur:
```
Attack = Motive + Means + Opportunity
```

Remove any one element → attack either doesn't happen or fails.

---

## 4. Abbreviations Table

| Abbreviation | Full Form | One-Line Technical Meaning |
|---|---|---|
| CIA | Confidentiality, Integrity, Availability | Core triad of information security goals |
| DAD | Disclosure, Alteration, Destruction | Attacker's mirror of the CIA triad |
| DiD | Defence in Depth | Layered, overlapping security controls strategy |
| APT | Advanced Persistent Threat | Long-term, sophisticated, targeted cyber attack — often nation-state |
| CVE | Common Vulnerabilities and Exposures | Unique identifiers for known, publicly disclosed vulnerabilities |
| CVSS | Common Vulnerability Scoring System | 0–10 severity scoring system for vulnerabilities |
| NVD | National Vulnerability Database | NIST's centralized database of CVE entries with CVSS scores |
| CWE | Common Weakness Enumeration | Classification system for types of software weaknesses |
| STRIDE | Spoofing Tampering Repudiation Information-disclosure DoS Elevation | Microsoft's threat modelling framework |
| PASTA | Process for Attack Simulation and Threat Analysis | 7-stage risk-centric threat modelling methodology |
| TTPs | Tactics, Techniques, Procedures | Attacker behavior descriptions used in threat intelligence |
| IoC | Indicator of Compromise | Artefact or observable evidence that a breach has occurred |
| ISMS | Information Security Management System | ISO 27001 framework for managing information security systematically |
| NIST CSF | National Institute of Standards and Technology Cybersecurity Framework | 5-function voluntary cybersecurity risk management framework |
| RFC | Request for Comments | IETF documents defining internet standards and terminology |
| MitM | Man-in-the-Middle | Attack where an adversary secretly intercepts and relays communications |
| DoS | Denial of Service | Attack that prevents legitimate users from accessing a service |
| DDoS | Distributed Denial of Service | DoS launched simultaneously from multiple compromised systems |
| ACL | Access Control List | Rules defining which users/systems can access specific resources |

---

## 5. Keywords + Concept Map

| Term | Definition | Connections | Use Cases |
|------|-----------|-------------|-----------|
| **Confidentiality** | Preventing unauthorized disclosure of information | CIA Triad, Encryption, ACL | Data at rest/transit protection |
| **Integrity** | Ensuring data is accurate and unaltered | Hashing, Digital Signatures, CIA | File verification, message authentication |
| **Availability** | Ensuring systems/data are accessible when needed | CIA, DoS attacks, Redundancy | SLAs, uptime requirements |
| **Threat** | Potential cause of harm to an asset | Threat Agent, Vulnerability, Risk | Risk assessment |
| **Vulnerability** | Weakness exploitable by a threat | CVE, CWE, Patch management | Penetration testing, vulnerability scans |
| **Risk** | Likelihood × Impact of a threat exploiting a vulnerability | Risk treatment, Residual Risk | Risk management frameworks |
| **Passive Attack** | Intercept without modification | Traffic analysis, sniffing | Encrypted channels as countermeasure |
| **Active Attack** | Modify, disrupt, or forge | Replay, MitM, Masquerade | Authentication + integrity controls |
| **Non-repudiation** | Neither party can deny communication occurred | Digital signatures, PKI | Legal compliance, email security |
| **Defence in Depth** | Multiple overlapping security layers | Perimeter, host, application, data | Enterprise security architecture |
| **STRIDE** | Threat model categorizing 6 attack types | Microsoft SDL, Threat modelling | Application security design |
| **Zero-Day** | Unknown vulnerability with no available patch | APT attacks, exploit markets | Patch management urgency |

---

## 6. Quick Reference Cheatsheet

### 🔸 CIA vs DAD Mapping

| CIA Property | DAD Threat | Attack Examples |
|---|---|---|
| Confidentiality | Disclosure | Sniffing, eavesdropping, shoulder surfing |
| Integrity | Alteration | Tampering, MitM, replay |
| Availability | Destruction/Denial | DoS, DDoS, ransomware |

---

### 🔸 Passive vs Active — One-Line Comparison

| | Passive | Active |
|---|---|---|
| **Action** | Monitor / collect | Modify / disrupt / forge |
| **Detection** | Difficult | Easier |
| **Prevention** | Encryption | Encryption + Auth + Integrity |
| **CIA Violated** | Confidentiality | Integrity / Availability |

---

### 🔸 Security Control Functions × Types Grid

| | Administrative | Technical | Physical |
|---|---|---|---|
| **Preventive** | Policies, AUP | Firewall, Encryption | Locks, Barriers |
| **Detective** | Audits, Reviews | IDS, Log monitoring | CCTV, Motion sensors |
| **Corrective** | Incident response plan | Backup restore, Patches | Fire suppression |
| **Deterrent** | Warning notices | Login banners | Security guards |

---

### 🔸 STRIDE → X.800 Security Service Mapping

| STRIDE | X.800 Service Violated |
|--------|----------------------|
| Spoofing | Authentication |
| Tampering | Data Integrity |
| Repudiation | Non-repudiation |
| Information Disclosure | Data Confidentiality |
| Denial of Service | Availability |
| Elevation of Privilege | Access Control |

---

### 🔸 CVSS Score → Severity

| Range | Severity |
|-------|----------|
| 0.0 | None |
| 0.1–3.9 | Low |
| 4.0–6.9 | Medium |
| 7.0–8.9 | High |
| 9.0–10.0 | Critical |

---

### 🔸 Key Standards Quick Ref

| Standard | Body | Focus | Certifiable? |
|----------|------|-------|-------------|
| ISO/IEC 27001:2022 | ISO/IEC | ISMS — 93 controls, 4 themes | Yes |
| NIST CSF 2.0 | NIST (USA) | 5 Functions: Identify, Protect, Detect, Respond, Recover | No |
| RFC 2828 | IETF | Internet security terminology/glossary | N/A |
| X.800 | ITU-T | OSI security architecture (attacks, mechanisms, services) | N/A |

---

## 7. Session Revision Snapshot

### ⚡ TL;DR — 5 Bullets

- ✅ CIA Triad = Confidentiality + Integrity + Availability — every security decision maps back to one of these
- ✅ Passive attacks intercept without modification (hard to detect, encryption prevents them); Active attacks modify/disrupt (easier to detect, harder to prevent)
- ✅ Threat × Vulnerability × Impact = Risk — all three must exist for an attack to cause harm
- ✅ X.800 defines 5 security services + 8 security mechanisms — the formal OSI-level security architecture
- ✅ Defence in Depth = layered security — never rely on a single control

---

### 🎯 MCQ-Likely Concepts — Everything Examiners Love

| Concept | Why It's Tricky |
|---------|----------------|
| Passive attacks are hard to **detect**, easy to **prevent** | Most students flip this |
| Traffic analysis works **even with encryption** | Counter-intuitive |
| McCumber Cube = **27 cells** | Many say 9 |
| CVE vs CWE vs CVSS | Three different systems — easily confused |
| STRIDE maps **Repudiation → Non-repudiation** (not Integrity) | Close enough to trap you |
| Risk **cannot be eliminated** — only reduced | Residual risk always remains |
| Parkerian Hexad adds **Possession, Authenticity, Utility** to CIA | The 3 extras are specific |
| ISO 27001:2022 = **93 controls** (was 114 in 2013) | Version-specific trap |
| NIST CSF functions order: **Identify → Protect → Detect → Respond → Recover** | Order matters |
| Insider threat bypasses **perimeter controls** entirely | Architectural implication |
| Defence in Depth = **NSA concept**, not ISO | Attribution trap |
| X.800 **Traffic Padding** counters **traffic analysis** | Mechanism-to-attack mapping |

---

<details>
<summary>🔬 Lab Content (Session 01 — No Lab Assigned)</summary>

No lab is assigned for Session 01 in the syllabus.
Lab work begins from Session 05 (CrypTool) and Session 09 (XCA).

</details>

---