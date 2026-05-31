# 🔍 MCQ Set — Session 10A

**Module:** Security Concepts — Ethical Hacking
**Coverage:** Security Evaluation Plan · Types of Ethical Hacks · Footprinting ·
Social Engineering in Recon · Traceroute · OSINT Framework · MITRE ATT&CK TA0043
**Total Questions:** 28
**Format:** Foundation + Fundamental + Basic Concepts only

---

## 📋 Table of Contents

- [Questions — Q1 to Q28](#questions)
- [Answers & Explanations](#answers--explanations)
- [Quick Answer Key](#quick-answer-key)
- [Topic Coverage Map](#topic-coverage-map)

---

## Questions

---

**Q1.** A Security Evaluation Plan (SEP) is signed and finalized at which point
in a penetration testing engagement?

- A) After the initial reconnaissance phase is complete
- B) Before a single packet is sent — prior to any testing activity
- C) After the first vulnerability is discovered and documented
- D) At the conclusion of testing — to formalize the findings

---

**Q2.** What is the "Get Out of Jail Free" card in the context of ethical hacking?

- A) A legal waiver that completely protects the tester from any criminal liability
- B) A short portable authorization letter carried by the tester during the engagement
- C) A document submitted to law enforcement before testing begins
- D) An internal policy exempting ethical hackers from following IT security rules

---

**Q3.** The PTES (Penetration Testing Execution Standard) framework consists of
how many phases?

- A) 4
- B) 5
- C) 6
- D) 7

---

**Q4.** NIST SP 800-115 — the US government standard for security testing —
defines how many phases in its methodology?

- A) 4
- B) 7
- C) 9
- D) 12

---

**Q5.** A penetration tester is given the target's source code, network diagrams,
and valid user credentials before testing begins. Which testing type is this?

- A) Black Box
- B) Red Box
- C) Grey Box
- D) White Box

---

**Q6.** Which penetration test type BEST simulates a scenario where an attacker
has obtained some internal information — such as a phishing victim's credentials —
and is described as MOST REALISTIC for modern threats?

- A) Black Box
- B) White Box
- C) Grey Box
- D) Red Team

---

**Q7.** What is the CORRECT definition of Footprinting in the context of ethical hacking?

- A) Analyzing malware on a compromised system after exploitation
- B) Scanning for open ports and services on target IP ranges
- C) Systematically collecting information about a target BEFORE any technical testing
- D) Documenting findings after a penetration test is completed

---

**Q8.** A penetration tester looks up the target organization's DNS records
using a third-party online tool, checks their LinkedIn company page, and
searches Shodan for their IP ranges. Which type of footprinting is this?

- A) Active Footprinting
- B) Hybrid Footprinting
- C) Passive Footprinting
- D) Enumeration

---

**Q9.** During footprinting, a tester sends ping requests to the target's web
server to check if it responds. This activity is BEST classified as:

- A) Passive Footprinting — pings are safe and non-invasive
- B) Active Footprinting — packets directly reach the target's systems
- C) OSINT — ping data is publicly available information
- D) Passive Footprinting — no vulnerability is being exploited

---

**Q10.** Certificate Transparency logs are described as a "goldmine for recon"
because they allow a tester to:

- A) View all SSL/TLS connections made by a target's employees
- B) Read the private keys used in a target's SSL certificates
- C) Find subdomains and servers that have ever had a certificate issued
- D) Intercept encrypted HTTPS traffic in real time

---

**Q11.** Which website is specifically used to search Certificate Transparency
logs for subdomains?

- A) shodan.io
- B) crt.sh
- C) dnsdumpster.com
- D) exploit-db.com

---

**Q12.** A security tester analyzes a company's LinkedIn page and notices that
50 of their engineers list "Palo Alto Networks" in their skills section. What
intelligence does this MOST directly reveal?

- A) The organization's physical security posture
- B) The firewall or network security technology the organization is likely using
- C) The number of employees in the security team
- D) The organization's budget for cybersecurity tools

---

**Q13.** A job posting from the target organization reads: "Seeking Senior Splunk
Administrator." What intelligence does this provide to a footprinting analyst?

- A) The target organization is planning to switch from Splunk to a competitor
- B) The target organization uses Splunk as their SIEM — and may currently lack expertise
- C) The target organization has an open vulnerability in their Splunk installation
- D) The target organization is hiring for a penetration testing role

---

**Q14.** Traceroute works by exploiting which specific field in the IP packet
header?

- A) Protocol field
- B) Source IP address field
- C) TTL (Time To Live) field
- D) Checksum field

---

