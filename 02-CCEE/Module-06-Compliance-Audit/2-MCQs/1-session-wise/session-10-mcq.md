# 🎯 MCQ — Session 10: CIS Controls & Benchmarks

> 30 MCQs | Raw Fundamentals | 4 Options Each | Full Explanations
> Covers: CIS Overview, Controls History, v8 Controls, Implementation
> Groups, CIS Compliance, Benchmarks, Levels, SecureSuite + Extra Notes

---

## MCQ Set

---

**Q1. CIS stands for and is classified as which type of organization?**

A) Cyber Intelligence Service — a US government agency
B) Center for Internet Security — a nonprofit organization ✅
C) Center for Information Security — a standards body like ISO
D) Cybersecurity and Infrastructure Services — a federal department

> **Explanation:** **CIS = Center for Internet Security** — it is a
> **nonprofit organization** founded in 2000. It is NOT a government
> agency (that would be CISA), NOT a standards body like ISO, and NOT
> a regulatory authority. CIS develops and maintains the CIS Controls
> and CIS Benchmarks — both free and voluntary — through community
> collaboration.

---

**Q2. CIS was founded in which year and is headquartered in which
location?**

A) 1995 — Washington DC, USA
B) 2006 — Wakefield, Massachusetts, USA
C) 2000 — East Greenbush, New York, USA ✅
D) 2002 — Geneva, Switzerland

> **Explanation:** **CIS was founded in 2000** and is headquartered
> in **East Greenbush, New York, USA**. Wakefield, Massachusetts is
> the PCI SSC headquarters. Geneva, Switzerland is ISO headquarters.
> Washington DC is associated with many US government agencies but
> not CIS. Knowing the founding year and location is directly tested.

---

**Q3. The CIS Controls were originally developed by which
organization under what name?**

A) ISO/IEC — originally called ISO Security Controls
B) NIST — originally called NIST Critical Controls
C) ISACA — originally called COBIT Security Controls
D) SANS Institute — originally called SANS Top 20 ✅

> **Explanation:** The CIS Controls were **originally developed by
> the SANS Institute** and called the **"SANS Top 20"** (Twenty
> Critical Security Controls). Ownership was gradually transferred
> to the Council on Cybersecurity (2011) and then to CIS (2015).
> MCQs frequently test this historical connection — SANS Top 20 =
> the precursor to today's CIS Controls.

---

**Q4. In which year did the CIS Controls officially come under
the Center for Internet Security and receive the name
"CIS Critical Security Controls"?**

A) 2011
B) 2013
C) 2015 ✅
D) 2018

> **Explanation:** **2015** is when the Council on Cybersecurity
> became the Center for Internet Security (CIS) and the controls
> were formally rebranded as **CIS Critical Security Controls**.
> Version 6.0 was published under the CIS brand in 2015. Before
> this, the controls had been called CAG (2009), CSC (2013), and
> SANS Top 20 (2008).

---

**Q5. How many controls does CIS Controls v8 contain and when
was it published?**

A) 20 controls — published 2019
B) 18 controls — published 2019
C) 20 controls — published 2021
D) 18 controls — published May 2021 ✅

> **Explanation:** **CIS Controls v8 was published in May 2021 and
> contains 18 controls** — reduced from 20 in v7.1. This reduction
> came from merging related controls — not removing security
> requirements. The 20-control count belongs to v7.1 (2019).
> Both the number (18) and year (2021) are directly tested.

---

**Q6. CIS Controls v7.1 had 20 controls. CIS Controls v8 reduced
this to 18. Which of the following best explains this reduction?**

A) Two controls were found ineffective and removed entirely
B) Related controls were merged together — all concepts still exist ✅
C) The two removed controls were replaced by CIS Benchmarks
D) v8 removed all controls related to physical security

> **Explanation:** The reduction from 20 to 18 controls in v8 was
> achieved by **merging related controls** — for example, controls
> related to application whitelisting were merged into the software
> asset inventory control. No security requirements were eliminated —
> they were reorganized. The approach also shifted from device-centric
> to activity-based in v8.

