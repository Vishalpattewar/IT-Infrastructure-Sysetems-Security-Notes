# 🎯 MCQ — Session 11: SSE-CMM

> 30 MCQs | Raw Fundamentals | 4 Options Each | Full Explanations
> Covers: SSE-CMM Overview, History, Architecture, 22 PAs, 11 Security
> PAs, Capability Levels, Using SSE-CMM, Pilots + Extra Notes

---

## MCQ Set

---

**Q1. SSE-CMM stands for and was primarily developed by which
organization?**

A) Software Security Engineering Capability Maturity Model — SEI Carnegie Mellon
B) Systems Security Engineering Capability Maturity Model — ISSEA ✅
C) Systems Software Engineering Capability Maturity Model — ISACA
D) Secure Systems Engineering Capability Maturity Model — NIST

> **Explanation:** **SSE-CMM = Systems Security Engineering Capability
> Maturity Model** — developed by the **ISSEA (International Systems
> Security Engineering Association)**. It was initiated by the NSA and
> based on SW-CMM from SEI/Carnegie Mellon — but ISSEA is the
> developing organization. ISACA develops COBIT. NIST develops SP
> 800-series. Knowing both the full name AND developing organization
> is directly tested.

---

**Q2. The SSE-CMM project was initiated in 1993 by which US
government agency?**

A) CISA — Cybersecurity and Infrastructure Security Agency
B) NIST — National Institute of Standards and Technology
C) DHS — Department of Homeland Security
D) NSA — National Security Agency ✅

> **Explanation:** The **NSA (National Security Agency)** initiated
> the SSE-CMM research project in 1993 — driven by the need for a
> standard way to measure and improve security engineering capability
> in defense and government contractors. CISA was established much
> later (2018). NIST develops cybersecurity frameworks but did not
> initiate SSE-CMM. DHS had no role in SSE-CMM creation.

---

**Q3. SSE-CMM was based on and adapted from which earlier
capability maturity model?**

A) CMMI — Capability Maturity Model Integration
B) SW-CMM — Software Capability Maturity Model ✅
C) COBIT Maturity Model
D) ISO/IEC 15504 Process Assessment Model

> **Explanation:** **SSE-CMM is directly based on SW-CMM (Software
> Capability Maturity Model)** developed by SEI/Carnegie Mellon.
> SSE-CMM adopted the same 5-level capability structure and the
> concept of Process Areas from SW-CMM — but applied them to the
> domain of security engineering instead of software development.
> CMMI later succeeded SW-CMM but was developed after SSE-CMM.

---

**Q4. SSE-CMM was adopted as which international ISO standard?**

A) ISO/IEC 15408
B) ISO/IEC 18045
C) ISO/IEC 27001
D) ISO/IEC 21827 ✅

> **Explanation:** **ISO/IEC 21827** is the international standard
> based on SSE-CMM — published as ISO/IEC 21827:2002 (first edition)
> and ISO/IEC 21827:2008 (current). ISO/IEC 15408 = Common Criteria.
> ISO/IEC 18045 = CEM (evaluation methodology). ISO/IEC 27001 = ISMS.
> Knowing which ISO number belongs to SSE-CMM is a common MCQ trap.

---

**Q5. The current version of SSE-CMM is:**

A) Version 1.1
B) Version 2.0
C) Version 3.0 ✅
D) Version 4.0

> **Explanation:** **SSE-CMM Version 3.0** is the current version —
> published in 2003 and adopted as ISO/IEC 21827:2008. Version 1.1
> was the first public release (1996). Version 2.0 was published in
> 1999. There is no Version 4.0. The version history: 1.1 (1996) →
> 2.0 (1999) → 3.0 (2003 — current).

---

**Q6. SSE-CMM has a two-dimensional architecture. The two
dimensions are:**

A) Technical Dimension (tools) and Process Dimension (activities)
B) Domain Dimension (WHAT is done) and Capability Dimension
   (HOW WELL it is done) ✅
C) Security Dimension (controls) and Management Dimension (governance)
D) Operational Dimension (daily tasks) and Strategic Dimension
   (planning)