**Q15.** When a router receives a packet and the TTL value reaches zero after
decrementing, what does the router send back to the source?

- A) TCP RST (Reset) packet
- B) ICMP Time Exceeded message
- C) TCP SYN-ACK packet
- D) ARP Reply packet

---

**Q16.** A tester runs a standard Linux `traceroute` to a target and notices
that hops 6, 7, and 8 all show `* * *` (asterisks) with no response. What does
this MOST LIKELY indicate?

- A) The target server is offline and not responding
- B) A firewall or router is blocking ICMP packets at that network segment
- C) The tester's internet connection is experiencing packet loss
- D) The traceroute has reached the target and completed successfully

---

**Q17.** Which traceroute variant uses TCP SYN packets instead of ICMP, making
it MORE useful for real-world footprinting through firewalls?

- A) `tracert` (Windows)
- B) `mtr` (My TraceRoute)
- C) `tcptraceroute` / `traceroute -T`
- D) Standard `traceroute` (Linux UDP mode)

---

**Q18.** In the context of OSINT, what does "Open Source" actually mean?

- A) Information gathered from open-source software projects only
- B) Information collected using free and open-source security tools
- C) Publicly accessible information — no hacking or authorization required to view
- D) Information shared between government intelligence agencies

---

**Q19.** Which of the following Google Dorking operators limits search results
to a specific domain?

- A) `inurl:`
- B) `filetype:`
- C) `intitle:`
- D) `site:`

---

**Q20.** A penetration tester uses the Google Dork:
`intitle:"index of" site:targetcompany.com`
What is this dork designed to find?

- A) The target's login and admin portal pages
- B) Directory listing pages — which may expose sensitive files
- C) Pages containing the word "password" in the body text
- D) All subdomains of the target domain

---

**Q21.** The Google Hacking Database (GHDB) — a repository of pre-built
Google Dorks organized by category — is maintained at which website?

- A) shodan.io
- B) osintframework.com
- C) exploit-db.com/google-hacking-database
- D) haveibeenpwned.com

---

**Q22.** The OSINT Framework tool at osintframework.com organizes OSINT tools
by which primary organizing principle?

- A) By tool cost (free vs commercial)
- B) By attacker skill level required
- C) By the type of data being sought (username, IP, email, etc.)
- D) By the phase of the penetration test

---

**Q23.** Which MITRE ATT&CK Tactic ID covers ALL reconnaissance techniques —
including active scanning, OSINT gathering, and social media intelligence?

- A) TA0001 (Initial Access)
- B) TA0007 (Discovery)
- C) TA0043 (Reconnaissance)
- D) TA0010 (Exfiltration)

---

**Q24.** According to the MITRE ATT&CK framework, which technique ID maps
specifically to gathering subdomain intelligence from Certificate Transparency logs?

- A) T1595.001 — Active Scanning: IP Blocks
- B) T1596.003 — Search Technical Databases: Digital Certificates
- C) T1590.002 — Gather Victim Network Info: DNS
- D) T1593.001 — Search Open Source: Social Media

---

**Q25.** In 2024, a Hong Kong company transferred a large sum of money after
attackers used which AI-powered technique to impersonate the company's CFO on
a video call?

- A) AI-generated phishing email with the CFO's writing style
- B) Voice cloning of the CFO using a 30-second audio sample
- C) Deepfake video of the CFO on a real-time video call
- D) Credential stuffing using the CFO's leaked password

---

**Q26.** A defender wants to reduce their organization's exposure discovered
through OSINT. They run all standard recon tools against their OWN organization
to discover what attackers can see. What is this practice called?

- A) Threat Intelligence Gathering
- B) Vulnerability Assessment
- C) Attack Surface Management (ASM)
- D) Security Information and Event Management (SIEM)

---

**Q27.** Which of the following correctly describes the role of DATA BROKERS
as an OSINT threat in 2026?

- A) Criminal organizations that sell stolen credit card data on the dark web
- B) Companies that LEGALLY collect, aggregate, and sell personal data —
   making comprehensive employee profiles purchasable for $1–5 USD
- C) Government agencies that share intelligence between law enforcement bodies
- D) Cybersecurity firms that sell threat intelligence feeds to enterprises

---

**Q28.** A tester runs traceroute to a target and the last few hops reveal IP
addresses in the 192.168.10.x and 172.16.x.x ranges. Why is this significant
to the attacker?

- A) These are public IPs that confirm the target's geographic location
- B) These are RFC 1918 private addresses — the target's internal IP addressing
   schema is leaking through the traceroute output
- C) These IPs indicate the target is using a content delivery network (CDN)
- D) These are the ISP's IPs — indicating the tester is still far from the target