---

**Q7. Which CIS Control specifically addresses maintaining an
inventory of all hardware assets within an organization?**

A) CIS Control 2 — Inventory and Control of Software Assets
B) CIS Control 3 — Data Protection
C) CIS Control 1 — Inventory and Control of Enterprise Assets ✅
D) CIS Control 4 — Secure Configuration of Enterprise Assets

> **Explanation:** **CIS Control 1 = Inventory and Control of
> Enterprise Assets** — it focuses on actively managing all
> hardware assets (computers, servers, network devices, mobile
> devices) so only authorized devices are allowed and all assets
> are known. CIS Control 2 covers software. CIS Control 4 covers
> secure configuration of those assets.

---

**Q8. CIS Control 18 — the last control in v8 — covers which
security activity?**

A) Incident Response Management
B) Application Software Security
C) Penetration Testing ✅
D) Service Provider Management

> **Explanation:** **CIS Control 18 = Penetration Testing** —
> testing the effectiveness of defenses through penetration
> testing and red team exercises. In v7.1 this was Control 20
> (the last control in that version too — just renumbered).
> CIS Control 17 = Incident Response Management. CIS Control 16
> = Application Software Security. CIS Control 15 = Service
> Provider Management.

---

**Q9. The three CIS Implementation Groups (IGs) are designed
to help organizations do which of the following?**

A) Certify their compliance with CIS Controls for regulatory purposes
B) Prioritize CIS Controls implementation based on organization size,
   resources, and risk profile ✅
C) Replace ISO 27001 certification with a CIS alternative
D) Rank the severity of cybersecurity incidents

> **Explanation:** **Implementation Groups are a risk-based
> prioritization tool** — they help organizations determine WHICH
> CIS Controls and safeguards to implement first based on their
> size, available resources, and risk exposure. They are NOT a
> certification program, NOT a replacement for ISO 27001, and NOT
> an incident severity scale. IG1 is for small orgs, IG2 for medium,
> IG3 for large.

---

**Q10. IG1 is described as "essential cyber hygiene" and is
targeted at which type of organization?**

A) Large enterprises with dedicated security teams and sensitive data
B) Government agencies with classified information
C) Small organizations with limited IT and cybersecurity resources ✅
D) Organizations already certified to ISO 27001

> **Explanation:** **IG1 targets small organizations with limited
> IT and cybersecurity resources** — it represents the minimum
> security baseline that ALL organizations should implement
> regardless of size. IG1 contains 56 safeguards covering the most
> fundamental protections against common attacks. IG3 targets large
> enterprises with security experts and sensitive data.

---

**Q11. How many safeguards does IG1 contain and how many does
full IG3 implementation cover in total?**

A) IG1 = 20 safeguards / IG3 = 100 total safeguards
B) IG1 = 56 safeguards / IG3 = 153 total safeguards ✅
C) IG1 = 56 safeguards / IG3 = 171 total safeguards
D) IG1 = 74 safeguards / IG3 = 153 total safeguards

> **Explanation:** **IG1 = 56 safeguards** (essential baseline).
> **IG3 = 153 total safeguards** (full implementation of all 18
> controls). IG2 adds 74 safeguards to IG1 (130 total). IG3 adds
> 23 more (153 total). The 171 figure was the total sub-controls
> in v7.1 — not v8. These specific numbers are directly tested.

---

**Q12. The CIS Implementation Groups are cumulative. This means:**

A) Each IG covers completely different controls from the others
B) IG3 organizations skip IG1 and IG2 and go straight to advanced
   controls
C) IG2 includes all IG1 safeguards plus additional ones — IG3
   includes all IG1 and IG2 safeguards ✅
D) Organizations must choose only one IG — they cannot mix safeguards

> **Explanation:** **IGs are cumulative** — IG2 includes all 56 IG1
> safeguards PLUS 74 additional ones (130 total). IG3 includes all
> IG1 + IG2 safeguards PLUS 23 more (153 total). An IG3 organization
> implements ALL safeguards across all 18 controls. Organizations
> build upward — complete IG1 first, then add IG2, then IG3.

