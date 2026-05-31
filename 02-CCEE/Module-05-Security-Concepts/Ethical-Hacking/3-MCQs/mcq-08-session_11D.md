# 💥 MCQ Set — Session 11D

**Module:** Security Concepts — Ethical Hacking
**Coverage:** DDoS Architecture · Botnet Mechanics · C2 Models · Volumetric Attacks ·
Protocol Attacks · Application Layer Attacks · SYN Cookies · Amplification ·
DDoS Countermeasures
**Total Questions:** 30
**Format:** Foundation + Fundamental + Basic Concepts only

---

## 📋 Table of Contents

- [Questions — Q1 to Q30](#questions)
- [Answers & Explanations](#answers--explanations)
- [Quick Answer Key](#quick-answer-key)
- [Topic Coverage Map](#topic-coverage-map)

---

## Questions

---

**Q1.** What is the FUNDAMENTAL difference between a DoS attack and a
DDoS attack that makes DDoS significantly harder to defend against?

- A) DDoS uses encrypted traffic while DoS uses plain-text traffic
- B) DDoS originates from MANY sources simultaneously — blocking individual
   IPs is impractical when each bot sends seemingly normal traffic volumes
- C) DDoS targets applications while DoS only targets network infrastructure
- D) DDoS requires malware while DoS can be launched manually

---

**Q2.** In the six-component DDoS architecture, which component NEVER sends
attack traffic directly to the victim — keeping their IP out of the target's
logs entirely?

- A) The Bots (Zombies)
- B) The Handlers
- C) The Botmaster (Attacker)
- D) The Reflectors

---

**Q3.** What are REFLECTORS in a DDoS amplification attack?

- A) Compromised machines that are part of the botnet
- B) Legitimate third-party servers that UNWITTINGLY amplify traffic by
   responding to spoofed requests aimed at the victim
- C) Mirrors of the victim's website hosted on CDN nodes
- D) Intermediate relay servers between the C2 and the bots

---

**Q4.** Which stage of the botnet lifecycle involves the bot contacting C2
to register its IP, OS version, and bandwidth capacity — receiving an ID
and configuration in return?

- A) Initial Infection (Seeding)
- B) Propagation (Self-Replication)
- C) Rallying (C2 Connection)
- D) Weaponization (Attack Command)

---

**Q5.** Mirai (2016) infected 600,000+ IoT devices automatically. What was
Mirai's primary infection method?

- A) Exploiting unpatched CVEs in enterprise firewalls
- B) Phishing emails with malicious attachments
- C) Scanning for IoT devices with DEFAULT CREDENTIALS using 62 credential pairs
- D) Supply chain compromise of IoT firmware update servers

---

**Q6.** In a Centralized (Client-Server) C2 model, what is the PRIMARY
weakness that makes the botnet easy to disrupt?

- A) Commands propagate slowly through multiple hops
- B) The botnet is limited to a maximum of 1,000 bots
- C) Single point of failure — seizing the C2 server disrupts the
   entire botnet
- D) The protocol is too complex for bots to implement reliably

---

**Q7.** Which C2 model does the Conficker worm use — generating 50,000
pseudo-random domains per day across 110 TLDs to find the active C2 server?

- A) Centralized (IRC)
- B) Peer-to-Peer (P2P)
- C) Domain Generation Algorithm (DGA)
- D) Fast-Flux DNS

---

**Q8.** Comparing the three C2 models, which is MOST DIFFICULT for law
enforcement to take down because it has no central node?

- A) Centralized (IRC-based)
- B) Centralized (HTTP-based)
- C) Domain Generation Algorithm (DGA)
- D) Peer-to-Peer (P2P)

---

**Q9.** The three DDoS attack categories target different resources. Which
category targets BANDWIDTH and is measured in Gbps/Tbps?

- A) Protocol Attacks
- B) Application Layer Attacks
- C) Volumetric Attacks
- D) State Exhaustion Attacks

---

**Q10.** A UDP Flood sends packets to RANDOM ports on the victim. What
resource does this primarily exhaust on the victim machine?

- A) Hard disk space through log file accumulation
- B) TCP backlog queue entries
- C) CPU and outbound bandwidth — victim must generate ICMP
   "Destination Unreachable" for each unknown port
- D) SSL/TLS certificate validation capacity

---

**Q11.** In a DNS Amplification attack, the attacker sends small DNS
queries (approximately 60 bytes) with the victim's IP as the source to
open DNS resolvers. The resolvers send large responses (approximately 3,000
bytes) to the victim. What is the approximate amplification factor?

- A) 5×
- B) 28–54×
- C) 556×
- D) 51,000×

---

**Q12.** Which amplification protocol/service produced the LARGEST known
amplification factor — approximately 51,000× — and was exploited in the
February 2018 GitHub DDoS attack (1.35 Tbps)?

- A) DNS (ANY query) on UDP 53
- B) NTP Monlist on UDP 123
- C) SNMP on UDP 161
- D) Memcached on UDP 11211

---

**Q13.** The Smurf attack amplifies ICMP traffic using directed broadcast
addresses. Why is the Smurf attack considered LARGELY DEAD in 2026?

- A) ICMP has been deprecated from IPv4 and is no longer in use
- B) RFC 2644 (1999) mandated that routers must NOT forward directed
   broadcasts by default
- C) Modern firewalls automatically detect and block all ICMP traffic
- D) ISPs globally implemented BCP38 which prevents ICMP spoofing

---

**Q14.** A SYN Flood is classified as a PROTOCOL attack rather than a
volumetric attack. Why?

- A) SYN packets are encrypted and require extra processing
- B) Each SYN is only ~40–60 bytes — the damage is to the TCP STATE TABLE
   (backlog queue), not to available bandwidth
- C) SYN Floods target DNS servers exclusively
- D) SYN packets use UDP protocol which consumes connection state entries

