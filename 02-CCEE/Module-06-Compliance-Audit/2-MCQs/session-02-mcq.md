# 🎯 MCQ — Session 02: Security Evaluation & Assurance

> 30 MCQs | Raw Fundamentals | 4 Options Each | Full Explanations
> Covers: Security Evaluation, TCSEC, ITSEC, Common Criteria, EAL Levels,
> Evaluation Process, Evaluation Phases, CEM + Extra Notes

---

## MCQ Set

---

**Q1. Security Evaluation is best defined as:**

A) A process of scanning an IT product for known vulnerabilities
B) A formal structured assessment of whether an IT product meets its
   defined security requirements ✅
C) A review of an organization's compliance with regulations
D) A penetration test conducted by the vendor on their own product

> **Explanation:** Security Evaluation is a **formal, structured process**
> performed by an **independent accredited body** to assess whether a product
> meets its defined security requirements. A describes vulnerability scanning.
> C describes compliance audit (Session 01). D is invalid — vendors cannot
> evaluate their own products.

---

**Q2. What is the term used for the IT product or system that is being
evaluated in a Common Criteria evaluation?**

A) Security Target (ST)
B) Protection Profile (PP)
C) Target of Evaluation (TOE) ✅
D) Evaluation Assurance Level (EAL)

> **Explanation:** **TOE = Target of Evaluation** — the specific IT product,
> component, or system being evaluated. ST is the document describing security
> claims for the TOE. PP is a generic requirements template. EAL is the
> resulting rating.

---

**Q3. TCSEC is also commonly known as:**

A) The Green Book
B) The Red Book
C) The Blue Book
D) The Orange Book ✅

> **Explanation:** **TCSEC = Orange Book** — named after its literal orange
> cover. It is part of the US DoD Rainbow Series of security standards where
> each book has a different color cover. This nickname appears very frequently
> in MCQs.

---

**Q4. Which organization published the TCSEC (Orange Book)?**

A) ISO/IEC
B) NIST
C) US Department of Defense (DoD) ✅
D) European Commission

> **Explanation:** **TCSEC was published by the US DoD** — specifically under
> DoD standard 5200.28-STD. NIST publishes SP 800-series documents. ISO/IEC
> publishes Common Criteria. The European Commission was involved in ITSEC.

---

**Q5. In TCSEC, which class represents the HIGHEST level of security
assurance?**

A) B3
B) C2
C) D
D) A1 ✅

> **Explanation:** **A1 = Verified Design** is the highest TCSEC class —
> requires formal mathematical verification of the design. The order from
> lowest to highest is: D → C1 → C2 → B1 → B2 → B3 → A1. D is the
> lowest (minimal protection).

---

**Q6. In TCSEC, which class represents NO security — failing all higher
requirements?**

A) C1
B) D ✅
C) B1
D) E0

> **Explanation:** **Class D = Minimal Protection** — assigned to systems that
> fail to meet requirements of any higher class. It literally means no
> meaningful security. E0 belongs to ITSEC, not TCSEC.

---

**Q7. ITSEC was developed by which group of countries?**

A) USA, Canada, Australia, UK
B) France, Germany, Netherlands, UK ✅
C) USA, Germany, Japan, France
D) UK, Japan, Canada, Australia

> **Explanation:** **ITSEC was a joint European effort** by France, Germany,
> Netherlands, and the United Kingdom. It was Europe's answer to the US TCSEC
> standard and covered confidentiality, integrity, AND availability — unlike
> TCSEC which focused only on confidentiality.

---

**Q8. A key difference between TCSEC and ITSEC in terms of security focus is:**

A) TCSEC covers CIA; ITSEC covers only Confidentiality
B) ITSEC covers CIA; TCSEC covers only Confidentiality ✅
C) Both cover only Confidentiality
D) Both cover the full CIA triad equally

> **Explanation:** **TCSEC focused primarily on Confidentiality** — it was
> designed for US military/government classified information. **ITSEC expanded
> to cover all three — Confidentiality, Integrity, and Availability.** Common
> Criteria also covers all three, inheriting this from ITSEC.

---

**Q9. The current international standard for IT security evaluation is:**

A) TCSEC
B) ITSEC
C) Common Criteria (ISO/IEC 15408) ✅
D) CEM (ISO/IEC 18045)