---
&nbsp;

&nbsp;

&nbsp;

---

## Answers & Explanations

---

**Q1. Correct Answer: B) Before a single packet is sent — prior to any testing activity** ✅

**Explanation:**
The **Security Evaluation Plan (SEP)** is a legally binding document that must be
negotiated, signed, and fully executed by BOTH parties — client and tester — BEFORE
any testing activity begins. This includes before any reconnaissance, passive or active.

- **A)** — ❌ Waiting until after recon means testing has begun without legal authorization
  — the tester is already exposed to criminal liability
- **B)** — ✅ Signed before any activity — this is non-negotiable
- **C)** — ❌ Starting after first findings means testing occurred without authorization
- **D)** — ❌ Signing at the end of testing provides no legal protection during testing

> The SEP IS the legal protection. Without it signed first, the tester is
> a criminal — even if the client verbally said "go ahead."

---

**Q2. Correct Answer: B) A short portable authorization letter carried by the tester
during the engagement** ✅

**Explanation:**
The **"Get Out of Jail Free" card** is a separate, shorter document from the full SEP —
designed to be portable and immediately presentable to law enforcement if needed during
on-site testing. It contains: client org name, authorization statement, in-scope IP ranges,
testing dates/times, emergency contact, and senior executive signature.

The **Coalfire Case (2019)** illustrated why this document must be robust — two authorized
testers were arrested during a physical pentest of an Iowa courthouse and detained for
11 days before charges were dropped.

- **A)** — ❌ It does NOT completely protect from criminal liability — it demonstrates
  authorization to law enforcement. Courts can still question it.
- **B)** — ✅ Short, portable authorization letter carried on-person during testing
- **C)** — ❌ It is NOT submitted to law enforcement proactively — it is presented IF stopped
- **D)** — ❌ It exempts nothing internally — it is an authorization document, not a waiver

---

**Q3. Correct Answer: D) 7** ✅

**Explanation:**
The **PTES (Penetration Testing Execution Standard)** defines exactly **7 phases**:
1. Pre-Engagement
2. Intelligence Gathering
3. Threat Modeling
4. Vulnerability Analysis
5. Exploitation
6. Post-Exploitation
7. Reporting

- **A) 4** — ❌ 4 phases is the NIST SP 800-115 framework — not PTES
- **B) 5** — ❌ 5 phases maps to the 5 Phases of Ethical Hacking (general model) — not PTES
- **C) 6** — ❌ Not PTES — no major standard has exactly 6 phases
- **D) 7** — ✅ PTES has exactly 7 phases

---

**Q4. Correct Answer: A) 4** ✅

**Explanation:**
**NIST SP 800-115** (Technical Guide to Information Security Testing) defines
**4 phases** for its security testing methodology:
1. Planning
2. Discovery
3. Attack
4. Reporting

- **A) 4** — ✅ NIST SP 800-115 = 4 phases
- **B) 7** — ❌ 7 phases = PTES
- **C) 9** — ❌ Not associated with any standard in this module
- **D) 12** — ❌ 12 is the number of PCI DSS requirements — not a testing phase count

---

**Q5. Correct Answer: D) White Box** ✅

**Explanation:**
**White Box testing** (also called Crystal Box or Full Knowledge testing) provides the
tester with COMPLETE information about the target: source code, architecture diagrams,
network topology, valid credentials, and system documentation. It is the most thorough
type and simulates a scenario where the attacker has insider-level knowledge.

- **A) Black Box** — ❌ Zero knowledge — simulates a fully external attacker
- **B) Red Box** — ❌ Not a standard test classification — does not exist
- **C) Grey Box** — ❌ PARTIAL knowledge — e.g., user-level credentials without source code
- **D) White Box** — ✅ COMPLETE knowledge — source code + diagrams + credentials

---

**Q6. Correct Answer: C) Grey Box** ✅

**Explanation:**
**Grey Box testing** is explicitly described as the **most realistic for modern threat
simulation** because it mirrors what actually happens in real attacks: a phishing email
succeeds → attacker now has user credentials + limited knowledge of the org → what can
they do from that position? This is far more realistic than a pure external (black box)
or fully trusted (white box) scenario.

- **A) Black Box** — ❌ Most realistic for EXTERNAL attacker with no prior info — not the
  most realistic overall given how most breaches actually begin
- **B) White Box** — ❌ Most thorough but least realistic — attackers rarely have full access
  to source code and credentials before breaking in
- **C) Grey Box** — ✅ Partial knowledge — most realistic for modern insider/post-phishing
  breach scenarios