> **Explanation:** SSE-CMM's two dimensions are: **Domain Dimension
> = WHAT is done** — covering Process Areas (PAs) and Base Practices
> (BPs) — the specific security engineering activities. **Capability
> Dimension = HOW WELL it is done** — covering Capability Levels
> (1–5) and Generic Practices (GPs) — measuring process maturity.
> This two-dimensional structure is the architectural foundation
> of SSE-CMM.

---

**Q7. How many total Process Areas does SSE-CMM define and how
are they categorized?**

A) 11 total — all Security Process Areas
B) 20 total — 11 Security + 5 Project + 4 Organization
C) 22 total — 11 Security + 6 Project + 5 Organization ✅
D) 25 total — 15 Security + 5 Project + 5 Organization

> **Explanation:** SSE-CMM defines exactly **22 Process Areas**
> in three categories: **11 Security PAs (PA01–PA11)**, **6 Project
> PAs (PA12–PA17)**, and **5 Organization PAs (PA18–PA22)**. The
> 11 Security PAs are the core — they define what security
> engineering organizations must do. Project and Organization PAs
> provide supporting practices.

---

**Q8. Which of the following is one of the 11 Security Process
Areas in SSE-CMM?**

A) Manage Project Risk (PA14)
B) Define Organization's Systems Engineering Process (PA18)
C) Assess Security Risk (PA03) ✅
D) Ensure Quality (PA12)

> **Explanation:** **PA03 = Assess Security Risk** is one of the
> 11 Security Process Areas (PA01–PA11). PA14 (Manage Project Risk)
> is a Project PA. PA18 (Define Organization's Systems Engineering
> Process) is an Organization PA. PA12 (Ensure Quality) is also a
> Project PA. Only PA01–PA11 are the core security-focused process
> areas.

---

**Q9. Which Security Process Area focuses on developing
evidence-based arguments that a system is secure?**

A) PA03 — Assess Security Risk
B) PA05 — Assess Vulnerability
C) PA06 — Build Assurance Argument ✅
D) PA11 — Verify and Validate Security

> **Explanation:** **PA06 = Build Assurance Argument** — developing
> evidence-based arguments that the system meets its security
> requirements and is trustworthy. PA03 assesses security risks.
> PA05 identifies and assesses vulnerabilities. PA11 verifies and
> validates that security requirements are met. Build Assurance
> Argument is distinct — it creates the formal argument for why
> the system can be trusted.

---

**Q10. Which Security Process Area involves defining and
documenting security requirements for a system?**

A) PA01 — Administer Security Controls
B) PA07 — Coordinate Security
C) PA10 — Specify Security Needs ✅
D) PA08 — Monitor Security Posture

> **Explanation:** **PA10 = Specify Security Needs** — defining
> and documenting the security requirements that the system must
> meet. PA01 manages and administers security controls. PA07
> coordinates security activities across the project. PA08 monitors
> and manages the ongoing security posture. Specifying needs comes
> early in the lifecycle — before building or assessing security.

---

**Q11. How many Capability Levels does SSE-CMM define and what
is the starting level?**

A) 6 levels — starting at Level 0 (Non-Existent)
B) 5 levels — starting at Level 0 (Incomplete)
C) 5 levels — starting at Level 1 (Performed Informally) ✅
D) 4 levels — starting at Level 1 (Initial)

> **Explanation:** SSE-CMM defines **5 Capability Levels starting
> at Level 1** — NOT Level 0. This is a critical distinction from
> COBIT's maturity model (which starts at 0). **Level 1 = Performed
> Informally** — even informal, ad hoc performance of base practices
> qualifies as Level 1. Level 0 does not exist in SSE-CMM.

---

**Q12. SSE-CMM Capability Level 1 is named "Performed Informally."
This means:**

A) No security engineering processes exist at all
B) Base Practices are performed but may be incomplete, inconsistent,
   or depend on individual skill rather than defined processes ✅
C) Processes are planned and tracked at the project level
D) The organization has defined security engineering processes
   organization-wide

> **Explanation:** **Level 1 = Performed Informally** means Base
> Practices ARE being performed — but the execution is ad hoc,
> reactive, and dependent on individual knowledge and effort
> ("individual heroics"). There is no formal planning, tracking,
> or standardization. The key point: Level 1 is NOT "doing nothing"
> — it IS performing security engineering, just informally.