> **Explanation:** **Common Criteria = ISO/IEC 15408** is the current
> international standard. TCSEC and ITSEC have both been superseded by CC.
> CEM (ISO/IEC 18045) is the evaluation methodology standard — the companion
> to CC, not CC itself.

---

**Q10. Common Criteria is structured into how many parts?**

A) Two
B) Three ✅
C) Four
D) Five

> **Explanation:** CC has **three parts**: Part 1 = Introduction and General
> Model, Part 2 = Security Functional Requirements (SFR), Part 3 = Security
> Assurance Requirements (SAR). This structure is a common MCQ question.

---

**Q11. Security Functional Requirements (SFR) in Common Criteria answer
which question?**

A) How confident are we that the product works correctly?
B) What depth of evaluation was performed?
C) What security features must the product have? ✅
D) Who performed the evaluation?

> **Explanation:** **SFR = Security Functional Requirements** answer "What
> does the product DO?" — they define the security features and functions the
> product must implement. SAR answers "How confident are we?" — the depth and
> rigor of evaluation.

---

**Q12. Security Assurance Requirements (SAR) in Common Criteria answer
which question?**

A) What security features must the product implement?
B) How confident are we that the product correctly implements its security
   features? ✅
C) What vulnerabilities exist in the product?
D) Which country certified the product?

> **Explanation:** **SAR = Security Assurance Requirements** answer "How
> confident are we it does it RIGHT?" — they define the evaluation rigor
> required. SFR defines the features. SAR defines how thoroughly those
> features must be verified.

---

**Q13. EAL stands for:**

A) Evaluated Assurance List
B) Evaluation Assessment Label
C) Evaluation Assurance Level ✅
D) External Audit Level

> **Explanation:** **EAL = Evaluation Assurance Level** — the rating from 1
> to 7 that indicates the depth and rigor of the CC evaluation. Higher number
> = more rigorous evaluation. This abbreviation appears in almost every
> security evaluation MCQ.

---

**Q14. Which EAL level is described as "Functionally Tested" — the lowest
level of evaluation?**

A) EAL2
B) EAL3
C) EAL4
D) EAL1 ✅

> **Explanation:** **EAL1 = Functionally Tested** — the lowest assurance level.
> It involves basic functional testing only and is used for low-risk commercial
> products where some assurance is needed but threats are not serious. EAL2 =
> Structurally Tested. EAL3 = Methodically Tested and Checked.

---

**Q15. Which EAL level is the MOST COMMON level for commercial security
products?**

A) EAL2
B) EAL3
C) EAL4 ✅
D) EAL5

> **Explanation:** **EAL4 = Methodically Designed, Tested and Reviewed** is
> the most common commercial evaluation level. It is the highest level
> achievable without fundamentally redesigning a product specifically for
> evaluation. Most enterprise firewalls, operating systems, and security
> products target EAL4.

---

**Q16. Which EAL level requires formal mathematical verification of the
design — the highest assurance level?**

A) EAL5
B) EAL6
C) EAL7 ✅
D) EAL4

> **Explanation:** **EAL7 = Formally Verified Design and Tested** — requires
> complete formal mathematical proof of the design and implementation. It is
> used for extreme security environments such as military and classified
> government systems. EAL6 = Semiformally Verified. EAL5 = Semiformally
> Designed.

---

**Q17. A higher EAL rating means the product has MORE security features
than a lower EAL product. This statement is:**

A) True — higher EAL means more features are built in
B) True — EAL7 products have all security features
C) False — higher EAL means more rigorous evaluation, not more features ✅
D) False — EAL only measures the number of vulnerabilities found

> **Explanation:** This is a **critical concept and common MCQ trap**. A
> higher EAL means the **same features are evaluated MORE rigorously and
> deeply** — not that the product has more features. Two products can have
> the same features but different EAL ratings based on how thoroughly they
> were evaluated.

---

**Q18. What is the name of the accredited independent laboratory that
performs Common Criteria evaluations?**

A) Certification Body
B) National Scheme
C) Common Criteria Testing Laboratory (CCTL) ✅
D) Evaluation Authority Board

> **Explanation:** **CCTL = Common Criteria Testing Laboratory** — the
> accredited independent lab that actually evaluates the TOE. The Certification
> Body reviews the CCTL's findings and issues the certificate. The National
> Scheme oversees the entire process in a given country.

---

**Q19. In a Common Criteria evaluation, who issues the final certificate after
reviewing the evaluation results?**