- **D) Red Team** — ❌ Red Team is an engagement model (broad scope, full simulation) —
  not a knowledge-level classification

---

**Q7. Correct Answer: C) Systematically collecting information about a target BEFORE
any technical testing** ✅

**Explanation:**
**Footprinting** is the structured, methodical process of gathering intelligence about
a target — covering network, systems, people, web, security posture, and physical
information — BEFORE any scanning, exploitation, or direct interaction with the target
occurs. It is the foundation of Phase 1 (Reconnaissance).

- **A)** — ❌ Analyzing malware on a compromised system = digital forensics or malware
  analysis — Phase 3 or later activity
- **B)** — ❌ Scanning for open ports = Phase 2 (Scanning & Enumeration) — NOT footprinting
- **C)** — ✅ Systematic information gathering before technical testing = footprinting
- **D)** — ❌ Documenting findings after testing = reporting — Phase 5 activity

---

**Q8. Correct Answer: C) Passive Footprinting** ✅

**Explanation:**
All three activities — using a third-party DNS tool, checking LinkedIn, searching Shodan —
involve querying **third-party sources** that hold cached or publicly available information
about the target. No packets travel to the target's own systems. The target has NO WAY
of detecting these queries.

The defining test: **"Did any of my activity reach the TARGET'S systems?"** Answer: No.
Therefore this is **Passive Footprinting**.

- **A) Active** — ❌ Active footprinting requires packets to directly reach target systems
- **B) Hybrid** — ❌ Not a standard classification in the passive/active model
- **C) Passive** — ✅ All queries go to third-party sources — target systems untouched
- **D) Enumeration** — ❌ Enumeration is Phase 2 — extracting specific service/user details
  after direct scanning contact

---

**Q9. Correct Answer: B) Active Footprinting — packets directly reach the target's systems** ✅

**Explanation:**
A **ping** sends ICMP Echo Request packets that travel directly to the target server.
The target server receives these packets and sends ICMP Echo Reply packets back. These
interactions are **logged on the target's systems** and can trigger IDS alerts.

This is the defining characteristic of **Active Footprinting** — the target's systems
receive traffic from the tester. Authorization is required.

- **A)** — ❌ "Safe and non-invasive" is irrelevant to the passive/active classification —
  the classification is about whether target systems are reached, not about harm level
- **B)** — ✅ ICMP packets hit the target server directly — active footprinting
- **C)** — ❌ Ping is not OSINT — it actively queries the target, not a public database
- **D)** — ❌ Passive recon does NOT touch target systems at all — ping absolutely does

---

**Q10. Correct Answer: C) Find subdomains and servers that have ever had a certificate
issued** ✅

**Explanation:**
**Certificate Transparency (CT)** is a public log of ALL SSL/TLS certificates ever issued
for any domain. When organizations create web servers — even internal dev/staging servers —
and obtain SSL certificates, those certificates are logged PUBLICLY and PERMANENTLY.
Attackers search CT logs to find subdomains and servers that may not be visible in normal
DNS queries.

Examples found: `dev.company.com`, `staging.company.com`, `vpn.company.com`,
`admin.company.com` — often with weaker security configurations than production.

- **A)** — ❌ CT logs do NOT record individual SSL connections/sessions — only certificates
- **B)** — ❌ Private keys are NEVER included in CT logs — only public certificate information
- **C)** — ✅ Historical certificate records reveal subdomains and servers
- **D)** — ❌ CT logs are historical records — they do NOT intercept live traffic

---

**Q11. Correct Answer: B) crt.sh** ✅

**Explanation:**
**[crt.sh](https://crt.sh)** is the specific tool used to search Certificate Transparency
logs. By searching for `%.targetcompany.com`, every subdomain that has ever had an SSL
certificate issued will appear — including development, staging, API, admin, and VPN
subdomains that may not be publicly advertised.

- **A) shodan.io** — ❌ Shodan scans internet-connected devices and services — not
  specifically CT logs
- **B) crt.sh** — ✅ The dedicated Certificate Transparency log search tool
- **C) dnsdumpster.com** — ❌ DNS intelligence and subdomain mapping — different source
- **D) exploit-db.com** — ❌ Houses the Google Hacking Database (GHDB) and exploits —
  not CT logs

---

**Q12. Correct Answer: B) The firewall or network security technology the organization
is likely using** ✅

**Explanation:**
When 50 engineers at an organization list "Palo Alto Networks" in their LinkedIn skills
section, it reveals that a significant portion of their technical staff has expertise
with Palo Alto Networks products — this strongly indicates the organization is using
Palo Alto Networks firewalls, NGFW, or related security infrastructure. This is valuable
intelligence for planning an attack or test — knowing the specific security product lets
an attacker research known weaknesses or bypass techniques.