---

**Q15.** In a SYN Flood with spoofed source IPs, why is IP spoofing
CRITICAL to the attack's effectiveness?

- A) Spoofing allows the attacker to hide from firewall logs
- B) Without spoofing, the attacker's real IP receives the SYN-ACK and
   the OS auto-sends RST — immediately freeing the backlog slot
- C) Spoofing increases packet size, amplifying the volumetric effect
- D) Spoofing prevents the target from sending ICMP responses

---

**Q16.** What does the Linux kernel setting `net.ipv4.tcp_syncookies=1`
enable?

- A) UDP flood protection via ICMP rate limiting
- B) SYN Cookies — the server encodes connection state in the ISN instead
   of allocating a TCB, eliminating state storage for unverified connections
- C) Maximum SYN packet rate limiting at 100 per second
- D) Automatic blackhole routing for high-rate SYN sources

---

**Q17.** SYN Cookies prevent SYN Flood attacks by encoding connection state
in which field of the SYN-ACK response?

- A) The TCP Checksum field
- B) The IP TTL field
- C) The TCP Source Port field
- D) The Initial Sequence Number (ISN)

---

**Q18.** Application layer (L7) DDoS attacks are described as the HARDEST
to defend. Why?

- A) They consume enormous bandwidth that overwhelms all upstream links
- B) The traffic is VALID HTTP — legitimate-looking requests that pass
   through firewalls and IDS as normal user traffic
- C) Application attacks target the C2 servers, not the victim directly
- D) L7 attacks use zero-day vulnerabilities that have no patches

---

**Q19.** The Slowloris attack opens many partial HTTP connections and keeps
them open by sending one header byte every 10–15 seconds. Which web server
is NOT vulnerable to Slowloris due to its event-driven architecture?

- A) Apache
- B) IIS
- C) Tomcat
- D) Nginx

---

**Q20.** Why can a SINGLE machine running Slowloris take down an Apache
web server?

- A) Slowloris exploits a buffer overflow in the Apache process
- B) Apache uses a THREAD-PER-CONNECTION model — each slow connection
   permanently holds one thread until the request completes or times out
- C) Slowloris corrupts Apache's configuration files during the attack
- D) Apache has a hard limit of 10 connections total by default

---

**Q21.** The RUDY (R-U-Dead-Yet) attack is similar to Slowloris but targets
POST bodies instead of headers. How does RUDY hold connections open?

- A) Sends HTTP headers with an invalid Content-Type value
- B) Declares a very large Content-Length then transmits the POST body
   ONE BYTE AT A TIME — forcing the server to wait indefinitely
- C) Sends SYN packets with the URG flag set in the POST header
- D) Floods the server with empty POST requests to exhaust memory

---

**Q22.** Comparing the three DDoS categories: which combination CORRECTLY
matches categories to their defense approach?

- A) Volumetric → WAF + CAPTCHA · Protocol → Upstream Scrubbing · App → SYN Cookies
- B) Volumetric → Upstream Scrubbing/Anycast · Protocol → SYN Cookies/BCP38 ·
   App → WAF/Behavioral Analysis
- C) Volumetric → SYN Cookies · Protocol → Anycast · App → BCP38
- D) All three categories → Deploy a firewall with default deny rules

---

**Q23.** Blackhole Routing (RTBH) is described as a "last resort" DDoS
countermeasure. Why?

- A) Blackhole routing is expensive and requires special hardware
- B) It drops ALL traffic to the victim IP — including legitimate traffic —
   so the service remains unavailable even though the attack is "stopped"
- C) Blackhole routing only works against UDP traffic, not TCP floods
- D) It requires all ISPs globally to coordinate simultaneously

---

**Q24.** Anycast IP addressing distributes DDoS attack traffic across
multiple geographic locations. Which statement BEST explains how this
defends against volumetric DDoS?

- A) Anycast encrypts attack traffic so it cannot be processed by bots
- B) Anycast routes each bot to a nearby PoP — the attack is distributed
   across all locations, with each absorbing only a fraction of total volume
- C) Anycast changes the victim's IP address every 5 minutes
- D) Anycast adds an extra network hop that drops malformed packets

---

**Q25.** The October 2016 Dyn DNS DDoS attack used the Mirai botnet,
reached approximately 1.2 Tbps, and caused outages affecting Twitter,
Netflix, Reddit, GitHub, and others. What was the PRIMARY botnet
composition used in this attack?

- A) Compromised enterprise servers with high-bandwidth connections
- B) A network of Windows PCs infected via phishing campaigns
- C) IoT devices (cameras, DVRs, routers) compromised via default credentials
- D) Cloud VMs rented specifically for the attack

---

**Q26.** BCP38 / uRPF (Unicast Reverse Path Forwarding) is described as
the most fundamental countermeasure against amplification attacks. Why?

- A) It prevents attackers from accessing open DNS resolvers
- B) It blocks ALL amplification attacks by preventing IP spoofing
   at the ISP level — without spoofing, the victim cannot be set as the
   "source" for reflected traffic
- C) It limits the size of DNS responses to under 512 bytes
- D) It adds rate limiting to all UDP traffic at perimeter routers

---

**Q27.** Under India's IT Act 2000, a DDoS attack targeting CRITICAL
INFRASTRUCTURE (banking, power grid, defense) is classified under which
section with a penalty of imprisonment up to LIFE?

- A) Section 43 — Unauthorized access with civil compensation
- B) Section 66 — Computer-related offenses up to 3 years
- C) Section 66F — Cyberterrorism
- D) Section 67 — Publishing obscene content

---

**Q28.** A SIEM analyst observes that the SYN:SYN-ACK ratio on a server
is 200:1 — meaning 200 SYN packets are being received for every 1 SYN-ACK
response sent. What does this indicate?