A) The Developer/Vendor
B) The CCTL (Testing Laboratory)
C) The Certification Body ✅
D) ISO/IEC

> **Explanation:** The **Certification Body** reviews the Evaluation Technical
> Report (ETR) produced by the CCTL and issues the formal CC certificate if
> the evaluation passes. The CCTL evaluates but does not certify. The vendor
> submits but does not certify. ISO/IEC publishes the standard but does not
> issue individual product certificates.

---

**Q20. The document produced by a CCTL summarizing the results of a Common
Criteria evaluation is called:**

A) Security Target (ST)
B) Protection Profile (PP)
C) Certification Report
D) Evaluation Technical Report (ETR) ✅

> **Explanation:** **ETR = Evaluation Technical Report** — produced by the
> CCTL to summarize all evaluation findings, work done, and conclusions. The
> Certification Body then reviews the ETR to decide whether to issue a
> certificate. ST is the developer's document. PP is the generic requirements
> template.

---

**Q21. A Protection Profile (PP) differs from a Security Target (ST) in that:**

A) PP is product-specific; ST is generic for a category of products
B) PP is created by the developer; ST is created by the community
C) PP is generic for a product category; ST is specific to one product ✅
D) PP and ST are different names for the same document

> **Explanation:** **PP = generic** requirements for a category of products
> (e.g., all firewalls). **ST = specific** claims for one particular product
> (e.g., this specific firewall version). PP is created by industry/community
> groups. ST is created by the developer/vendor for their specific TOE.

---

**Q22. Think of a Protection Profile (PP) as a job description and a Security
Target (ST) as a resume. Based on this analogy, which statement is correct?**

A) PP describes one specific product; ST describes a product category
B) PP sets generic requirements; ST is the product's specific claims
   against those requirements ✅
C) PP is created by the evaluator; ST is created by the certifier
D) PP comes after ST in the evaluation process

> **Explanation:** The analogy holds perfectly — **PP = job description**
> (what any product in this category should do), **ST = resume** (what this
> specific product claims it does). ST is written by the vendor to describe
> their specific TOE and its security claims.

---

**Q23. CEM stands for and is defined by which ISO standard?**

A) Common Evaluation Model — ISO/IEC 15408
B) Certified Evaluation Methodology — ISO/IEC 27001
C) Common Evaluation Methodology — ISO/IEC 18045 ✅
D) Cyber Evaluation Method — ISO/IEC 31000

> **Explanation:** **CEM = Common Evaluation Methodology = ISO/IEC 18045.**
> It defines HOW evaluators must conduct CC evaluations — ensuring consistency
> across different labs worldwide. CC itself is ISO/IEC 15408 and defines WHAT
> to evaluate. ISO/IEC 27001 is information security management. ISO 31000 is
> risk management.

---

**Q24. The relationship between CC (ISO/IEC 15408) and CEM (ISO/IEC 18045) is:**

A) CC defines HOW to evaluate; CEM defines WHAT to evaluate
B) CC defines WHAT to evaluate; CEM defines HOW to evaluate ✅
C) CC and CEM are two names for the same standard
D) CC is used only in the USA; CEM is used only in Europe

> **Explanation:** **CC = WHAT** (requirements — what the product must do and
> how rigorously it must be evaluated). **CEM = HOW** (methodology — the
> specific procedures evaluators must follow). They are companion standards —
> CC without CEM would result in inconsistent evaluations across labs.

---

**Q25. The CCRA (Common Criteria Recognition Arrangement) primarily achieves:**

A) Standardization of EAL level naming across countries
B) Mutual recognition of CC certificates across member countries ✅
C) Mandatory re-evaluation of products in each member country
D) Centralized evaluation at a single global CCTL

> **Explanation:** **CCRA = Mutual Recognition** — member countries agree to
> accept CC certificates issued by other member countries. This means a product
> evaluated once can be sold and trusted in all member countries without
> re-evaluation. This is what makes CC truly international.

---

**Q26. Which of the following correctly orders TCSEC classes from LOWEST to
HIGHEST security?**

A) A1 → B3 → B2 → B1 → C2 → C1 → D
B) D → C1 → C2 → B1 → B2 → B3 → A1 ✅
C) D → B1 → B2 → B3 → C1 → C2 → A1
D) C1 → C2 → D → B1 → B2 → B3 → A1