- **A)** — ❌ Physical security posture is not revealed by software skills
- **B)** — ✅ Technology stack exposure — "50 engineers use this → org uses this product"
- **C)** — ❌ 50 engineers listing a skill doesn't directly reveal team SIZE —
  they could be spread across different teams
- **D)** — ❌ Budget cannot be directly inferred from technology brand

---

**Q13. Correct Answer: B) The target organization uses Splunk as their SIEM — and may
currently lack expertise** ✅

**Explanation:**
Job postings are a PRIMARY source of technology stack intelligence. When an organization
advertises for a "Senior Splunk Administrator," they directly reveal:
1. They USE Splunk as their SIEM platform
2. They currently LACK a senior Splunk expert (the current position is open)
3. Their monitoring capability may be undermanned during the hiring period

This is valuable because the attacker now knows the SIEM product — and can research
evasion techniques specific to Splunk detection rules.

- **A)** — ❌ Hiring for a role means they're investing in it, not switching away
- **B)** — ✅ Splunk use confirmed AND potentially understaffed = two pieces of intel
- **C)** — ❌ A job posting reveals WHAT technology they use — not specific vulnerabilities
- **D)** — ❌ "Senior Splunk Administrator" is clearly a SIEM management role, not pentest

---

**Q14. Correct Answer: C) TTL (Time To Live) field** ✅

**Explanation:**
Traceroute's entire mechanism is built on the **TTL (Time To Live)** field in the IP
packet header. Every time a router forwards a packet, it decrements TTL by 1. When TTL
reaches 0, the router drops the packet and sends an **ICMP Time Exceeded** message back
to the source. Traceroute exploits this by sending packets with progressively increasing
TTL values (1, 2, 3...) to reveal each hop in sequence.

- **A) Protocol field** — ❌ The protocol field identifies the transport protocol (TCP/UDP/ICMP)
  — traceroute doesn't exploit this field
- **B) Source IP** — ❌ The source IP is simply the tester's address — traceroute doesn't
  manipulate it (that would be IP spoofing)
- **C) TTL** — ✅ Traceroute exploits TTL by incrementing it one step at a time
- **D) Checksum** — ❌ The checksum validates packet integrity — traceroute doesn't use it
  as the mapping mechanism

---

**Q15. Correct Answer: B) ICMP Time Exceeded message** ✅

**Explanation:**
When a router receives a packet, it decrements TTL by 1. If the result is **zero**, the
router **drops** the packet and sends an **ICMP Type 11 — Time Exceeded** message back
to the original sender. This message contains the router's IP address — which is exactly
what traceroute records as the hop at that TTL level.

- **A) TCP RST** — ❌ TCP RST is sent to terminate TCP connections — not related to TTL
  expiration which is an IP-layer event
- **B) ICMP Time Exceeded** — ✅ Exactly the message sent when TTL hits zero at a router
- **C) TCP SYN-ACK** — ❌ Part of the TCP three-way handshake — not a TTL response
- **D) ARP Reply** — ❌ ARP operates at Layer 2 for MAC address resolution — completely
  different protocol and purpose

---

**Q16. Correct Answer: B) A firewall or router is blocking ICMP packets at that
network segment** ✅

**Explanation:**
When traceroute shows `* * *` for a hop, it means no **ICMP Time Exceeded** response
was received within the timeout period. The most common cause: a **firewall or router
is configured to DROP ICMP packets** (including Time Exceeded responses) at that point
in the network. This is intentional — network administrators configure this to prevent
traceroute-based topology mapping.

An attacker notes the position of the `***` hops to identify where firewalls are placed.

- **A)** — ❌ If the target were offline, ALL subsequent hops would also show `***` or
  the final destination simply wouldn't respond — a single gap of three `***` hops
  indicates firewall filtering, not server outage
- **B)** — ✅ ICMP blocking at a firewall/router = `***` response
- **C)** — ❌ If the tester's connection had packet loss, ALL hops would show inconsistent
  results — not a specific cluster of three consecutive `***`
- **D)** — ❌ Successful completion shows the target responding (Echo Reply or port
  unreachable) — `***` means no response received

---

**Q17. Correct Answer: C) `tcptraceroute` / `traceroute -T`** ✅

**Explanation:**
Standard Linux `traceroute` uses **UDP** packets by default. Standard Windows `tracert`
uses **ICMP** Echo Requests. Many firewalls are configured to BLOCK UDP and ICMP at
perimeter points — which is why `***` appears.