- A) The server is experiencing normal peak traffic load
- B) The server's outbound bandwidth is saturated by large responses
- C) A SYN Flood is in progress — most SYNs have spoofed IPs and never
   complete the handshake, consuming backlog queue entries
- D) An HTTP Flood is consuming all available server threads

---

**Q29.** In 2026, AI-powered adaptive botnets differ from earlier botnets
by dynamically changing attack vectors based on defense responses. If an
upstream scrubbing center successfully absorbs a volumetric UDP flood, what
would a 2026 adaptive botnet most likely do NEXT?

- A) Increase UDP flood volume until the scrubbing center is overwhelmed
- B) Stop the attack and wait 24 hours before trying again
- C) Switch to an application-layer attack (HTTP Flood or Slowloris) that
   passes through scrubbing as "legitimate" low-bandwidth traffic
- D) Switch to using more reflectors to increase the amplification factor

---

**Q30.** The MITRE ATT&CK technique T1499.003 (Application Exhaustion)
covers slow-rate attacks like Slowloris and RUDY. Which SIEM alert pattern
would BEST detect T1499.003 in progress?

- A) High inbound bandwidth spike (> 10 Gbps on the uplink)
- B) High SYN:SYN-ACK ratio (> 100:1) on port 80/443
- C) Large number of HTTP connections in ESTABLISHED state with very low
   bytes transferred and near-zero completion rate
- D) High rate of ICMP Destination Unreachable packets from the server

---
&nbsp;

&nbsp;

&nbsp;

---

## Answers & Explanations

---

**Q1. Correct Answer: B) DDoS originates from MANY sources simultaneously —
blocking individual IPs is impractical when each bot sends seemingly normal
traffic volumes** ✅

**Explanation:**
A **DoS** attack from a single source is trivially stopped: add a firewall rule
blocking that one IP — done. A **DDoS** attack from 100,000 bots is a fundamentally
different problem. Each bot may only send a few hundred packets per second —
well within "normal" ranges. The COMBINATION of all bots creates a devastating
flood, but no single source stands out as anomalous. Blocking every bot IP
requires identifying each one individually, and new ones rotate in constantly.

- **A)** — ❌ DDoS/DoS are not differentiated by encryption
- **B)** — ✅ Many sources simultaneously — each "normal," combined devastating
- **C)** — ❌ Both DoS and DDoS can target any layer
- **D)** — ❌ Both can use automated tools or malware

---

**Q2. Correct Answer: C) The Botmaster (Attacker)** ✅

**Explanation:**
The **Botmaster** operates through the C2 infrastructure — issuing commands to
bots, never sending attack traffic from their personal IP. The actual flood
traffic comes from the **bots**. Handlers relay commands. Reflectors amplify.
The botmaster's personal IP address never appears in the victim's traffic logs
or firewall records — maintaining operational security.

- **A) Bots** — ❌ Bots ARE the machines that generate and send attack traffic
- **B) Handlers** — ❌ Handlers relay commands but are still network infrastructure
  the botmaster may control
- **C) Botmaster** — ✅ Never sends traffic directly — operates through C2
- **D) Reflectors** — ❌ Reflectors send traffic to the victim (though unwittingly)

---

**Q3. Correct Answer: B) Legitimate third-party servers that UNWITTINGLY
amplify traffic by responding to spoofed requests aimed at the victim** ✅

**Explanation:**
**Reflectors** are NOT compromised. They are legitimate, publicly accessible
servers (DNS resolvers, NTP servers, Memcached instances) that simply respond
normally to requests. The attacker sends small requests with the **victim's IP
spoofed as the source**. The reflector believes the victim sent the query and
sends its (much larger) response to the victim. The reflector is an innocent
participant — it has no idea it is being used in an attack.

- **A)** — ❌ Compromised botnet machines are BOTS — not reflectors
- **B)** — ✅ Legitimate third-party servers responding to spoofed requests
- **C)** — ❌ CDN mirror nodes are a different concept entirely
- **D)** — ❌ Intermediate relay servers between C2 and bots are HANDLERS

---

**Q4. Correct Answer: C) Rallying (C2 Connection)** ✅

**Explanation:**
The botnet lifecycle stages in order:
1. **Initial Infection** — malware delivered to first machines
2. **Rallying** — infected bot contacts C2, registers, receives ID and config
3. **Propagation** — bot scans and infects more machines
4. **Weaponization** — botmaster issues attack command
5. **Maintenance** — updates, evasion, capacity rental

The **Rallying** stage is specifically when the bot "phones home" — establishing
the C2 channel by reporting its IP, OS, bandwidth, and receiving configuration.

- **A)** — ❌ Seeding = initial infection of the first machines
- **B)** — ❌ Propagation = the bot scanning and infecting additional machines
- **C)** — ✅ Rallying = bot phones home to C2, registers, receives configuration
- **D)** — ❌ Weaponization = botmaster issues the actual attack command

---

**Q5. Correct Answer: C) Scanning for IoT devices with DEFAULT CREDENTIALS
using 62 credential pairs** ✅

**Explanation:**
**Mirai** spread by scanning the **entire IPv4 address space** on TCP ports 23
and 2323 (Telnet). When it found a responding device, it attempted login using a
hardcoded list of **62 default username/password combinations** (admin/admin,
root/root, root/1234, etc.). If any worked, Mirai installed itself. This approach
infected 600,000+ devices within weeks — primarily cameras, DVRs, and home routers
— without the attacker touching 99.99% of them manually.

- **A)** — ❌ Enterprise firewall CVE exploitation is not Mirai's method
- **B)** — ❌ Phishing is a PC-targeting method — not how IoT devices are infected
- **C)** — ✅ Default credential brute force via Telnet (TCP 23/2323)
- **D)** — ❌ Supply chain firmware compromise is a different, targeted attack model