---

**Q13. Which SSE-CMM Capability Level is characterized by a
standard organizational process being defined and used by all
projects?**

A) Level 2 — Planned and Tracked
B) Level 3 — Well Defined ✅
C) Level 4 — Quantitatively Controlled
D) Level 5 — Continuously Improving

> **Explanation:** **Level 3 = Well Defined** — a standard
> organizational process is defined, documented, and used consistently
> across all projects (with allowed tailoring). Level 2 (Planned
> and Tracked) applies discipline at the project level but processes
> may vary between projects. Level 3 brings organizational
> standardization — the same process is used organization-wide.

---

**Q14. An organization collects quantitative measures from its
security engineering processes and uses statistical methods to
manage process performance. This describes which SSE-CMM
Capability Level?**

A) Level 2 — Planned and Tracked
B) Level 3 — Well Defined
C) Level 4 — Quantitatively Controlled ✅
D) Level 5 — Continuously Improving

> **Explanation:** **Level 4 = Quantitatively Controlled** —
> quantitative measures are collected from processes and used to
> statistically manage and control process performance. Variation
> is understood and managed. This requires sophisticated measurement
> infrastructure. Level 3 defines the process. Level 4 measures and
> controls it. Level 5 then uses that data to continuously improve.

---

**Q15. The highest SSE-CMM Capability Level — Level 5 — is
named and characterized by:**

A) Quantitatively Controlled — statistical process management
B) Well Defined — organizational standard process
C) Continuously Improving — proactive improvement using
   quantitative data ✅
D) Optimized — elimination of all process defects

> **Explanation:** **Level 5 = Continuously Improving** —
> the organization uses quantitative performance data to
> proactively identify and implement process improvements.
> New technologies are evaluated. Defect causes are systematically
> eliminated. Process improvement is an organizational discipline.
> "Optimized" is the Level 5 name in COBIT 4.1 — not SSE-CMM.
> SSE-CMM's Level 5 is specifically "Continuously Improving."

---

**Q16. In SSE-CMM, the difference between a Process Area (PA)
and a Base Practice (BP) is:**

A) PA = a specific activity / BP = a cluster of related activities
B) PA = a cluster of related practices achieving a goal /
   BP = a specific activity within that PA ✅
C) PA = an organizational level concept / BP = a project level concept
D) PA and BP are different names for the same concept

> **Explanation:** **PA (Process Area)** = a higher-level grouping
> of related practices that together achieve a specific security
> engineering goal (e.g., PA03 = Assess Security Risk). **BP (Base
> Practice)** = a specific individual activity within that PA (e.g.,
> BP.03.01 = Identify security risks). Multiple BPs make up each PA.
> Think PA = chapter, BP = section within that chapter.

---

**Q17. Generic Practices (GPs) in SSE-CMM belong to which
dimension and serve what purpose?**

A) Domain Dimension — define what security engineering activities
   must be performed
B) Capability Dimension — define HOW WELL processes are performed
   across all Process Areas ✅
C) Project Dimension — define project management activities
D) Organization Dimension — define organizational structure

> **Explanation:** **Generic Practices (GPs) belong to the Capability
> Dimension** — they apply to ALL Process Areas and define HOW WELL
> each process is performed at each capability level. GPs address
> planning, tracking, verifying, defining, measuring, and improving
> processes. Base Practices (BPs) belong to the Domain Dimension —
> they define WHAT specific activities are performed.

---

**Q18. A key fundamental difference between Common Criteria
(ISO/IEC 15408) and SSE-CMM (ISO/IEC 21827) is:**

A) Common Criteria evaluates organizations — SSE-CMM evaluates
   products
B) Both evaluate products using the same methodology
C) Common Criteria evaluates products (TOE) — SSE-CMM evaluates
   organizations' security engineering processes ✅
D) SSE-CMM is mandatory — Common Criteria is voluntary