**TCP traceroute** sends **TCP SYN packets** on ports 80 or 443 — ports that firewalls
almost always allow through (because blocking them would break web browsing). This allows
TCP traceroute to pass through firewalls that would block standard traceroute, revealing
additional hops that UDP/ICMP traceroute cannot reach.

- **A) `tracert` (Windows)** — ❌ Uses ICMP Echo Requests — blocked by same firewalls
  that block standard traceroute
- **B) `mtr`** — ❌ Combines ping + traceroute for real-time display — still uses
  ICMP/UDP by default — not the firewall bypass method
- **C) `tcptraceroute` / `traceroute -T`** — ✅ TCP SYN packets on port 80/443 —
  bypass firewalls that block ICMP/UDP
- **D) Standard `traceroute` (UDP mode)** — ❌ This is what standard Linux traceroute
  uses — easily blocked by firewalls

---

**Q18. Correct Answer: C) Publicly accessible information — no hacking or authorization
required to view** ✅

**Explanation:**
In the intelligence context, **"Open Source"** means **PUBLICLY AVAILABLE** — not open
source software. OSINT refers to intelligence gathered from sources that any member of
the public can legally access: websites, social media, government records, news articles,
DNS databases, WHOIS, job postings, etc. No unauthorized access, no hacking.

The "open" in OSINT = open to the public, not "open source code."

- **A)** — ❌ OSINT is not restricted to open-source software projects — it covers
  ALL public information sources
- **B)** — ❌ The "open source" in OSINT does NOT refer to tool licensing
- **C)** — ✅ Publicly accessible information — legally viewable by anyone
- **D)** — ❌ Government intelligence sharing = classified intel — the OPPOSITE of OSINT
  which must be publicly available

---

**Q19. Correct Answer: D) `site:`** ✅

**Explanation:**
The **`site:`** operator in Google search limits all results to pages from a specific
domain. Example: `site:targetcompany.com` returns ONLY pages indexed from that domain.

Other operators serve different purposes:
- `inurl:` — text in the URL
- `filetype:` — specific file extension
- `intitle:` — text in the page title

- **A) `inurl:`** — ❌ Finds text in the URL path — not domain restriction
- **B) `filetype:`** — ❌ Filters by file extension (pdf, xls, txt) — not domain
- **C) `intitle:`** — ❌ Finds text in the HTML title tag — not domain
- **D) `site:`** — ✅ Restricts results to specific domain — the domain-limiting operator

---

**Q20. Correct Answer: B) Directory listing pages — which may expose sensitive files** ✅

**Explanation:**
The dork `intitle:"index of"` finds **web server directory listing pages** — pages where
the web server has been misconfigured to display the file system contents of a directory
instead of a proper web page. These listings may expose:
- Configuration files with passwords
- Backup files
- Database dumps
- Private documents
- Source code

The `site:targetcompany.com` limits results to the target domain.

- **A)** — ❌ Login pages would use `inurl:login` or `inurl:admin` — not `intitle:"index of"`
- **B)** — ✅ "Index of" is the standard HTML title for Apache/Nginx directory listings
- **C)** — ❌ Finding "password" in body text would use `intext:password` — not intitle
- **D)** — ❌ Subdomain discovery uses `-www site:targetcompany.com` or DNS tools —
  not `intitle:"index of"`

---

**Q21. Correct Answer: C) exploit-db.com/google-hacking-database** ✅

**Explanation:**
The **Google Hacking Database (GHDB)** is maintained by Offensive Security on their
**Exploit-DB** platform at `exploit-db.com/google-hacking-database`. It contains
thousands of pre-built Google Dorks organized by category including: sensitive files,
error messages, login portals, network devices, web cameras, and vulnerable servers.

- **A) shodan.io** — ❌ Shodan is an internet device search engine — hosts device data,
  not the GHDB
- **B) osintframework.com** — ❌ Visual map of OSINT tools by data category — does not
  host the GHDB
- **C) exploit-db.com/google-hacking-database** — ✅ The official GHDB location
- **D) haveibeenpwned.com** — ❌ Breach and credential checking service — not dork database

---

**Q22. Correct Answer: C) By the type of data being sought (username, IP, email, etc.)** ✅

**Explanation:**
The **OSINT Framework** at osintframework.com is a visual tree-structure tool where the
top-level categories are organized by **what type of data you are looking for** — not by
tool cost, skill level, or attack phase. Categories include: Username, Email Address,
Domain Name, IP Address, Images/Video/Audio, Social Networks, Phone Numbers, Business
Records, Geolocation, Dark Web, and more. You navigate to what data type you need and
find the tools that can gather it.