---

**Q6. Correct Answer: C) Single point of failure — seizing the C2 server
disrupts the entire botnet** ✅

**Explanation:**
In a **Centralized C2 model**, ALL bots connect to one (or a few) central servers.
If law enforcement seizes the C2 server, ALL bots lose their command channel
simultaneously — the botnet effectively dies. This is exactly how the GameOver
Zeus banking trojan (centralized variant) was taken down in Operation Tovar
(2014) — FBI seized the C2 servers and bots had nowhere to connect.

- **A)** — ❌ Slow command propagation is a weakness of P2P models — centralized
  is actually FAST
- **B)** — ❌ Centralized botnets can scale to millions of bots
- **C)** — ✅ Single point of failure = single seizure = entire botnet disrupted
- **D)** — ❌ IRC and HTTP protocols are straightforward to implement in bot code

---

**Q7. Correct Answer: C) Domain Generation Algorithm (DGA)** ✅

**Explanation:**
**Conficker** (2008–2009) used a DGA that generated **50,000 pseudo-random
domains per day** across 110 top-level domains. The botmaster registered just
ONE of those daily domains as the active C2. Conficker bots tried each generated
domain until they found the live one. This forced the security community to form
the "Conficker Working Group" — a massive coordination effort to preemptively
register and block all 50,000 daily domains.

- **A)** — ❌ IRC-based is centralized communication — not domain generation
- **B)** — ❌ P2P has no domains — bots connect to peer IPs
- **C)** — ✅ DGA generates pseudo-random daily domains — Conficker's method
- **D)** — ❌ Fast-Flux is a DNS evasion technique for hosting bulletproof
  infrastructure — different from DGA

---

**Q8. Correct Answer: D) Peer-to-Peer (P2P)** ✅

**Explanation:**
**P2P botnets** have no central command server. Commands are injected at any
node in the mesh and propagate through the network. There is **no single node**
whose seizure disrupts the botnet. Law enforcement would need to simultaneously
sinkhole or remove a significant fraction of all bot nodes — practically
impossible at scale. GameOver Zeus's P2P variant took significantly longer to
partially disrupt than centralized botnets.

| Model | Takedown Difficulty |
|---|---|
| Centralized | EASY — seize C2 |
| DGA | HARD — reverse engineer + register all domains daily |
| **P2P** | **VERY HARD — no central target** |

- **A) / B) Centralized** — ❌ Easiest to take down — seize the C2 server
- **C) DGA** — ❌ Hard but reversible once algorithm is known
- **D) P2P** — ✅ Most difficult — no central node to target

---

**Q9. Correct Answer: C) Volumetric Attacks** ✅

**Explanation:**
The three DDoS categories and their metrics:

| Category | Target | Measurement |
|---|---|---|
| **Volumetric** | **Bandwidth** | **Gbps / Tbps** |
| Protocol | State tables | Packets per second (pps) |
| Application | CPU / memory / DB | Requests per second (rps) |

Volumetric attacks aim to **saturate the network link** — filling it with so much
traffic that nothing else can pass. Examples: UDP Flood, DNS Amplification,
Memcached Amplification.

- **A) Protocol** — ❌ Protocol attacks target state tables, measured in pps
- **B) Application** — ❌ App-layer attacks target CPU/memory, measured in rps
- **C) Volumetric** — ✅ Targets bandwidth, measured in Gbps/Tbps
- **D)** — ❌ "State Exhaustion" is another name for Protocol attacks

---

**Q10. Correct Answer: C) CPU and outbound bandwidth — victim must generate
ICMP "Destination Unreachable" for each unknown port** ✅

**Explanation:**
A **UDP Flood** sends massive volumes of UDP packets to random ports. Since UDP is
connectionless (no handshake), the attacker fires at wire speed. For each UDP
packet arriving at a port with NO application listening, the victim's kernel must:
1. Check whether any application is listening on that port
2. Determine: no application listening
3. Generate an ICMP "Destination Unreachable (Port Unreachable)" response
4. Send that ICMP response

This consumes CPU for the port lookup and ICMP generation, AND consumes outbound
bandwidth for the ICMP responses — a secondary consumption effect.

- **A)** — ❌ UDP Floods don't fill disk logs — that would require application logging
- **B)** — ❌ TCP backlog queue entries are consumed by SYN Floods — not UDP
- **C)** — ✅ CPU for port checks + outbound BW for ICMP Unreachable responses
- **D)** — ❌ SSL/TLS validation is an application-layer concern — UDP has no TLS

---

**Q11. Correct Answer: B) 28–54×** ✅

**Explanation:**
**DNS Amplification** uses open DNS resolvers as reflectors. The attacker sends
a spoofed DNS `ANY` query (approximately 60 bytes) to an open resolver. The
resolver responds with a large DNS response (typically 2,000–3,000+ bytes) to
the spoofed victim IP. The amplification factor is:

Response size / Request size = 3,000 / 60 ≈ **50× (range: 28–54×)**

This means 1 Mbps of spoofed DNS queries can generate 28–54 Mbps aimed at the
victim — and with thousands of reflectors, a 1 Gbps attacker can generate a
multi-Tbps attack.

- **A) 5×** — ❌ Too low for DNS amplification
- **B) 28–54×** — ✅ DNS ANY query amplification factor
- **C) 556×** — ❌ 556× is the NTP Monlist amplification factor
- **D) 51,000×** — ❌ 51,000× is the Memcached amplification factor

---

**Q12. Correct Answer: D) Memcached on UDP 11211** ✅

**Explanation:**
**Memcached** (a distributed caching system) on **UDP port 11211** produced the
most extreme amplification factor of any known reflection attack — up to
**51,000×**. An attacker pre-loads data into an exposed Memcached server, then
sends a 15-byte `get [key]` request with the victim's spoofed IP. Memcached
responds with the full stored value (potentially 1 MB+) directed at the victim.