---

**Q13. Which statement correctly distinguishes CIS Implementation
Groups from a maturity model?**

A) Implementation Groups and maturity models are identical concepts
B) IGs are a compliance certification framework — maturity models
   are voluntary
C) IGs are risk-based prioritization tools — maturity models measure
   process capability levels ✅
D) IGs apply only to large enterprises — maturity models apply to all
   organizations

> **Explanation:** **IGs are a prioritization tool** — they tell
> organizations WHICH controls to implement based on their risk
> profile. A **maturity model** (like COBIT's 0–5 scale) measures
> HOW WELL processes are implemented. IGs say "implement these 56
> safeguards first" — they do not rate the quality of
> implementation. NIST explicitly notes this distinction.

---

**Q14. CIS Benchmarks provide which type of security guidance
compared to CIS Controls?**

A) Strategic governance direction — higher level than CIS Controls
B) Technology-specific hardening configuration guidelines —
   more specific than CIS Controls ✅
C) Risk management methodology — complementary to CIS Controls
D) Legal compliance requirements for specific industries

> **Explanation:** **CIS Benchmarks are MORE specific than CIS
> Controls** — while CIS Control 4 says "implement secure
> configurations," a CIS Benchmark for Windows 11 tells you
> EXACTLY which registry settings, group policies, and services
> to configure. Benchmarks are the technical implementation
> guidance for CIS Control 4 specifically. Over 100 benchmarks
> cover specific OS, cloud, app, database, and device types.

---

**Q15. CIS Benchmarks are organized into two levels. Which
statement correctly describes Level 1?**

A) Advanced security for high-risk environments — may impact
   system functionality
B) Essential security baseline appropriate for all organizations —
   minimal functionality impact ✅
C) The highest security level — required for government systems only
D) A certification level — organizations can be certified to Level 1

> **Explanation:** **CIS Benchmark Level 1 = essential security
> baseline** — practical recommendations appropriate for ALL
> organizations with minimal impact on system functionality.
> **Level 2 = advanced security** — more restrictive configurations
> for sensitive/high-security environments that may impact
> functionality. Organizations should implement Level 1 first,
> then assess Level 2 applicability. Neither level involves
> certification.

---

**Q16. An organization wants to harden its AWS cloud environment
using CIS guidance. Which CIS product is most appropriate?**

A) CIS Controls v8 — IG1 implementation
B) CIS RAM — Risk Assessment Method
C) CIS Benchmark for Amazon Web Services (AWS) ✅
D) CIS CSAT — Controls Self-Assessment Tool

> **Explanation:** The **CIS Benchmark for AWS** provides specific,
> actionable configuration recommendations for hardening an AWS
> environment — covering IAM settings, S3 bucket policies,
> CloudTrail logging, VPC configurations, and more. CIS Controls
> provide strategic guidance but not AWS-specific settings.
> CIS RAM is a risk assessment method. CIS CSAT assesses Controls
> implementation maturity — not specific cloud configurations.

---

**Q17. The CIS Controls are described as "offense-informed defense."
This philosophy means:**

A) Organizations should launch offensive cyber operations against
   attackers
B) Controls are derived from analysis of real-world attacker
   techniques and threat data — not just theoretical frameworks ✅
C) Offensive security tools should replace defensive controls
D) Organizations must hire former hackers to implement CIS Controls

> **Explanation:** **Offense-informed defense** means the CIS
> Controls were developed by analyzing what attackers actually do
> in real-world incidents and working backwards to identify the
> controls that would have prevented or detected those attacks.
> This data-driven approach makes CIS Controls more practically
> effective than purely theoretical frameworks. It is the
> philosophical foundation of CIS Controls prioritization.

---

**Q18. CIS Control 7 addresses which security activity?**

A) Audit Log Management
B) Malware Defenses
C) Continuous Vulnerability Management ✅
D) Network Monitoring and Defense