- **A)** — ❌ Tool cost is not the organizing principle — many free AND paid tools exist
  across all categories
- **B)** — ❌ Skill level is not how OSINT Framework organizes its tree
- **C)** — ✅ Data type being sought = the organizing principle of osintframework.com
- **D)** — ❌ Attack phase is not the organizing principle — one data type can be used
  across multiple phases

---

**Q23. Correct Answer: C) TA0043 (Reconnaissance)** ✅

**Explanation:**
**TA0043** is the MITRE ATT&CK Tactic ID for **Reconnaissance** — the pre-attack phase
covering all techniques adversaries use to gather information before conducting operations.
It includes active scanning, OSINT gathering, phishing for information, and searching
open source/technical databases.

- **A) TA0001 (Initial Access)** — ❌ Initial Access covers techniques to get into the
  target network (phishing, exploit public-facing apps) — after recon is complete
- **B) TA0007 (Discovery)** — ❌ Discovery covers post-access internal network mapping —
  NOT the pre-attack external recon phase
- **C) TA0043** — ✅ Reconnaissance — pre-attack external information gathering
- **D) TA0010 (Exfiltration)** — ❌ Exfiltration = stealing data out of target — final phases

---

**Q24. Correct Answer: B) T1596.003 — Search Technical Databases: Digital Certificates** ✅

**Explanation:**
The MITRE ATT&CK technique **T1596.003** specifically maps to searching **Digital
Certificate databases** — which includes Certificate Transparency logs — to discover
subdomains, infrastructure, and historical systems associated with the target organization.

- **A) T1595.001 — Active Scanning: IP Blocks** — ❌ This maps to actively scanning
  IP address ranges — not searching CT logs passively
- **B) T1596.003** — ✅ Search Technical Databases: Digital Certificates — CT log searches
- **C) T1590.002 — Gather Network Info: DNS** — ❌ Maps to DNS record enumeration —
  not certificate transparency specifically
- **D) T1593.001 — Search Open Source: Social Media** — ❌ Social media intelligence —
  not certificate databases

---

**Q25. Correct Answer: C) Deepfake video of the CFO on a real-time video call** ✅

**Explanation:**
In early 2024, a Hong Kong company was defrauded of **$25.6 million USD** after
attackers used **AI-generated deepfake video technology** to impersonate the company's
CFO and other colleagues on a real-time video conference call. Employees on the call
believed they were speaking to their real CFO and authorized the fraudulent wire transfers.
This case demonstrated that deepfake attacks had reached real-time video capability —
making them significantly more dangerous than static fake images or audio.

- **A)** — ❌ AI phishing emails are a separate technique — the Hong Kong case involved
  real-time video, not email
- **B)** — ❌ Voice cloning (30-second audio → cloned voice) was a separate incident in
  the UK ($243,000 loss) — not the Hong Kong $25.6M case
- **C)** — ✅ Real-time deepfake video on a video call — the $25.6 million Hong Kong case
- **D)** — ❌ Credential stuffing uses leaked passwords — the Hong Kong case used visual
  impersonation, not credentials

---

**Q26. Correct Answer: C) Attack Surface Management (ASM)** ✅

**Explanation:**
**Attack Surface Management (ASM)** is the practice of continuously discovering,
monitoring, and reducing your organization's external attack surface — FROM THE ATTACKER'S
PERSPECTIVE. This includes running OSINT tools, recon tools, and vulnerability scanners
against YOUR OWN organization to find what an attacker would find. Tools like Shodan
Monitor, Censys ASM, SpiderFoot HX, and Microsoft Defender EASM are purpose-built for
continuous ASM.

- **A) Threat Intelligence Gathering** — ❌ TI focuses on external threat actor activity —
  not scanning your own attack surface
- **B) Vulnerability Assessment** — ❌ VA typically scans known internal systems for
  vulnerabilities — ASM discovers UNKNOWN external exposure
- **C) Attack Surface Management** — ✅ Running recon against your own org = ASM
- **D) SIEM** — ❌ SIEM aggregates and correlates log data for detection — not external
  attack surface discovery

---

**Q27. Correct Answer: B) Companies that LEGALLY collect, aggregate, and sell personal
data — making comprehensive employee profiles purchasable for $1–5 USD** ✅

**Explanation:**
**Data Brokers** are LEGITIMATE companies (Spokeo, Whitepages, BeenVerified, ZoomInfo,
LexisNexis) that legally gather data from public records, purchase histories, social
media, apps, and other sources — then sell comprehensive personal profiles. An attacker
can buy a detailed profile of a target employee (name, addresses, family members,
employment history, phone numbers, email addresses) for as little as $1–5 USD.
This makes targeted social engineering attacks significantly easier.