This was demonstrated dramatically in the **February 2018 GitHub DDoS** — peaking
at **1.35 Tbps**, the largest DDoS attack recorded at that time.

- **A) DNS** — ❌ DNS ANY query: 28–54× amplification
- **B) NTP Monlist** — ❌ NTP: 556× amplification
- **C) SNMP** — ❌ SNMP: approximately 6× amplification
- **D) Memcached** — ✅ UDP 11211 — up to 51,000× — GitHub 2018 (1.35 Tbps)

---

**Q13. Correct Answer: B) RFC 2644 (1999) mandated that routers must NOT
forward directed broadcasts by default** ✅

**Explanation:**
The **Smurf attack** relies on routers forwarding packets addressed to the
**directed broadcast address** (e.g., 192.168.1.255) to all hosts on that subnet.
**RFC 2644 (1999)** mandated that routers MUST disable directed broadcast
forwarding by default. Cisco IOS has had `no ip directed-broadcast` as the
default configuration since IOS 12.0 (1998). Without routers forwarding
directed broadcasts, the amplification mechanism simply doesn't work.

- **A)** — ❌ ICMP is still in active use in IPv4 networking
- **B)** — ✅ RFC 2644 (1999) — routers no longer forward directed broadcasts
- **C)** — ❌ Firewalls don't universally block all ICMP — and that's not the
  reason Smurf is dead
- **D)** — ❌ BCP38 prevents spoofing but many ASes still lack it — that's not
  why Smurf is dead

---

**Q14. Correct Answer: B) Each SYN is only ~40–60 bytes — the damage is to
the TCP STATE TABLE (backlog queue), not to available bandwidth** ✅

**Explanation:**
**SYN Floods** are **Protocol attacks** (Layer 3/4) — NOT volumetric. Each SYN
packet is approximately 40–60 bytes. Even at high rates, SYN Flood traffic is
relatively low bandwidth. The damage is to the **TCP backlog queue** — each SYN
causes the kernel to allocate a TCB (Transmission Control Block) entry. When the
backlog fills, ALL new connection attempts (including legitimate ones) are dropped.
A 100 Mbps SYN flood can overwhelm a server with a 10 Gbps link because the
bottleneck is state entries, not bandwidth.

- **A)** — ❌ SYN packets are not encrypted — no extra processing for encryption
- **B)** — ✅ State table exhaustion — not bandwidth saturation
- **C)** — ❌ SYN Floods target any TCP service — not DNS exclusively
- **D)** — ❌ SYN uses TCP — and the protocol issue is about state, not
  the transport protocol

---

**Q15. Correct Answer: B) Without spoofing, the attacker's real IP receives
the SYN-ACK and the OS auto-sends RST — immediately freeing the backlog slot** ✅

**Explanation:**
This is the critical mechanism:
- **Without spoofing:** Target sends SYN-ACK to attacker's real IP → attacker's
  OS receives it → OS automatically sends RST (no application connection was opened)
  → target's kernel removes the backlog entry → attack fails because slots are
  freed faster than they're filled
- **With spoofing:** Target sends SYN-ACK to a spoofed IP → that host ignores or
  RSTs it (it never sent a SYN) → target waits **75 seconds** for the ACK →
  backlog slot is consumed for the full timeout window → attack succeeds

Spoofing converts a 75-second delay into a persistent state exhaustion attack.

- **A)** — ❌ Firewall logs capture source IPs but that's about attribution, not
  attack effectiveness
- **B)** — ✅ Without spoofing, automatic RST frees backlog slots — defeating the attack
- **C)** — ❌ Spoofing doesn't change packet size
- **D)** — ❌ ICMP responses are about UDP floods — not SYN Flood mechanics

---

**Q16. Correct Answer: B) SYN Cookies — the server encodes connection state
in the ISN instead of allocating a TCB, eliminating state storage for
unverified connections** ✅

**Explanation:**
`net.ipv4.tcp_syncookies=1` enables **SYN Cookies** on Linux. With SYN Cookies:
1. Server receives SYN → does NOT allocate a TCB
2. Encodes a special hash into the SYN-ACK's **Initial Sequence Number (ISN)**: timestamp + MSS + client IP/port + secret key
3. **Forgets the connection entirely** — zero state stored
4. When a legitimate client sends the final ACK (containing ISN+1), the server reconstructs and verifies the connection from the ISN
5. Only then is a TCB allocated

Spoofed SYNs never send the final ACK → no state is ever allocated → SYN flood has zero effect on the backlog queue.

- **A)** — ❌ ICMP rate limiting is a separate UDP flood defense — not syncookies
- **B)** — ✅ SYN Cookies encode state in ISN — no TCB allocated until ACK verified
- **C)** — ❌ syncookies doesn't implement rate limiting — it eliminates state storage
- **D)** — ❌ Blackhole routing is a completely different mechanism

---

**Q17. Correct Answer: D) The Initial Sequence Number (ISN)** ✅

**Explanation:**
SYN Cookies encode the connection information into the **Initial Sequence Number
(ISN)** of the SYN-ACK response. The ISN is a 32-bit field in the TCP header.
The encoding includes: timestamp (5 bits), MSS index (3 bits), HMAC of client
IP/port, server IP/port, and timestamp (24 bits). When the final ACK arrives,
ACK number = ISN + 1 — the server reconstructs the ISN from ACK-1 and verifies
the hash to confirm the connection was legitimate.

- **A) TCP Checksum** — ❌ Checksum is for error detection — not state encoding
- **B) IP TTL** — ❌ TTL decrements at each hop — can't reliably store state
- **C) TCP Source Port** — ❌ Source port identifies the client — not a free field
- **D) ISN** — ✅ Initial Sequence Number encodes the SYN Cookie state