> **Explanation:** **CIS Control 7 = Continuous Vulnerability
> Management** — continuously acquiring, assessing, and acting
> on vulnerability information to identify, remediate, or accept
> risks. CIS Control 8 = Audit Log Management. CIS Control 10 =
> Malware Defenses. CIS Control 13 = Network Monitoring and
> Defense. Knowing specific control numbers is tested in MCQs.

---

**Q19. Which CIS Control specifically covers protecting against
phishing and malicious web content through email and web browser
security?**

A) CIS Control 3 — Data Protection
B) CIS Control 7 — Continuous Vulnerability Management
C) CIS Control 9 — Email and Web Browser Protections ✅
D) CIS Control 14 — Security Awareness and Skills Training

> **Explanation:** **CIS Control 9 = Email and Web Browser
> Protections** — improving protections and detection capabilities
> for email-borne threats (phishing, malicious attachments) and
> web-based threats (drive-by downloads, malicious websites).
> CIS Control 14 covers security awareness training — the human
> side of phishing defense. CIS Control 9 covers the technical
> controls. Both together address phishing comprehensively.

---

**Q20. An organization suffers a ransomware attack. Based on CIS
Controls, which control is most directly relevant for ensuring
the organization can recover its data?**

A) CIS Control 7 — Continuous Vulnerability Management
B) CIS Control 10 — Malware Defenses
C) CIS Control 11 — Data Recovery ✅
D) CIS Control 18 — Penetration Testing

> **Explanation:** **CIS Control 11 = Data Recovery** — establishing
> and maintaining data recovery practices including backups, tested
> recovery procedures, and offline copies. This is the most directly
> relevant control for **recovering from** ransomware. CIS Control
> 10 (Malware Defenses) helps PREVENT ransomware. CIS Control 11
> ensures you can RECOVER when prevention fails.

---

**Q21. The CIS Community Defense Model (CDM) is designed to
answer which question?**

A) How should organizations certify their CIS Controls compliance?
B) Which CIS Controls should be prioritized to defend against the
   most common real-world attacks? ✅
C) How should organizations implement NIST CSF alongside CIS Controls?
D) Which organizations qualify for IG1 vs IG2 vs IG3?

> **Explanation:** The **CIS Community Defense Model (CDM)** is a
> data-driven model that maps CIS Controls and Safeguards to real-world
> attack patterns — answering "which controls stop which attacks
> most effectively?" Based on threat intelligence, CDM shows that
> implementing specific controls provides the highest return on
> security investment. It is NOT a certification framework or
> framework mapping tool.

---

**Q22. Mapping CIS Controls to NIST CSF — which CIS Controls
primarily map to the NIST CSF "Detect" function?**

A) CIS Controls 1, 2, 3, 15
B) CIS Controls 4, 5, 6, 9, 10, 14
C) CIS Controls 7, 8, 13 ✅
D) CIS Controls 17 and 11

> **Explanation:** The **NIST CSF Detect function** maps primarily
> to **CIS Controls 7 (Vulnerability Management), 8 (Audit Logs),
> and 13 (Network Monitoring)** — all focused on identifying when
> something is happening. CIS Controls 1, 2, 3, 15 map to Identify.
> CIS Controls 4, 5, 6, 9, 10, 14 map to Protect. CIS Control 17
> maps to Respond. CIS Control 11 maps to Recover.

---

**Q23. The CIS CSAT (Controls Self-Assessment Tool) provides
organizations with what output?**

A) A formal compliance certificate recognized by regulators
B) Automated scanning results for CIS Benchmark compliance
C) A maturity score for each CIS Control and gap analysis ✅
D) A legal attestation of information security effectiveness

> **Explanation:** **CIS CSAT** is a web-based tool that assesses
> the organization's current CIS Controls implementation and
> provides a **maturity score** for each control (levels 1–5)
> along with gap analysis and prioritized recommendations. It is
> NOT a certification tool. CIS-CAT Pro does automated benchmark
> scanning. No CIS tool provides a legally recognized attestation.

---

**Q24. CIS Hardened Images are pre-configured virtual machine
images that are particularly useful for which environment?**