> **Explanation:** **Critical distinction:**
> **Common Criteria = evaluates PRODUCTS** (the Target of Evaluation —
> what security features does this specific system have?)
> **SSE-CMM = evaluates ORGANIZATIONS** (how capable are this
> organization's security engineering processes?)
> They are complementary — a product can be CC-evaluated AND the
> organization that built it can be SSE-CMM-appraised. Neither is
> mandatory over the other.

---

**Q19. A government agency wants to ensure that a defense
contractor has mature, reliable security engineering processes
before awarding a contract. Which framework is most directly
applicable?**

A) Common Criteria — to evaluate the security of delivered products
B) ISO/IEC 27001 — to certify the contractor's ISMS
C) SSE-CMM — to evaluate the contractor's security engineering
   process capability ✅
D) PCI DSS — to validate the contractor's financial data security

> **Explanation:** **SSE-CMM** is specifically designed for this
> use case — evaluating the **security engineering process capability**
> of organizations building secure systems. Government agencies can
> require minimum SSE-CMM capability levels in contracts. Common
> Criteria would evaluate the final product. ISO 27001 certifies
> the ISMS. PCI DSS is for payment card data — irrelevant here.

---

**Q20. The formal appraisal method used to assess an
organization's SSE-CMM capability level is called:**

A) SCAMPI — Standard CMMI Appraisal Method
B) SSAM — SSE-CMM Appraisal Method ✅
C) SSAE — Statement on Standards for Attestation Engagements
D) SLAM — Security Level Assessment Method

> **Explanation:** **SSAM = SSE-CMM Appraisal Method** — the formal
> method for assessing an organization's SSE-CMM capability levels.
> Conducted by trained SSE-CMM appraisers, SSAM involves interviews,
> document reviews, and process observations. SCAMPI is CMMI's
> equivalent appraisal method. SSAE (not SLAM) is AICPA's attestation
> standard for SOC reports — completely different domain.

---

**Q21. Which of the following is a Project Process Area (PA12–PA17)
in SSE-CMM?**

A) Assess Security Risk (PA03)
B) Monitor Security Posture (PA08)
C) Manage Configurations (PA13) ✅
D) Provide Ongoing Skills and Knowledge (PA22)

> **Explanation:** **PA13 = Manage Configurations** — a Project
> Process Area (PA12–PA17) that covers controlling and managing
> changes to system configurations within a project. PA03 and PA08
> are Security PAs (PA01–PA11). PA22 is an Organization PA
> (PA18–PA22). The Project PAs focus on project management
> practices that support security engineering.

---

**Q22. Which Organization Process Area in SSE-CMM specifically
addresses continuously improving the organization's systems
engineering process?**

A) PA18 — Define Organization's Systems Engineering Process
B) PA19 — Improve Organization's Systems Engineering Process ✅
C) PA20 — Manage Product Line Evolution
D) PA22 — Provide Ongoing Skills and Knowledge

> **Explanation:** **PA19 = Improve Organization's Systems Engineering
> Process** — focused on continuously improving the engineering
> process at the organizational level. PA18 defines (establishes)
> the standard process. PA19 improves it. PA20 manages product line
> evolution. PA22 ensures staff have current security engineering
> skills and knowledge. PA18 and PA19 work together — define then
> continuously improve.

---

**Q23. SSE-CMM pilots were conducted to serve which primary
purpose?**

A) Train security engineers in SSE-CMM capability level assessment
B) Market SSE-CMM to government agencies and defense contractors
C) Validate that SSE-CMM accurately describes real-world security
   engineering practices before ISO adoption ✅
D) Replace Common Criteria evaluations with SSE-CMM appraisals

> **Explanation:** **SSE-CMM pilots validated the model** — real
> organizations tested whether SSE-CMM's process areas and capability
> levels accurately reflected actual security engineering practice.
> Pilots included development organizations, evaluation organizations,
> government acquisition agencies, and service providers. Results
> directly led to refinements in v2.0 and v3.0 and gave the model
> credibility for ISO/IEC 21827 adoption.

---

**Q24. SSE-CMM addresses which core discipline that spans the
entire system lifecycle from concept to retirement?**

A) Software Quality Assurance — ensuring software meets requirements
B) Systems Security Engineering — designing and building secure
   systems throughout the lifecycle ✅