---

**Q18. Correct Answer: B) The traffic is VALID HTTP — legitimate-looking
requests that pass through firewalls and IDS as normal user traffic** ✅

**Explanation:**
**Application layer attacks** send valid, well-formed HTTP requests to real
endpoints. There is nothing syntactically wrong with the packets — no invalid
flags, no spoofed IPs, no malformed headers. A WAF's basic rules see normal
GET and POST requests. Volumetric alerts don't trigger because bandwidth is
low. Firewall sees TCP connections on port 80/443 completing normally. The attack
is only detectable through behavioral analysis — request rate per IP, completion
rates, client characteristics, session patterns.

- **A)** — ❌ App-layer attacks use VERY LOW bandwidth — their danger is
  low detectability, not high volume
- **B)** — ✅ Valid HTTP traffic passes all basic security controls
- **C)** — ❌ App-layer attacks target the victim's web application directly
- **D)** — ❌ App-layer DDoS doesn't use zero-days — it abuses normal functionality

---

**Q19. Correct Answer: D) Nginx** ✅

**Explanation:**
**Nginx** uses an **event-driven, asynchronous architecture** — a small number of
worker processes each handle thousands of connections using non-blocking I/O.
Idle connections (like Slowloris's partial HTTP connections) consume minimal
resources — just a small event loop entry. Nginx can maintain millions of idle
connections simultaneously without degrading performance.

**Apache** uses a **thread-per-connection model** — each connection, even an idle
partial one, permanently occupies a worker thread from the thread pool. When all
threads are consumed by Slowloris connections, no new threads are available for
legitimate requests.

- **A) Apache** — ❌ Apache IS vulnerable — thread-per-connection = Slowloris kills it
- **B) IIS** — ❌ IIS is partially vulnerable
- **C) Tomcat** — ❌ Tomcat (in default configuration) uses a similar threading model
- **D) Nginx** — ✅ Event-driven — immune to Slowloris

---

**Q20. Correct Answer: B) Apache uses a THREAD-PER-CONNECTION model — each
slow connection permanently holds one thread until the request completes or
times out** ✅

**Explanation:**
Apache allocates **one worker thread per active connection**. The thread pool is
finite (default MaxRequestWorkers = 256 in Apache 2.4). A Slowloris connection
holds its thread indefinitely — sending just enough data to prevent timeout.
When all 256 threads are occupied by partial Slowloris connections, Apache cannot
spawn new threads for legitimate users. At < 1 Mbps total bandwidth, one machine
can exhaust the entire thread pool.

- **A)** — ❌ Slowloris doesn't exploit a buffer overflow — it abuses connection
  handling timeout behavior
- **B)** — ✅ Thread-per-connection = finite thread pool = Slowloris exhausts all threads
- **C)** — ❌ Slowloris doesn't modify files — it only holds network connections
- **D)** — ❌ Apache's default connection limit is much higher than 10 — the attack
  exhausts the thread pool, not a tiny connection limit

---

**Q21. Correct Answer: B) Declares a very large Content-Length then transmits
the POST body ONE BYTE AT A TIME** ✅

**Explanation:**
**RUDY (R-U-Dead-Yet)** targets POST body handling. It sends a POST request
declaring a large `Content-Length` (e.g., 1,000,000 bytes), then transmits the
body one byte every 10 seconds. The server has committed to receiving the full
declared body — it cannot reject the connection without violating HTTP semantics.
At 1 byte per 10 seconds, a 1 MB body takes ~10 million seconds (~115 days) —
the connection slot is held effectively forever.

- **A)** — ❌ Invalid Content-Type would cause the server to reject the request
  immediately — not hold it open
- **B)** — ✅ Large Content-Length + one byte at a time = connection held indefinitely
- **C)** — ❌ URG flag in POST headers is not how RUDY works — it's an HTTP attack
- **D)** — ❌ Empty POST floods are HTTP Floods — not the RUDY slow-body technique

---

**Q22. Correct Answer: B) Volumetric → Upstream Scrubbing/Anycast ·
Protocol → SYN Cookies/BCP38 · App → WAF/Behavioral Analysis** ✅

**Explanation:**
Each DDoS category requires a fundamentally different defense because they attack
different resources:

| Category | Attack Target | Primary Defense |
|---|---|---|
| Volumetric | Bandwidth | Upstream scrubbing, Anycast diffusion |
| Protocol | State tables | SYN Cookies, stateless ACLs, BCP38 |
| Application | CPU/memory/DB | WAF, CAPTCHA, behavioral analysis, CDN |

A WAF is useless against a 1 Tbps UDP flood. SYN Cookies don't help against
HTTP Floods. Deploying the wrong defense wastes time and money.

- **A)** — ❌ WAF+CAPTCHA is application defense — applying it to volumetric fails
- **B)** — ✅ Correct mapping of defense to attack category
- **C)** — ❌ Defense assignments are incorrectly matched
- **D)** — ❌ A single firewall cannot defend against all DDoS categories — this
  is the most common misconception

---

**Q23. Correct Answer: B) It drops ALL traffic to the victim IP — including
legitimate traffic — so the service remains unavailable even though the attack
is "stopped"** ✅

**Explanation:**
**Blackhole Routing (RTBH)** instructs routers to drop ALL packets destined for
the victim's IP address at the ISP edge. Attack traffic is discarded — but so
is ALL legitimate user traffic. The victim's service is still completely
inaccessible. The attacker effectively achieves their goal (service unavailable)
through this countermeasure. RTBH is used only when the attack volume threatens
to overwhelm upstream infrastructure affecting OTHER customers — it protects the
ISP at the cost of the victim's service availability.