> **Explanation:** The correct ascending order is **D → C1 → C2 → B1 → B2
> → B3 → A1**. D is the lowest (no security). A1 is the highest (formal
> mathematical verification). The divisions go D (minimal) → C (discretionary)
> → B (mandatory) → A (verified).

---

**Q27. ITSEC uses assurance levels labeled E0 through E6. The equivalent
concept in Common Criteria is:**

A) TCSEC Classes D through A1
B) CC Parts 1 through 3
C) EAL1 through EAL7 ✅
D) SFR and SAR

> **Explanation:** **ITSEC's E0–E6 directly maps to CC's EAL1–EAL7** — both
> are 7-level assurance rating scales. ITSEC's E0 (lowest) corresponds roughly
> to EAL1. E6 (highest) corresponds roughly to EAL7. CC evolved the concept
> from ITSEC and formalized it internationally.

---

**Q28. During which phase of the CC evaluation process does the CCTL perform
independent penetration testing of the TOE?**

A) Initiation
B) Document Review
C) Development Analysis
D) Testing ✅

> **Explanation:** **Testing phase** is where the CCTL conducts independent
> functional tests, penetration tests, and vulnerability analysis on the actual
> TOE. Initiation = planning the evaluation. Document Review = reviewing ST and
> design docs. Development Analysis = reviewing architecture and design.

---

**Q29. Why must the CCTL (evaluating laboratory) be independent of the
developer whose product is being evaluated?**

A) To reduce the cost of evaluation
B) To ensure faster evaluation timelines
C) To ensure objectivity and make the evaluation trustworthy ✅
D) To comply with GDPR requirements

> **Explanation:** **Independence = Trustworthiness.** If developers evaluated
> their own products, they would have an obvious incentive to pass their own
> evaluation. An independent CCTL has no financial or organizational interest
> in the outcome — making the certificate meaningful and credible to buyers.

---

**Q30. Which of the following is the correct mapping of CC evaluation
participants to their roles?**

A) Developer → issues certificate / CCTL → evaluates / Certification Body
   → creates TOE
B) Developer → creates TOE / CCTL → evaluates independently / Certification
   Body → issues certificate ✅
C) Developer → evaluates TOE / CCTL → issues certificate / Certification
   Body → creates TOE
D) Developer → creates PP / CCTL → creates ST / Certification Body →
   evaluates TOE

> **Explanation:** The correct mapping is:
> **Developer** → creates the TOE and prepares documentation (ST)
> **CCTL** → independently evaluates the TOE and produces the ETR
> **Certification Body** → reviews the ETR and issues the CC certificate
> This chain of independence is fundamental to CC's credibility.

---

## 📊 Quick Answer Key

| Q | Ans | Q | Ans | Q | Ans |
|---|---|---|---|---|---|
| 1 | B | 11 | C | 21 | C |
| 2 | C | 12 | B | 22 | B |
| 3 | D | 13 | C | 23 | C |
| 4 | C | 14 | D | 24 | B |
| 5 | D | 15 | C | 25 | B |
| 6 | B | 16 | C | 26 | B |
| 7 | B | 17 | C | 27 | C |
| 8 | B | 18 | C | 28 | D |
| 9 | C | 19 | C | 29 | C |
| 10 | B | 20 | D | 30 | B |

---

## 🎯 Topic Coverage Map

| Topic | MCQs Covered |
|---|---|
| Security Evaluation — definition | Q1 |
| TOE | Q2 |
| TCSEC — Orange Book, DoD, Classes | Q3, Q4, Q5, Q6, Q26 |
| ITSEC — Countries, CIA focus | Q7, Q8 |
| TCSEC vs ITSEC security focus | Q8 |
| Common Criteria — current standard | Q9 |
| CC Structure — 3 parts | Q10 |
| SFR vs SAR | Q11, Q12 |
| EAL — abbreviation | Q13 |
| EAL levels — specific names & uses | Q14, Q15, Q16 |
| EAL misconception (features vs rigor) | Q17 |
| CCTL | Q18 |
| Certification Body | Q19 |
| ETR | Q20 |
| PP vs ST | Q21, Q22 |
| CEM — ISO 18045 | Q23 |
| CC vs CEM relationship | Q24 |
| CCRA — mutual recognition | Q25 |
| ITSEC E levels vs EAL | Q27 |
| Evaluation phases | Q28 |
| CCTL independence | Q29 |
| CC participants — full chain | Q30 |

---