- **A)** — ❌ Dark web stolen data sellers are CRIMINAL marketplaces — data brokers are
  LEGAL businesses — this is a critical distinction
- **B)** — ✅ Legal data aggregators selling personal profiles — attacker intelligence source
- **C)** — ❌ Government intelligence sharing is classified/restricted — opposite of
  data broker open sales
- **D)** — ❌ Threat intelligence feeds are cybersecurity products for defenders —
  not personal data profiles for sale

---

**Q28. Correct Answer: B) These are RFC 1918 private addresses — the target's internal
IP addressing schema is leaking through the traceroute output** ✅

**Explanation:**
**RFC 1918** defines private (non-routable) IP address ranges:
- `10.0.0.0/8`
- `172.16.0.0/12` (172.16.x.x – 172.31.x.x)
- `192.168.0.0/16`

When traceroute output shows these ranges in the final hops, it means the target's
routers are not filtering their ICMP Time Exceeded responses — and are revealing the
INTERNAL IP addressing scheme. An attacker can now infer what other hosts may exist
on those subnets (e.g., 192.168.10.5 is the web server → 192.168.10.1 might be the
gateway, 192.168.10.x range may have other servers).

- **A)** — ❌ RFC 1918 addresses are private ranges — they are NOT public IPs and cannot
  geolocate to a physical place
- **B)** — ✅ Private IP address ranges leaking through traceroute = internal addressing
  schema exposure
- **C)** — ❌ CDN usage shows up as the final hop before target being a CDN IP
  (Cloudflare, Akamai) — not as private RFC 1918 addresses
- **D)** — ❌ ISP hops appear at the beginning of a traceroute (hops 2–4) — not at the
  end near the target

---

## Quick Answer Key

| Q | Answer | Q | Answer | Q | Answer |
|---|---|---|---|---|---|
| Q1 | B | Q11 | B | Q21 | C |
| Q2 | B | Q12 | B | Q22 | C |
| Q3 | D | Q13 | B | Q23 | C |
| Q4 | A | Q14 | C | Q24 | B |
| Q5 | D | Q15 | B | Q25 | C |
| Q6 | C | Q16 | B | Q26 | C |
| Q7 | C | Q17 | C | Q27 | B |
| Q8 | C | Q18 | C | Q28 | B |
| Q9 | B | Q19 | D | | |
| Q10 | C | Q20 | B | | |

---

## Topic Coverage Map

| Q | Section | Concept Tested |
|---|---|---|
| Q1 | Section 1 | SEP — when it must be signed |
| Q2 | Section 1 | Get Out of Jail Free card — definition |
| Q3 | Section 1 | PTES framework — number of phases |
| Q4 | Section 1 | NIST SP 800-115 — number of phases |
| Q5 | Section 2 | Test types by knowledge — White Box |
| Q6 | Section 2 | Test types by knowledge — Grey Box (most realistic) |
| Q7 | Section 3 | Footprinting — definition |
| Q8 | Section 3 | Passive vs Active footprinting — passive example |
| Q9 | Section 3 | Passive vs Active footprinting — active example |
| Q10 | Section 3 | Certificate Transparency — what it reveals |
| Q11 | Section 3 | Certificate Transparency — crt.sh tool |
| Q12 | Section 4 | Social engineering recon — LinkedIn tech stack |
| Q13 | Section 4 | Social engineering recon — job postings as intelligence |
| Q14 | Section 5 | Traceroute — TTL field exploitation |
| Q15 | Section 5 | Traceroute — ICMP Time Exceeded response |
| Q16 | Section 5 | Traceroute — meaning of `***` hops |
| Q17 | Section 5 | Traceroute variants — TCP traceroute firewall bypass |
| Q18 | Section 6 | OSINT — definition of "Open Source" |
| Q19 | Section 6 | Google Dorking — site: operator |
| Q20 | Section 6 | Google Dorking — intitle:"index of" meaning |
| Q21 | Section 6 | GHDB — exploit-db.com location |
| Q22 | Section 6 | OSINT Framework — organizing principle |
| Q23 | Section 7 | MITRE ATT&CK — TA0043 Reconnaissance tactic |
| Q24 | Section 7 | MITRE ATT&CK — T1596.003 certificate transparency |
| Q25 | Section 8 | 2026 context — deepfake video fraud (Hong Kong $25.6M) |
| Q26 | Section 8 | Attack Surface Management — definition |
| Q27 | Section 8 | Data brokers — what they are and the threat |
| Q28 | Section 5 | Traceroute — RFC 1918 internal IP leakage |

---