- **A)** — ❌ RTBH is a routing announcement — no special hardware required
- **B)** — ✅ Drops ALL traffic including legitimate — service remains down
- **C)** — ❌ RTBH drops all IP traffic regardless of protocol (TCP and UDP)
- **D)** — ❌ RTBH can be implemented unilaterally by a single ISP with BGP communities

---

**Q24. Correct Answer: B) Anycast routes each bot to a nearby PoP — the
attack is distributed across all locations, with each absorbing only a
fraction of total volume** ✅

**Explanation:**
**Anycast** announces the same IP address from multiple geographic PoPs
simultaneously. BGP routing directs each packet to the nearest PoP. During a
DDoS, attack traffic from bots in different regions naturally distributes across
all PoPs. A 500 Gbps attack against Cloudflare-protected infrastructure gets
distributed across 200+ PoPs — each handling only ~2.5 Gbps — well within the
scrubbing capacity at each location. No single location sees the full attack volume.

- **A)** — ❌ Anycast doesn't encrypt traffic
- **B)** — ✅ Geographic distribution of attack traffic — each PoP absorbs a fraction
- **C)** — ❌ Anycast doesn't rotate IP addresses — it routes the SAME IP to multiple
  locations
- **D)** — ❌ Anycast doesn't add extra hops that drop packets

---

**Q25. Correct Answer: C) IoT devices (cameras, DVRs, routers) compromised
via default credentials** ✅

**Explanation:**
The **October 2016 Dyn DNS attack** used the **Mirai botnet** — composed almost
entirely of **IoT devices** including IP cameras (primarily Xiongmai-brand),
digital video recorders (DVRs), and home routers. All were compromised by Mirai
via **default credential brute force** on Telnet (ports 23/2323). Approximately
100,000 compromised IoT devices generated the ~1.2 Tbps peak that took down
Dyn DNS and indirectly caused outages for Twitter, Netflix, Reddit, GitHub,
PayPal, Spotify, and dozens of other services.

- **A)** — ❌ Mirai targeted consumer IoT — not enterprise servers
- **B)** — ❌ Mirai spread via Telnet credential brute force — not phishing
- **C)** — ✅ IoT devices (cameras, DVRs, routers) via default credentials
- **D)** — ❌ Mirai used existing compromised devices — not rented cloud VMs

---

**Q26. Correct Answer: B) It blocks ALL amplification attacks by preventing
IP spoofing at the ISP level — without spoofing, the victim cannot be set
as the "source" for reflected traffic** ✅

**Explanation:**
Every reflection/amplification attack relies on the same mechanism: the attacker
forges the **victim's IP** as the source IP in requests sent to reflectors.
Without this spoofing, reflectors would send their amplified responses back to
the ATTACKER — not the victim. **BCP38/uRPF** blocks outbound packets whose
source IP doesn't belong to the originating network, making spoofing impossible
at the ISP edge. If universal, BCP38 would eliminate ALL reflection/amplification
attacks simultaneously — DNS Amp, NTP Monlist, Memcached, Smurf — all in one
countermeasure.

- **A)** — ❌ BCP38 doesn't prevent access to open DNS resolvers
- **B)** — ✅ No spoofing = no reflection possible = all amplification attacks fail
- **C)** — ❌ BCP38 doesn't limit DNS response sizes
- **D)** — ❌ BCP38 is about source address validation — not UDP rate limiting

---

**Q27. Correct Answer: C) Section 66F — Cyberterrorism** ✅

**Explanation:**
**IT Act 2000 Section 66F** covers **Cyberterrorism** — actions that threaten
the unity, integrity, sovereignty, or security of India, or that attack critical
infrastructure. DDoS attacks against critical infrastructure (banking, power
grids, defense systems, government services) fall under this section. The penalty
is imprisonment up to **LIFE** — the most severe penalty in the IT Act.

For context:
- S. 43 — Civil compensation for unauthorized access (no criminal penalty)
- S. 66 — General computer offenses — up to 3 years + ₹5 lakh
- **S. 66F — Cyberterrorism — up to LIFE imprisonment**

- **A) S. 43** — ❌ Civil compensation — no criminal imprisonment
- **B) S. 66** — ❌ 3 years — applies to general hacking offenses
- **C) S. 66F** — ✅ Cyberterrorism — critical infrastructure DDoS — up to life
- **D) S. 67** — ❌ Publishing obscene content — completely different offense

---

**Q28. Correct Answer: C) A SYN Flood is in progress — most SYNs have
spoofed IPs and never complete the handshake, consuming backlog queue entries** ✅

**Explanation:**
In normal TCP traffic, almost every SYN is followed by a SYN-ACK and an ACK —
the handshake completes. A **SYN:SYN-ACK ratio of 200:1** means 200 SYN packets
arrive for every 1 that results in a SYN-ACK being sent. This indicates that:
1. The server IS sending SYN-ACKs (it's responding to the flood)
2. But 199 out of 200 connections never complete the handshake
3. The backlog queue is filling with half-open connections
4. This is the signature pattern of an active SYN Flood

A 200:1 ratio is an extreme anomaly that immediately warrants investigation and
SYN Cookie activation.

- **A)** — ❌ Normal peak traffic still completes handshakes — the ratio would be
  close to 1:1
- **B)** — ❌ Outbound bandwidth saturation would show large response packets — not
  an anomalous SYN:SYN-ACK ratio
- **C)** — ✅ 200:1 SYN:SYN-ACK ratio = most SYNs spoofed, never completing
- **D)** — ❌ HTTP Flood would show completed TCP connections and valid HTTP — not
  anomalous SYN ratios

---

**Q29. Correct Answer: C) Switch to an application-layer attack (HTTP Flood
or Slowloris) that passes through scrubbing as "legitimate" low-bandwidth
traffic** ✅