A) On-premises data centers running legacy mainframe systems
B) Cloud deployments on AWS, Azure, or GCP ✅
C) Air-gapped government networks with no internet connectivity
D) Mobile device management for iOS and Android devices

> **Explanation:** **CIS Hardened Images** are pre-configured VM
> images already meeting CIS Benchmark standards — available on
> major **cloud marketplaces (AWS, Azure, GCP)**. They allow
> organizations to deploy already-hardened base images instead of
> manually applying hundreds of benchmark settings. This is
> particularly valuable in cloud environments where speed and
> automation of deployment are critical.

---

**Q25. Which of the following is a key difference between
CIS Controls v7.1 and CIS Controls v8?**

A) v7.1 introduced Implementation Groups — v8 removed them
B) v7.1 was free — v8 requires a paid CIS membership
C) v7.1 had 20 controls (device-centric) — v8 has 18 controls
   (activity-based) ✅
D) v7.1 covered all 18 controls — v8 reduced to 15 controls

> **Explanation:** The two key differences between v7.1 and v8:
> **Number of controls** (20 → 18) and **approach** (device-centric
> → activity/outcome-based). v8 enhanced coverage of cloud,
> mobile, and remote work environments. Both versions are free.
> Implementation Groups were introduced in v7 and refined in v8 —
> not removed. The 15-control count is fictional.

---

**Q26. An organization implementing CIS Controls for the first
time should begin with which Implementation Group?**

A) IG3 — to ensure maximum security from the start
B) IG2 — the middle ground between basic and advanced
C) IG1 — essential cyber hygiene that all organizations should
   implement first ✅
D) The IG appropriate to their industry sector regardless of size

> **Explanation:** **All organizations should begin with IG1** —
> regardless of size, industry, or existing security maturity.
> IG1 represents essential cyber hygiene and the foundational
> safeguards that stop the most common attacks. Since IGs are
> cumulative, IG2 and IG3 build on IG1 — starting with IG3
> without completing IG1 would leave fundamental gaps.

---

**Q27. The CIS RAM (Risk Assessment Method) is designed to work
most directly with which CIS product?**

A) CIS Benchmarks — providing risk scores for each configuration
B) CIS Hardened Images — assessing cloud deployment risk
C) CIS SecureSuite — for enterprise-level risk reporting
D) CIS Controls and Implementation Groups — aligned to IG1 and
   enterprise editions ✅

> **Explanation:** **CIS RAM is directly aligned to CIS Controls
> and Implementation Groups** — the IG1 edition of CIS RAM is
> for small organizations implementing IG1, while the Enterprise
> edition is for larger organizations. CIS RAM provides the risk
> assessment methodology that determines WHICH controls to prioritize
> within the CIS Controls framework — not benchmark configuration
> risk scoring.

---

**Q28. Which CIS Control specifically covers managing the security
of third-party service providers who have access to organizational
assets?**

A) CIS Control 12 — Network Infrastructure Management
B) CIS Control 15 — Service Provider Management ✅
C) CIS Control 16 — Application Software Security
D) CIS Control 17 — Incident Response Management

> **Explanation:** **CIS Control 15 = Service Provider Management**
> — developing a process to evaluate service providers who access
> organizational assets, including assessing their security
> practices and managing associated risks. This maps directly to
> ISO 27001's Supplier Relationships domain (A.15) and NIST CSF's
> supply chain risk management under Identify. Third-party risk
> is a standalone control in CIS v8.

---

**Q29. Comparing CIS Controls and NIST CSF — which statement
best describes their complementary relationship?**

A) CIS Controls replace NIST CSF — organizations only need one
B) NIST CSF provides strategic governance direction — CIS Controls
   provide specific technical implementation actions ✅
C) NIST CSF is for US government only — CIS Controls are for
   private sector
D) CIS Controls are mandatory — NIST CSF is voluntary

> **Explanation:** **NIST CSF + CIS Controls are complementary:**
> NIST CSF provides the **strategic framework** (Identify, Protect,
> Detect, Respond, Recover — what to do at a governance level).
> CIS Controls provide **specific technical actions** (exactly
> which safeguards to implement). Many organizations use both —
> NIST CSF for board-level communication and governance, CIS
> Controls for the IT team's implementation roadmap. Both are
> voluntary.