C) IT Service Management — delivering and supporting IT services
D) Information Security Management — managing an organization's ISMS

> **Explanation:** **SSE (Systems Security Engineering)** is the
> discipline SSE-CMM measures — a disciplined approach to designing,
> building, and operating trustworthy secure systems throughout the
> **entire system lifecycle** (concept → development → production →
> utilization → support → retirement). It is NOT just about ISMS
> (ISO 27001) or IT service delivery (ITIL) — it is about engineering
> security into systems from the ground up.

---

**Q25. In SSE-CMM, the relationship between the Domain Dimension
and Capability Dimension creates what structure?**

A) A linear process flow from basic to advanced security activities
B) A hierarchical tree of security requirements
C) A two-dimensional matrix where each PA is assessed at each
   Capability Level ✅
D) A circular improvement cycle similar to PDCA

> **Explanation:** The **two-dimensional matrix** is the fundamental
> structural result of combining the Domain Dimension (PAs as rows)
> with the Capability Dimension (Capability Levels as columns). Each
> cell in the matrix represents a PA assessed at a specific capability
> level — using Generic Practices (GPs) to determine how well that
> PA is performed. This matrix structure enables granular assessment
> of an organization's security engineering capability.

---

**Q26. Comparing SSE-CMM Capability Levels to COBIT's maturity
model, which key structural difference exists?**

A) SSE-CMM has more levels (7) than COBIT (5)
B) SSE-CMM starts at Level 1 — COBIT 4.1 maturity starts at Level 0 ✅
C) SSE-CMM uses letters (A–E) — COBIT uses numbers (0–5)
D) SSE-CMM and COBIT have identical level structures and names

> **Explanation:** A key structural difference: **SSE-CMM starts at
> Level 1** (Performed Informally — the process exists but is ad hoc)
> while **COBIT 4.1's maturity model starts at Level 0** (Non-Existent
> — complete absence of process). Both use 5 meaningful levels of
> capability/maturity and both use numbers. The starting point
> difference means "no process" in COBIT = Level 0, while the lowest
> performing level in SSE-CMM = Level 1.

---

**Q27. Which Security Process Area in SSE-CMM covers ongoing
monitoring and management of a system's security posture
throughout its operational life?**

A) PA10 — Specify Security Needs
B) PA06 — Build Assurance Argument
C) PA11 — Verify and Validate Security
D) PA08 — Monitor Security Posture ✅

> **Explanation:** **PA08 = Monitor Security Posture** — covering
> ongoing monitoring and management of the security posture of a
> system during its operational lifecycle. PA10 specifies security
> requirements (early lifecycle). PA06 builds the assurance argument.
> PA11 verifies and validates security requirements are met (testing
> phase). PA08 is the ongoing operational monitoring activity.

---

**Q28. An organization's security engineering processes are
planned before execution and results are tracked and verified —
but the process may differ between different projects. This
describes which SSE-CMM Capability Level?**

A) Level 1 — Performed Informally
B) Level 2 — Planned and Tracked ✅
C) Level 3 — Well Defined
D) Level 4 — Quantitatively Controlled

> **Explanation:** **Level 2 = Planned and Tracked** — processes
> are planned, performed according to plan, tracked against plans,
> and results verified. The key distinguishing characteristic: this
> discipline is applied at the **project level** and may vary
> between projects. **Level 3 (Well Defined)** adds organizational
> standardization — the same process used across all projects.
> The "varies between projects" clue points to Level 2.

---

**Q29. SSE-CMM's ISO/IEC 21827 standard addresses a different
subject matter from ISO/IEC 15408 (Common Criteria). Which
statement correctly contrasts their subject matter?**

A) ISO/IEC 21827 evaluates product security features —
   ISO/IEC 15408 evaluates process maturity
B) ISO/IEC 21827 measures security engineering process capability —
   ISO/IEC 15408 specifies IT product security evaluation criteria ✅
C) Both ISO/IEC 21827 and 15408 evaluate organizations using
   5-level rating scales
D) ISO/IEC 21827 is for software development — ISO/IEC 15408 is
   for hardware security