**Explanation:**
A **2026 AI-adaptive botnet** monitors defense responses and changes attack
vectors to maximize disruption. If a volumetric UDP flood is absorbed by upstream
scrubbing, the scrubbing center is correctly identifying and filtering high-volume
attack traffic. The logical adaptation: switch to an **application-layer attack**
(HTTP Flood, Slowloris) that:
1. Uses very low bandwidth — doesn't trigger volumetric thresholds
2. Contains valid HTTP — passes scrubbing as "clean" traffic
3. Reaches the origin server directly
4. Requires a completely different defense response

This is the 2026 multi-vector attack reality: defenders must activate different
playbooks simultaneously or the adaptive botnet simply switches to the undefended
attack surface.

- **A)** — ❌ Increasing volume against an already-absorbing scrubbing center
  wastes resources — the scrubbing capacity isn't the bottleneck
- **B)** — ❌ Waiting 24 hours is not what AI-adaptive botnets do — they adapt
  in real-time
- **C)** — ✅ Switch to low-bandwidth app-layer attack that bypasses scrubbing
- **D)** — ❌ More reflectors increase the same volumetric attack type — which
  the scrubbing center is already successfully absorbing

---

**Q30. Correct Answer: C) Large number of HTTP connections in ESTABLISHED
state with very low bytes transferred and near-zero completion rate** ✅

**Explanation:**
**T1499.003 (Application Exhaustion — Slowloris/RUDY)** is characterized by:
- Connections that **ESTABLISH** normally (SYN → SYN-ACK → ACK completes)
- Then transfer **very few bytes** over a long period (sending just enough to
  prevent timeout)
- Near-zero **request completion rate** (partial headers never finish)
- Normal or low bandwidth

The SIEM alert: many connections in ESTABLISHED state on port 80/443 where the
HTTP request has been in progress for > 30–60 seconds with < 100 bytes transferred.
This is abnormal — legitimate browsers complete headers in < 1 second.

- **A)** — ❌ High inbound bandwidth is the signature of T1498 VOLUMETRIC attacks —
  not T1499.003 which is specifically low-bandwidth
- **B)** — ❌ High SYN:SYN-ACK ratio is the signature of T1499.001 SYN Flood
- **C)** — ✅ ESTABLISHED connections + very low bytes + no completion = Slowloris/RUDY
- **D)** — ❌ High ICMP Destination Unreachable from server = responding to a UDP
  Flood — completely different attack type

---

## Quick Answer Key

| Q | Answer | Q | Answer | Q | Answer |
|---|---|---|---|---|---|
| Q1 | B | Q11 | B | Q21 | B |
| Q2 | C | Q12 | D | Q22 | B |
| Q3 | B | Q13 | B | Q23 | B |
| Q4 | C | Q14 | B | Q24 | B |
| Q5 | C | Q15 | B | Q25 | C |
| Q6 | C | Q16 | B | Q26 | B |
| Q7 | C | Q17 | D | Q27 | C |
| Q8 | D | Q18 | B | Q28 | C |
| Q9 | C | Q19 | D | Q29 | C |
| Q10 | C | Q20 | B | Q30 | C |

---

## Topic Coverage Map

| Q | Section | Concept Tested |
|---|---|---|
| Q1 | Section 1 | DoS vs DDoS — fundamental distinction |
| Q2 | Section 1 | Six components — Botmaster never sends traffic directly |
| Q3 | Section 1 | Six components — Reflectors definition |
| Q4 | Section 2 | Botnet lifecycle — Rallying stage |
| Q5 | Section 2 | Botnet lifecycle — Mirai infection method (default creds) |
| Q6 | Section 2 | C2 models — Centralized single point of failure |
| Q7 | Section 2 | C2 models — DGA (Conficker) |
| Q8 | Section 2 | C2 models — P2P most difficult to take down |
| Q9 | Section 3 | DDoS categories — Volumetric (bandwidth, Gbps/Tbps) |
| Q10 | Section 3 | Volumetric — UDP Flood (ICMP Unreachable CPU exhaustion) |
| Q11 | Section 3 | Volumetric — DNS Amplification factor (28–54×) |
| Q12 | Section 3 | Volumetric — Memcached amplification (51,000×, GitHub 2018) |
| Q13 | Section 3 | Protocol — Smurf attack dead since RFC 2644 (1999) |
| Q14 | Section 3 | Protocol — SYN Flood = state table, not bandwidth |
| Q15 | Section 3 | Protocol — Why spoofing is critical to SYN Flood |
| Q16 | Section 3 | Protocol — SYN Cookies (tcp_syncookies=1) |
| Q17 | Section 3 | Protocol — SYN Cookies encode state in ISN |
| Q18 | Section 3 | Application layer — hard to detect (valid HTTP) |
| Q19 | Section 3 | Application layer — Nginx immune to Slowloris |
| Q20 | Section 3 | Application layer — Apache thread-per-connection vulnerability |
| Q21 | Section 3 | Application layer — RUDY POST body byte-at-a-time |
| Q22 | Section 4 | Countermeasures — correct defense per category |
| Q23 | Section 4 | Countermeasures — Blackhole routing as last resort |
| Q24 | Section 4 | Countermeasures — Anycast diffusion mechanism |
| Q25 | Section 3 | Real-world — Dyn/Mirai (IoT default credentials, 1.2 Tbps) |
| Q26 | Section 4 | Countermeasures — BCP38 eliminates all amplification |
| Q27 | Section 6 | Legal — IT Act S. 66F (Cyberterrorism = life imprisonment) |
| Q28 | Section 3 | Detection — SYN:SYN-ACK ratio 200:1 = SYN Flood |
| Q29 | Section 6 | 2026 context — AI-adaptive botnet vector switching |
| Q30 | Section 5 | MITRE ATT&CK — T1499.003 Slowloris SIEM detection |

---