---

**Q30. Which combination of CIS facts is entirely correct?**

A) CIS founded 2006 / v8 has 20 controls / IG1 = 74 safeguards /
   Benchmarks have 3 levels / SANS Top 20 = current name
B) CIS founded 2000 / v8 has 18 controls / IG1 = 56 safeguards /
   Benchmarks have 2 levels / originally SANS Top 20 ✅
C) CIS founded 2000 / v7.1 has 18 controls / IG3 = 130 safeguards /
   Benchmarks have 2 levels / CIS-CAT = risk assessment tool
D) CIS founded 2000 / v8 has 18 controls / IG1 = 56 safeguards /
   Benchmarks have 3 levels / originally NIST Top 20

> **Explanation:** The fully correct combination is:
> **CIS founded 2000** ✅ (not 2006 — that's PCI SSC)
> **v8 has 18 controls** ✅ (not 20 — that was v7.1)
> **IG1 = 56 safeguards** ✅ (not 74 — that's additional IG2 safeguards)
> **Benchmarks have 2 levels** ✅ (Level 1 and Level 2 — not 3)
> **Originally SANS Top 20** ✅ (not NIST Top 20)
> Option A fails on founding year (2006 = PCI SSC), control count,
> and IG1 safeguards. Option C fails because v7.1 had 20 controls
> and IG3 = 153 (not 130). Option D fails because Benchmarks have
> 2 levels (not 3) and origin was SANS (not NIST).

---

## 📊 Quick Answer Key

| Q | Ans | Q | Ans | Q | Ans |
|---|---|---|---|---|---|
| 1 | B | 11 | B | 21 | B |
| 2 | C | 12 | C | 22 | C |
| 3 | D | 13 | C | 23 | C |
| 4 | C | 14 | B | 24 | B |
| 5 | D | 15 | B | 25 | C |
| 6 | B | 16 | C | 26 | C |
| 7 | C | 17 | B | 27 | D |
| 8 | C | 18 | C | 28 | B |
| 9 | B | 19 | C | 29 | B |
| 10 | C | 20 | C | 30 | B |

---

## 🎯 Topic Coverage Map

| Topic | MCQs Covered |
|---|---|
| CIS = nonprofit — full name | Q1 |
| CIS founded 2000 — East Greenbush, NY | Q2 |
| Originally SANS Top 20 | Q3 |
| CIS brand adopted 2015 | Q4 |
| v8 = 18 controls — May 2021 | Q5 |
| 20 → 18 reduction — merging not removing | Q6 |
| CIS Control 1 — enterprise asset inventory | Q7 |
| CIS Control 18 — penetration testing | Q8 |
| IGs = prioritization tool | Q9 |
| IG1 = small orgs — essential hygiene | Q10 |
| IG1 = 56 / IG3 = 153 safeguards | Q11 |
| IGs are cumulative | Q12 |
| IGs vs maturity model distinction | Q13 |
| Benchmarks = more specific than Controls | Q14 |
| Benchmark Level 1 = essential baseline | Q15 |
| CIS Benchmark for AWS | Q16 |
| Offense-informed defense philosophy | Q17 |
| CIS Control 7 — vulnerability management | Q18 |
| CIS Control 9 — email/web protections | Q19 |
| CIS Control 11 — data recovery | Q20 |
| CDM — attack-to-control mapping | Q21 |
| CIS vs NIST CSF — Detect function | Q22 |
| CIS CSAT — maturity scoring tool | Q23 |
| CIS Hardened Images — cloud use | Q24 |
| v7.1 vs v8 — device vs activity based | Q25 |
| Start with IG1 always | Q26 |
| CIS RAM — aligned to IGs | Q27 |
| CIS Control 15 — service providers | Q28 |
| NIST CSF + CIS = complementary | Q29 |
| Combined CIS facts — all key numbers | Q30 |

---