> **Explanation:** **ISO/IEC 21827 (SSE-CMM)** = measures the
> **capability of organizations' security engineering processes**
> — how well does this organization build secure systems?
> **ISO/IEC 15408 (Common Criteria)** = specifies **criteria for
> evaluating the security of IT products** — how secure is this
> specific product?
> They operate in complementary but distinct domains — one
> evaluates the builder's process, the other evaluates the
> built product.

---

**Q30. Which combination of SSE-CMM facts is entirely correct?**

A) SSE-CMM by NIST / 20 PAs total / 5 Security PAs / Level 0 =
   starting level / ISO/IEC 15408
B) SSE-CMM by ISSEA / 22 PAs total / 11 Security PAs / Level 1 =
   starting level / ISO/IEC 21827 ✅
C) SSE-CMM by NSA / 22 PAs total / 11 Security PAs / Level 0 =
   starting level / ISO/IEC 21827
D) SSE-CMM by ISSEA / 22 PAs total / 11 Security PAs / Level 1 =
   starting level / ISO/IEC 15408

> **Explanation:** The fully correct combination is:
> **SSE-CMM by ISSEA** ✅ (NSA initiated but ISSEA developed it)
> **22 PAs total** ✅ (11 Security + 6 Project + 5 Organization)
> **11 Security PAs** ✅ (PA01–PA11)
> **Level 1 = starting level** ✅ (NOT Level 0 — starts at 1)
> **ISO/IEC 21827** ✅ (NOT 15408 — that is Common Criteria)
> Option C fails because NSA initiated (not developed) — ISSEA
> developed it — and Level 0 is not the starting level.
> Option D fails because ISO/IEC 15408 = Common Criteria, not
> SSE-CMM. Option A fails on almost every point.

---

## 📊 Quick Answer Key

| Q | Ans | Q | Ans | Q | Ans |
|---|---|---|---|---|---|
| 1 | B | 11 | C | 21 | C |
| 2 | D | 12 | B | 22 | B |
| 3 | B | 13 | B | 23 | C |
| 4 | D | 14 | C | 24 | B |
| 5 | C | 15 | C | 25 | C |
| 6 | B | 16 | B | 26 | B |
| 7 | C | 17 | B | 27 | D |
| 8 | C | 18 | C | 28 | B |
| 9 | C | 19 | C | 29 | B |
| 10 | C | 20 | B | 30 | B |

---

## 🎯 Topic Coverage Map

| Topic | MCQs Covered |
|---|---|
| SSE-CMM full name + ISSEA | Q1 |
| NSA initiated SSE-CMM — 1993 | Q2 |
| Based on SW-CMM | Q3 |
| ISO/IEC 21827 — SSE-CMM standard | Q4 |
| Current version — v3.0 | Q5 |
| Two dimensions — Domain + Capability | Q6 |
| 22 total PAs — 11+6+5 | Q7 |
| Security PAs PA01–PA11 | Q8 |
| PA06 — Build Assurance Argument | Q9 |
| PA10 — Specify Security Needs | Q10 |
| 5 levels — starts at Level 1 not 0 | Q11 |
| Level 1 — Performed Informally | Q12 |
| Level 3 — Well Defined | Q13 |
| Level 4 — Quantitatively Controlled | Q14 |
| Level 5 — Continuously Improving | Q15 |
| PA vs BP distinction | Q16 |
| Generic Practices — Capability Dimension | Q17 |
| SSE-CMM vs Common Criteria | Q18 |
| Government procurement use case | Q19 |
| SSAM — appraisal method | Q20 |
| Project PAs — PA13 Manage Configurations | Q21 |
| Organization PA — PA19 Improve Process | Q22 |
| SSE-CMM Pilots — purpose | Q23 |
| SSE — Systems Security Engineering | Q24 |
| Two-dimensional matrix structure | Q25 |
| SSE-CMM Level 1 vs COBIT Level 0 | Q26 |
| PA08 — Monitor Security Posture | Q27 |
| Level 2 — Planned and Tracked | Q28 |
| ISO/IEC 21827 vs ISO/IEC 15408 | Q29 |
| Combined SSE-CMM facts | Q30 |

---