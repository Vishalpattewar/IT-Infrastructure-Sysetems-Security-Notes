# 🕵️ MCQ Set — Session 11B

**Module:** Security Concepts — Ethical Hacking
**Coverage:** IP Spoofing · Enumeration (NetBIOS, SNMP, LDAP, DNS) ·
SMB Redirection & Relay MITM · NetBIOS DoS Attacks
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

**Q1.** IP Spoofing is possible because:

- A) The IPv4 protocol uses strong cryptographic verification of source IP addresses
- B) The IPv4 Source IP Address field is a 32-bit value that any raw socket can
   set to any value — routers do not verify source authenticity
- C) Modern firewalls automatically strip forged source IP addresses from all packets
- D) IPv4 mandates mutual authentication between sender and receiver before
   forwarding packets

---

**Q2.** In Blind IP Spoofing, what happens to the reply packets sent by the target?

- A) They are routed back to the attacker through a proxy tunnel
- B) They are stored on the target server until the attacker retrieves them
- C) They are sent to the FORGED source IP address — the attacker never sees them
- D) They are broadcast to all devices on the local network

---

**Q3.** In a Reflection/Amplification DDoS attack, the attacker forges the
SOURCE IP of which entity?

- A) The attacker's own IP — to hide from the reflectors
- B) The reflector servers' IPs — to confuse routing tables
- C) The VICTIM's IP — so all amplified responses are sent to the victim
- D) A random non-existent IP — so replies are dropped entirely

---

**Q4.** The 2018 GitHub DDoS attack used Memcached servers for amplification.
What was the approximate amplification factor in that attack?

- A) 10x
- B) 75x
- C) 51,000x
- D) 1,000,000x

---

**Q5.** Which countermeasure, if implemented by EVERY ISP globally, would
make IP spoofing functionally impossible?

- A) Deep Packet Inspection (DPI)
- B) IPsec tunnel mode on all internet traffic
- C) BCP38 / RFC 2827 egress filtering
- D) DNSSEC on all DNS servers

---

**Q6.** What is the FUNDAMENTAL difference between scanning (Session 10B) and
enumeration (Session 11B)?

- A) Scanning is passive while enumeration is active
- B) Scanning identifies OPEN PORTS; enumeration extracts the DATA those
   ports voluntarily provide — usernames, shares, routing tables
- C) Scanning requires authorization while enumeration does not
- D) Scanning uses NMAP while enumeration uses only Nessus

---

**Q7.** NetBIOS Name Service operates on which port and transport protocol?

- A) TCP 139
- B) UDP 137
- C) TCP 445
- D) UDP 161

---

**Q8.** During NetBIOS enumeration, a tester runs `nbtstat` and sees a name
registered with type code `[20]` and status UNIQUE. What does this indicate?

- A) The machine is a Domain Controller
- B) The machine has the Messenger service running — a user is logged in
- C) The machine has the File Server service active — it is sharing files via SMB
- D) The machine is the Master Browser for the network segment

---

**Q9.** Which NetBIOS type code identifies all Domain Controllers in the domain
(listed as a GROUP entry, maximum 25)?

- A) `[00]` UNIQUE
- B) `[20]` UNIQUE
- C) `[1C]` GROUP
- D) `[1B]` UNIQUE

---

**Q10.** SNMP versions 1 and 2c authenticate using community strings. What are
the DEFAULT community strings that ship with virtually every SNMP-enabled device?

- A) `"admin"` (read) and `"password"` (read-write)
- B) `"public"` (read) and `"private"` (read-write)
- C) `"read-only"` (read) and `"read-write"` (read-write)
- D) `"community"` (read) and `"secret"` (read-write)

---

**Q11.** An attacker runs `snmpwalk -v2c -c public [TARGET]` against a core
router. Which piece of intelligence from the MIB is MOST valuable for mapping
the entire network without scanning a single endpoint?

- A) sysDescr (OS version string)
- B) sysName (hostname)
- C) ipNetToMediaTable (ARP cache — all IP-MAC mappings of active hosts)
- D) sysUpTime (system uptime)

---

**Q12.** Which SNMP version provides actual security through username-based
authentication (MD5/SHA) and encryption (DES/AES)?

- A) SNMPv1
- B) SNMPv2c
- C) SNMPv3
- D) SNMPv2u

---

**Q13.** LDAP is the protocol used to query which Microsoft service that stores
all user, computer, group, and GPO objects in a Windows domain?

- A) Windows DNS
- B) Active Directory
- C) Internet Information Services (IIS)
- D) Windows Remote Desktop Services

---

**Q14.** LDAP operates on which standard port (unencrypted) and which port
for LDAP over SSL/TLS (LDAPS)?

- A) TCP 80 (LDAP) and TCP 443 (LDAPS)
- B) TCP 389 (LDAP) and TCP 636 (LDAPS)
- C) TCP 445 (LDAP) and TCP 3389 (LDAPS)
- D) TCP 161 (LDAP) and TCP 162 (LDAPS)

---

**Q15.** In Active Directory, which LDAP search filter returns all accounts that
have Service Principal Names — making them targets for Kerberoasting attacks?

- A) `(objectClass=user)`
- B) `(userAccountControl:1.2.840.113556.1.4.803:=65536)`
- C) `(servicePrincipalName=*)`
- D) `(objectClass=computer)`

---

**Q16.** Why is LDAP enumeration with even a LOW-PRIVILEGE domain user account
so powerful in most Active Directory environments?

- A) Low-privilege users have write access to all AD objects by default
- B) Low-privilege users can reset any user's password through LDAP
- C) AD is DESIGNED to be queryable by any authenticated user — even low-privilege
   accounts get FULL READ access to most AD objects
- D) Low-privilege users can modify Group Policy Objects through LDAP

---

**Q17.** Which tool graphically maps Active Directory relationships and
automatically computes attack paths from any user to Domain Admin?

- A) Nessus
- B) Wireshark
- C) BloodHound
- D) Burp Suite

---

**Q18.** A DNS zone transfer (AXFR) delivers which of the following to
the attacker?

- A) Only the A records for the primary domain
- B) A complete copy of ALL DNS records in the zone — every hostname, IP,
   MX, NS, CNAME, TXT, and PTR record
- C) Only the MX records identifying mail servers
- D) Only the NS records identifying DNS servers

---

**Q19.** What command would an attacker use to attempt a DNS zone transfer
against a specific DNS server?

- A) `nmap -sV company.com`
- B) `dig axfr company.com @[DNS_SERVER_IP]`
- C) `snmpwalk -v2c -c public company.com`
- D) `nbtstat -A company.com`

---

**Q20.** In NTLM challenge-response authentication, what is ACTUALLY transmitted
over the network?

- A) The user's plaintext password
- B) The user's NT hash (MD4 of the password)
- C) A challenge from the server and the client's hash-based response to that
   challenge — never the password or the raw hash
- D) The user's Kerberos ticket

---

**Q21.** SMB Relay attacks work because the attacker relays a valid NTLM
challenge-response pair to a different server in real time. What is the
SINGLE MOST EFFECTIVE countermeasure that prevents SMB Relay?

- A) Implementing complex password policies
- B) Enabling SMB Signing on ALL machines (not just Domain Controllers)
- C) Deploying antivirus on all endpoints
- D) Enabling Windows Firewall on all workstations

---

**Q22.** Responder is an industry-standard tool for capturing NTLM credentials.
It works by responding to which broadcast-based name resolution protocols?

- A) DNS and DHCP broadcasts
- B) NBNS (UDP 137), LLMNR (UDP 5355), and WPAD broadcasts
- C) ARP and ICMP broadcasts
- D) SNMP and LDAP queries

---

**Q23.** In the SMB Relay attack sequence, what critical condition must exist
on the TARGET server (the one the attacker relays authentication TO)?

- A) The target server must be running Linux
- B) SMB Signing must be DISABLED (or not required) on the target
- C) The target server must have SNMP enabled with default community strings
- D) The target server must be a Domain Controller

---

**Q24.** Which Windows Group Policy setting disables LLMNR — removing
one of the broadcast-based spoofing triggers used in SMB Relay?

- A) `Computer Config → Security Settings → Local Policies → Turn off LLMNR`
- B) `Computer Config → Admin Templates → Network → DNS Client → Turn off
   Multicast Name Resolution → ENABLED`
- C) `Computer Config → Windows Settings → Firewall → Block UDP 5355`
- D) `User Config → Admin Templates → Network → Disable Name Resolution`

---

**Q25.** In a NetBIOS DoS attack, an attacker continuously sends false NBNS
responses on the local network. What is the PRIMARY impact on Windows machines?

- A) All Windows machines immediately shut down
- B) Windows name resolution breaks — mapped drives disconnect, domain auth
   fails, and printer shares become unavailable
- C) All data on affected machines is encrypted by ransomware
- D) Windows machines lose their IP addresses and cannot reconnect

---

**Q26.** The NotPetya attack (2017) used NBNS flooding as a "disruption
multiplier." What was the approximate total damage caused by NotPetya globally?

- A) $1 million
- B) $100 million
- C) $1 billion
- D) $10 billion+

---

**Q27.** An organization wants to completely eliminate the NetBIOS attack
surface across all machines. Which approach provides the MOST comprehensive
solution?

- A) Install antivirus software on all machines
- B) Disable NetBIOS over TCP/IP on all adapters and use DHCP Option 001
   for network-wide enforcement
- C) Enable Windows Firewall on the Domain Controller only
- D) Change the default SNMP community string to a complex value

---

**Q28.** In a high-confidence SIEM detection rule for post-compromise
enumeration, which COMBINATION of activities from the SAME source IP within
30 minutes would indicate an attacker performing systematic enumeration?

- A) Multiple web page visits + email downloads + file prints
- B) NetBIOS scan (T1018) + SNMP walk (T1046) + LDAP query burst (T1087)
   from the same source
- C) DNS resolution + DHCP lease request + NTP time synchronization
- D) Single SSH login + one file download + logout

---
&nbsp;

&nbsp;

&nbsp;

---

## Answers & Explanations

---

**Q1. Correct Answer: B) The IPv4 Source IP Address field is a 32-bit value
that any raw socket can set to any value — routers do not verify source
authenticity** ✅

**Explanation:**
IPv4 was designed in RFC 791 (1981) for the trusted ARPANET. The Source IP
Address occupies bytes 12–15 of the IPv4 header — a simple 32-bit value with
NO protocol-level authenticity verification. When a router receives a packet,
it reads the DESTINATION IP for forwarding decisions and trusts the SOURCE IP
at face value. Any application with raw socket access can set the source IP
to any arbitrary value.

- **A)** — ❌ IPv4 has NO cryptographic verification of source addresses — this
  is the entire reason spoofing exists
- **B)** — ✅ Source IP is an unverified 32-bit field — routers trust it by default
- **C)** — ❌ Standard firewalls do NOT automatically strip forged source IPs —
  specific countermeasures like BCP38 must be explicitly configured
- **D)** — ❌ IPv4 has no mutual authentication — it was designed for a trusted
  academic network

---

**Q2. Correct Answer: C) They are sent to the FORGED source IP address — the
attacker never sees them** ✅

**Explanation:**
In Blind IP Spoofing, the attacker forges a source IP that is NOT their own.
When the target responds, it uses the (forged) source IP as the destination for
replies. The replies travel to the forged IP — the attacker has no way to
intercept them (unless they're on the LAN or control the forged IP's network).
This is why it's called "blind" — the attacker sends but cannot receive.

- **A)** — ❌ No proxy tunnel exists in blind spoofing — replies go to the forged IP
- **B)** — ❌ The target sends replies immediately — it doesn't store them
- **C)** — ✅ Replies go to forged source IP — attacker is blind to responses
- **D)** — ❌ Replies are unicast to the forged source IP — not broadcast

---

**Q3. Correct Answer: C) The VICTIM's IP — so all amplified responses are
sent to the victim** ✅

**Explanation:**
In a Reflection/Amplification DDoS attack, the attacker forges the **VICTIM's
IP address** as the source IP in requests sent to reflector servers (DNS resolvers,
NTP servers, Memcached servers). Each reflector generates a large response and
sends it to the "source" — which is the victim's IP. Thousands of reflectors
simultaneously sending large responses to the victim creates massive,
overwhelming traffic.

- **A)** — ❌ The attacker doesn't forge their OWN IP — that would send replies back
  to themselves and defeat the purpose
- **B)** — ❌ Forging the reflectors' IPs would cause them to send traffic to
  themselves — not useful for DDoS
- **C)** — ✅ Victim's IP forged as source → all amplified responses flood the victim
- **D)** — ❌ A non-existent IP would cause replies to be dropped — no DDoS effect

---

**Q4. Correct Answer: C) 51,000x** ✅

**Explanation:**
The **2018 GitHub DDoS attack** used Memcached servers as reflectors. The
attacker sent **203-byte requests** to Memcached servers with GitHub's IP forged
as the source. Memcached responded with **approximately 100KB responses** —
an amplification factor of roughly **51,000x**. The peak attack reached
**1.35 Tbps** — the largest DDoS attack recorded at that time. GitHub was
offline for approximately 10 minutes before Akamai Prolexic scrubbing absorbed
the traffic.

- **A) 10x** — ❌ Far too low — basic DNS amplification achieves ~75x
- **B) 75x** — ❌ 75x is the approximate factor for DNS amplification attacks —
  Memcached was exponentially worse
- **C) 51,000x** — ✅ Memcached amplification was approximately 51,000x
- **D) 1,000,000x** — ❌ No known amplification protocol reaches this factor

---

**Q5. Correct Answer: C) BCP38 / RFC 2827 egress filtering** ✅

**Explanation:**
**BCP38 (Best Current Practice 38) / RFC 2827** defines egress filtering: ISPs
should block outbound packets whose source IP address is NOT within the ISP's
assigned address range. If a packet from AS-12345 claims to have a source IP
belonging to AS-67890, the ISP drops it. If EVERY ISP globally implemented this,
no spoofed packet could ever leave its origin network — making IP spoofing
functionally impossible. However, approximately 25% of internet ASes still
don't implement BCP38 as of 2026.

- **A) DPI** — ❌ DPI inspects packet content — it doesn't validate source IP
  authenticity at the routing level
- **B) IPsec** — ❌ IPsec provides endpoint authentication — but requiring it on ALL
  internet traffic is impractical at global scale
- **C) BCP38** — ✅ Universal egress filtering = spoofing eliminated at the source
- **D) DNSSEC** — ❌ DNSSEC secures DNS responses — it has no bearing on IP-level
  spoofing

---

**Q6. Correct Answer: B) Scanning identifies OPEN PORTS; enumeration extracts
the DATA those ports voluntarily provide — usernames, shares, routing tables** ✅

**Explanation:**
This is a critical distinction:
- **Scanning** (Session 10B): "Port 445 is open running SMB" — identifies what
  EXISTS on the network (open ports, services, versions)
- **Enumeration** (Session 11B): "Users: administrator, jsmith, dbadmin.
  Shares: C$, ADMIN$, Finance. Password policy: 6 chars min" — extracts the
  MEANINGFUL DATA from those ports

Scanning finds the surface. Enumeration extracts actionable intelligence from it.

- **A)** — ❌ Both scanning and enumeration are active techniques — neither is passive
- **B)** — ✅ Scanning = open ports. Enumeration = data from those ports.
- **C)** — ❌ Both require authorization — enumeration is active and potentially more
  intrusive than scanning
- **D)** — ❌ Enumeration uses many tools (enum4linux, snmpwalk, ldapsearch, nbtscan)
  — not limited to Nessus

---

**Q7. Correct Answer: B) UDP 137** ✅

**Explanation:**
NetBIOS provides three services on three distinct ports:

| Service | Port | Transport |
|---|---|---|
| **Name Service (NBNS)** | **UDP 137** | UDP |
| Datagram Service | UDP 138 | UDP |
| Session Service | TCP 139 | TCP |

The Name Service on UDP 137 handles name registration and resolution —
it's the service that responds to `nbtstat` queries and broadcasts.

- **A) TCP 139** — ❌ TCP 139 is the NetBIOS Session Service (file/printer sharing)
- **B) UDP 137** — ✅ NetBIOS Name Service = UDP 137
- **C) TCP 445** — ❌ TCP 445 is SMB (direct, without NetBIOS encapsulation)
- **D) UDP 161** — ❌ UDP 161 is SNMP — completely different protocol

---

**Q8. Correct Answer: C) The machine has the File Server service active — it
is sharing files via SMB** ✅

**Explanation:**
NetBIOS type codes reveal specific services running on a machine:

| Type Code | Meaning |
|---|---|
| `[00]` UNIQUE | Workstation service — machine is active |
| `[03]` UNIQUE | Messenger service — user logged in |
| **`[20]` UNIQUE** | **File Server service — sharing files via SMB** |
| `[1D]` UNIQUE | Master Browser |
| `[1B]` UNIQUE | Domain Master Browser (PDC) |
| `[1C]` GROUP | Domain Controllers |

Type code `[20]` UNIQUE specifically indicates the **File Server service** is
registered — meaning the machine is actively sharing files and is a target for
share enumeration and data access.

- **A)** — ❌ Domain Controllers are identified by type code `[1C]` GROUP
- **B)** — ❌ Messenger service (user logged in) is type code `[03]` UNIQUE
- **C)** — ✅ `[20]` UNIQUE = File Server service = SMB file sharing active
- **D)** — ❌ Master Browser is type code `[1D]` UNIQUE

---

**Q9. Correct Answer: C) `[1C]` GROUP** ✅

**Explanation:**
NetBIOS type code **`[1C]` with GROUP type** represents the list of **Domain
Controllers** in the domain. This GROUP entry can contain up to 25 IP addresses
of Domain Controllers. For an attacker, Domain Controllers are the highest-priority
targets because compromising a DC gives full domain control (DCSync, Golden
Ticket, etc.).

- **A) `[00]` UNIQUE** — ❌ Workstation service — indicates machine is active
- **B) `[20]` UNIQUE** — ❌ File Server service — indicates SMB sharing active
- **C) `[1C]` GROUP** — ✅ Domain Controllers — list of all DCs (up to 25)
- **D) `[1B]` UNIQUE** — ❌ Domain Master Browser — the PDC that maintains the
  browse list (not the same as listing all DCs)

---

**Q10. Correct Answer: B) `"public"` (read) and `"private"` (read-write)** ✅

**Explanation:**
Virtually every SNMPv1 and SNMPv2c device ships with **`"public"`** as the
default read-only community string and **`"private"`** as the default read-write
community string. These are transmitted in plaintext. 2024 surveys indicate that
**30–40% of enterprise devices** still use these defaults in production.

`"public"` = anyone can query every MIB variable on the device.
`"private"` = anyone can CHANGE the device's configuration.

- **A)** — ❌ `"admin"/"password"` are common web interface defaults — not SNMP
- **B)** — ✅ `"public"` (read) and `"private"` (read-write) — universal SNMP defaults
- **C)** — ❌ Not the standard default community strings
- **D)** — ❌ Not the standard default community strings

---

**Q11. Correct Answer: C) ipNetToMediaTable (ARP cache — all IP-MAC mappings
of active hosts)** ✅

**Explanation:**
The **ARP cache** of a core router or Layer 3 switch contains a mapping of
**every active host** on all connected subnets — both IP and MAC address. A
single SNMP query against the `ipNetToMediaTable` (OID 1.3.6.1.2.1.4.22)
provides a complete live host inventory without scanning a single endpoint
directly. This is one of the most efficient reconnaissance techniques available
— "network topology via SNMP."

- **A) sysDescr** — ❌ Useful (reveals OS version) but only describes the SNMP
  device itself — doesn't map the network
- **B) sysName** — ❌ Reveals hostname of the device — useful but limited
- **C) ipNetToMediaTable** — ✅ ARP cache = every active host's IP and MAC =
  complete network map from one query
- **D) sysUpTime** — ❌ System uptime is informational — no network mapping value

---

**Q12. Correct Answer: C) SNMPv3** ✅

**Explanation:**
SNMP version security progression:

| Version | Authentication | Encryption | Security |
|---|---|---|---|
| v1 | Community string (plaintext) | None | Insecure |
| v2c | Community string (plaintext) | None | Insecure |
| **v3** | **Username + MD5/SHA** | **DES/AES** | **Secure** |

**SNMPv3** introduced the User-based Security Model (USM) with three security
levels: noAuthNoPriv, authNoPriv, and **authPriv** (authentication + encryption).

- **A) SNMPv1** — ❌ Plaintext community strings — no real security
- **B) SNMPv2c** — ❌ Same plaintext community strings as v1 — added bulk
  operations but no security improvement
- **C) SNMPv3** — ✅ Username + SHA authentication + AES encryption
- **D) SNMPv2u** — ❌ SNMPv2u was an experimental version that never gained
  widespread adoption

---

**Q13. Correct Answer: B) Active Directory** ✅

**Explanation:**
**Active Directory (AD)** is Microsoft's directory service that stores ALL domain
objects: users, computers, groups, Group Policy Objects (GPOs), printers, and
organizational units. LDAP (Lightweight Directory Access Protocol) on ports
389/636 is the standard protocol used to query and manage AD. Every Windows
domain client and server uses LDAP to interact with Active Directory.

- **A) Windows DNS** — ❌ DNS uses port 53 — LDAP is not used to query DNS
- **B) Active Directory** — ✅ LDAP is the query protocol for Active Directory
- **C) IIS** — ❌ IIS is a web server — queried via HTTP/HTTPS, not LDAP
- **D) Remote Desktop Services** — ❌ RDS uses port 3389 (RDP) — not LDAP

---

**Q14. Correct Answer: B) TCP 389 (LDAP) and TCP 636 (LDAPS)** ✅

**Explanation:**
LDAP port assignments:

| Port | Service |
|---|---|
| **TCP 389** | LDAP (unencrypted) |
| **TCP 636** | LDAPS (LDAP over SSL/TLS) |
| TCP 3268 | Global Catalog (unencrypted) |
| TCP 3269 | Global Catalog over SSL |

- **A)** — ❌ TCP 80/443 are HTTP/HTTPS — web protocol ports
- **B)** — ✅ LDAP = TCP 389 · LDAPS = TCP 636
- **C)** — ❌ TCP 445 is SMB · TCP 3389 is RDP
- **D)** — ❌ TCP 161/162 are SNMP — completely different protocol

---

**Q15. Correct Answer: C) `(servicePrincipalName=*)`** ✅

**Explanation:**
A **Service Principal Name (SPN)** is registered on service accounts that run
applications (SQL Server, web servers, etc.) under domain accounts. The LDAP
filter `(servicePrincipalName=*)` returns all accounts with ANY SPN registered
— these are **Kerberoasting targets**. In a Kerberoasting attack, the attacker
requests a Kerberos service ticket for the SPN, then cracks the ticket offline
to recover the service account's password.

- **A) `(objectClass=user)`** — ❌ Returns all user objects — too broad, doesn't
  specifically identify Kerberoasting targets
- **B) `(userAccountControl:...=65536)`** — ❌ This filter identifies accounts with
  "password never expires" — useful but not Kerberoasting-specific
- **C) `(servicePrincipalName=*)`** — ✅ All accounts with SPNs = Kerberoasting targets
- **D) `(objectClass=computer)`** — ❌ Returns computer objects — not service accounts

---

**Q16. Correct Answer: C) AD is DESIGNED to be queryable by any authenticated
user — even low-privilege accounts get FULL READ access to most AD objects** ✅

**Explanation:**
Active Directory was designed for applications like Outlook, SharePoint, and
other Microsoft services to query user information. By design, ANY authenticated
domain user — even the lowest-privilege account — has **read access** to virtually
the entire AD database: all users, computers, groups, Domain Controllers, password
policies, service accounts, and organizational structure. This is not a
misconfiguration — it's how AD is architected.

This is why compromising even ONE low-privilege domain account immediately gives
an attacker the intelligence to map the entire domain.

- **A)** — ❌ Low-privilege users have READ access — not WRITE access to all objects
- **B)** — ❌ Password reset is a privileged operation — low-privilege users cannot
  perform this
- **C)** — ✅ AD design gives authenticated users full READ access to most objects
- **D)** — ❌ GPO modification requires specific administrative privileges

---

**Q17. Correct Answer: C) BloodHound** ✅

**Explanation:**
**BloodHound** is the industry-standard tool for Active Directory relationship
mapping. It ingests data from LDAP enumeration and graphically visualizes all
relationships between users, computers, groups, sessions, and permissions.
Its most powerful feature: automatically computing the **shortest attack path**
from any compromised user to Domain Admin — showing exactly which accounts
and machines to target.

- **A) Nessus** — ❌ Nessus is a vulnerability scanner — it doesn't map AD
  relationship paths
- **B) Wireshark** — ❌ Wireshark captures network traffic — it doesn't analyze
  AD relationships
- **C) BloodHound** — ✅ AD relationship mapper + attack path calculator
- **D) Burp Suite** — ❌ Burp Suite is a web application proxy — not an AD tool

---

**Q18. Correct Answer: B) A complete copy of ALL DNS records in the zone —
every hostname, IP, MX, NS, CNAME, TXT, and PTR record** ✅

**Explanation:**
A **DNS Zone Transfer (AXFR)** is a legitimate mechanism for secondary DNS servers
to synchronize with the primary. If misconfigured to allow AXFR from ANY source,
an attacker receives a **complete copy of the entire zone** — every A, AAAA, MX,
NS, CNAME, TXT, SOA, and PTR record. This reveals all hostnames and their IP
addresses, including internal systems like Domain Controllers, payroll systems,
VPN endpoints, and legacy machines.

- **A)** — ❌ AXFR transfers ALL record types — not just A records
- **B)** — ✅ Complete zone copy — every record type in the zone
- **C)** — ❌ AXFR includes MX records but also ALL other record types
- **D)** — ❌ AXFR includes NS records but also ALL other record types

---

**Q19. Correct Answer: B) `dig axfr company.com @[DNS_SERVER_IP]`** ✅

**Explanation:**
The `dig` command with the `axfr` option requests a full zone transfer from the
specified DNS server:
- `dig` — DNS lookup utility (standard on Linux/macOS)
- `axfr` — request type: Authoritative Transfer (full zone copy)
- `company.com` — the domain zone to transfer
- `@[DNS_SERVER_IP]` — the specific DNS server to query

- **A)** — ❌ `nmap -sV` performs port scanning with service version detection —
  not DNS zone transfer
- **B)** — ✅ `dig axfr` is the standard command for DNS zone transfer requests
- **C)** — ❌ `snmpwalk` queries SNMP MIB — not DNS
- **D)** — ❌ `nbtstat` queries NetBIOS name tables — not DNS

---

**Q20. Correct Answer: C) A challenge from the server and the client's
hash-based response to that challenge — never the password or the raw hash** ✅

**Explanation:**
In NTLM challenge-response authentication:
1. Server sends an **8-byte random challenge**
2. Client computes: `NTLMv2 Response = HMAC-MD5(NT_Hash, challenge + username
   + domain + timestamp)`
3. Client sends: username + domain + NTLMv2 Response

The actual **password is never transmitted**. The **raw NT hash is never
transmitted**. Only the challenge-response pair crosses the wire. The server
validates by computing the same HMAC with its stored copy of the NT hash.

This design is precisely what enables SMB Relay — the attacker relays the
valid challenge-response WITHOUT ever knowing the password or hash.

- **A)** — ❌ Plaintext password is NEVER transmitted in NTLM — that would be
  the most basic security failure
- **B)** — ❌ The raw NT hash is NEVER transmitted — only the HMAC response
  computed FROM the hash is sent
- **C)** — ✅ Challenge + hash-based response only — no password or raw hash
- **D)** — ❌ Kerberos tickets are a different authentication protocol — NTLM
  does not use Kerberos tickets

---

**Q21. Correct Answer: B) Enabling SMB Signing on ALL machines (not just
Domain Controllers)** ✅

**Explanation:**
**SMB Signing** cryptographically signs each SMB packet using a session key
derived from the authentication. When SMB Signing is enabled and **required**,
the relay target verifies the signature on every packet. The attacker relayed
the authentication successfully, but they do NOT have the session key needed
to sign subsequent packets — so the relay fails after initial auth.

SMB Signing is enabled by default on **Domain Controllers** but **NOT on regular
workstations and member servers** — making them vulnerable. Enabling it on ALL
machines is the single most effective countermeasure.

- **A)** — ❌ Complex passwords don't prevent relay — the attacker never needs to
  know or crack the password
- **B)** — ✅ SMB Signing on ALL machines — prevents relay by requiring packet
  signatures the attacker cannot forge
- **C)** — ❌ Antivirus detects malware — it does not prevent network-level NTLM
  relay attacks
- **D)** — ❌ Windows Firewall may block some traffic but does not address the
  NTLM relay mechanism specifically

---

**Q22. Correct Answer: B) NBNS (UDP 137), LLMNR (UDP 5355), and WPAD
broadcasts** ✅

**Explanation:**
**Responder** captures NTLM credentials by poisoning three broadcast-based name
resolution protocols:
1. **NBNS (NetBIOS Name Service, UDP 137)** — legacy Windows name resolution
2. **LLMNR (Link-Local Multicast Name Resolution, UDP 5355)** — modern Windows
   fallback when DNS fails
3. **WPAD (Web Proxy Auto-Discovery)** — browsers requesting proxy configuration

When any Windows machine fails to resolve a name via DNS, it falls back to
broadcasting on these protocols. Responder answers every broadcast, claiming
to be the requested host, and captures the NTLM authentication that follows.

- **A)** — ❌ DNS and DHCP are not the protocols Responder primarily targets
- **B)** — ✅ NBNS + LLMNR + WPAD — the three broadcast protocols Responder poisons
- **C)** — ❌ ARP and ICMP are Layer 2/3 protocols — Responder targets application-layer
  name resolution
- **D)** — ❌ SNMP and LDAP are query protocols — not broadcast name resolution

---

**Q23. Correct Answer: B) SMB Signing must be DISABLED (or not required)
on the target** ✅

**Explanation:**
SMB Relay only works when the target server does NOT require SMB Signing.
If SMB Signing is required, the target expects every SMB packet to carry a
valid cryptographic signature. The attacker successfully relays the NTLM
authentication, but they lack the session key to sign subsequent packets —
the target rejects all unsigned packets after the initial auth exchange.

SMB Signing is enabled by default on Domain Controllers but **NOT** on regular
workstations and member servers — making them the primary relay targets.

- **A)** — ❌ SMB Relay targets Windows SMB — not Linux-specific
- **B)** — ✅ SMB Signing disabled = vulnerable to relay
- **C)** — ❌ SNMP status is irrelevant to SMB Relay
- **D)** — ❌ The target does NOT need to be a DC — any Windows machine with
  SMB Signing disabled is vulnerable. DCs typically HAVE signing enabled.

---

**Q24. Correct Answer: B) `Computer Config → Admin Templates → Network →
DNS Client → Turn off Multicast Name Resolution → ENABLED`** ✅

**Explanation:**
Disabling LLMNR through Group Policy requires navigating to:
`Computer Configuration → Administrative Templates → Network → DNS Client →
Turn off Multicast Name Resolution` and setting it to **ENABLED**.

Setting this to "Enabled" means the policy to TURN OFF multicast name resolution
is ACTIVE — LLMNR will be disabled on all machines that receive this GPO.

- **A)** — ❌ The path described doesn't match the actual GPO location
- **B)** — ✅ Correct GPO path for disabling LLMNR
- **C)** — ❌ Blocking UDP 5355 in the firewall is an alternative approach — but
  the question asks specifically about the Group Policy setting
- **D)** — ❌ This path doesn't exist and uses "User Config" — LLMNR is a
  computer-level setting, not user-level

---

**Q25. Correct Answer: B) Windows name resolution breaks — mapped drives
disconnect, domain auth fails, and printer shares become unavailable** ✅

**Explanation:**
NetBIOS DoS attacks flood the network with false NBNS responses containing
incorrect IP addresses for common network names. Windows machines trust the
first NBNS response received — so they receive wrong IPs for file servers,
Domain Controllers, and print servers. The result: all UNC path-based resources
fail (mapped drives, printer shares), domain authentication degrades, Group
Policy can't apply, and login scripts fail.

The critical insight: the IP network layer remains fully functional — but the
NAME RESOLUTION layer is poisoned, so Windows can't find anything by name.

- **A)** — ❌ NBNS DoS does not trigger machine shutdowns
- **B)** — ✅ Name resolution failure → drives, auth, printers all break
- **C)** — ❌ NBNS DoS is a disruption attack — not ransomware
- **D)** — ❌ IP addresses are assigned by DHCP — NBNS DoS doesn't affect IP assignment

---

**Q26. Correct Answer: D) $10 billion+** ✅

**Explanation:**
**NotPetya (June 2017)** is considered the most destructive cyberattack in
history with total damages exceeding **$10 billion**. Notable losses include
Maersk ($300 million), Merck, FedEx/TNT Express, and Mondelez. NotPetya combined
EternalBlue SMB exploitation with NBNS flooding as a disruption multiplier —
the NBNS component disrupted Windows name resolution across infected networks,
compounding the damage and impeding incident response efforts.

- **A) $1 million** — ❌ A single company's minor incident — not NotPetya scale
- **B) $100 million** — ❌ This is closer to single-company losses (MGM was $100M+)
- **C) $1 billion** — ❌ Understates the total global impact significantly
- **D) $10 billion+** — ✅ Total estimated global damages from NotPetya

---

**Q27. Correct Answer: B) Disable NetBIOS over TCP/IP on all adapters and use
DHCP Option 001 for network-wide enforcement** ✅

**Explanation:**
The most comprehensive approach to eliminating the NetBIOS attack surface is to
**disable NetBIOS over TCP/IP** entirely. This can be done:
- Per adapter: Network Adapter → IPv4 → Advanced → WINS → Disable NetBIOS
  over TCP/IP
- Network-wide: **DHCP Option 001** automatically configures all DHCP clients
  to disable NetBIOS — ensuring consistent enforcement across the entire network

Modern Active Directory does NOT require NetBIOS — DNS is the native name
resolution mechanism for AD. NetBIOS dependencies are legacy.

- **A)** — ❌ Antivirus doesn't address NetBIOS protocol-level attacks
- **B)** — ✅ Disable NetBIOS on all adapters + DHCP Option 001 for enforcement
- **C)** — ❌ Firewall on DC only leaves all other machines exposed — incomplete
- **D)** — ❌ SNMP community strings are a different protocol — irrelevant to
  NetBIOS

---

**Q28. Correct Answer: B) NetBIOS scan (T1018) + SNMP walk (T1046) + LDAP
query burst (T1087) from the same source** ✅

**Explanation:**
A legitimate administrator wouldn't simultaneously run `nbtscan`, `snmpwalk`,
and `ldapsearch` from the same machine within a 30-minute window. This pattern
— multiple enumeration techniques (T1018 Remote System Discovery + T1046
Network Service Discovery + T1087 Account Discovery) from a single source in
a compressed timeframe — is a strong indicator of **systematic post-compromise
enumeration** by an attacker mapping the environment.

Correlating multiple MITRE ATT&CK technique IDs from the same source provides
far higher detection confidence than alerting on any single technique.

- **A)** — ❌ Web browsing + email + printing is normal user behavior
- **B)** — ✅ Three different enumeration techniques from one source in 30 minutes
  = systematic attacker activity
- **C)** — ❌ DNS + DHCP + NTP are normal automated network functions
- **D)** — ❌ A single SSH session with one file operation is normal admin behavior

---

## Quick Answer Key

| Q | Answer | Q | Answer | Q | Answer |
|---|---|---|---|---|---|
| Q1 | B | Q11 | C | Q21 | B |
| Q2 | C | Q12 | C | Q22 | B |
| Q3 | C | Q13 | B | Q23 | B |
| Q4 | C | Q14 | B | Q24 | B |
| Q5 | C | Q15 | C | Q25 | B |
| Q6 | B | Q16 | C | Q26 | D |
| Q7 | B | Q17 | C | Q27 | B |
| Q8 | C | Q18 | B | Q28 | B |
| Q9 | C | Q19 | B | | |
| Q10 | B | Q20 | C | | |

---

## Topic Coverage Map

| Q | Section | Concept Tested |
|---|---|---|
| Q1 | Section 1 | IP Spoofing — why it is possible (no source verification) |
| Q2 | Section 1 | Blind IP Spoofing — reply destination (forged IP) |
| Q3 | Section 1 | Reflection/Amplification — victim's IP forged as source |
| Q4 | Section 1 | GitHub 2018 DDoS — Memcached amplification factor (51,000x) |
| Q5 | Section 1 | BCP38 / RFC 2827 — universal countermeasure |
| Q6 | Section 2 | Scanning vs Enumeration — fundamental distinction |
| Q7 | Section 2 | NetBIOS — Name Service port (UDP 137) |
| Q8 | Section 2 | NetBIOS type codes — `[20]` = File Server |
| Q9 | Section 2 | NetBIOS type codes — `[1C]` GROUP = Domain Controllers |
| Q10 | Section 2 | SNMP default community strings — "public" / "private" |
| Q11 | Section 2 | SNMP — ARP cache (ipNetToMediaTable) for network mapping |
| Q12 | Section 2 | SNMP versions — v3 security (USM, authPriv) |
| Q13 | Section 2 | LDAP — queries Active Directory |
| Q14 | Section 2 | LDAP ports — TCP 389 / TCP 636 |
| Q15 | Section 2 | LDAP filters — servicePrincipalName for Kerberoasting |
| Q16 | Section 2 | LDAP — AD design gives any auth user full READ access |
| Q17 | Section 2 | BloodHound — AD relationship mapping and attack paths |
| Q18 | Section 2 | DNS Zone Transfer — complete zone copy (all records) |
| Q19 | Section 2 | DNS Zone Transfer — dig axfr command |
| Q20 | Section 3 | NTLM — challenge-response (no password/hash transmitted) |
| Q21 | Section 3 | SMB Relay — SMB Signing as primary countermeasure |
| Q22 | Section 3 | Responder — NBNS/LLMNR/WPAD poisoning |
| Q23 | Section 3 | SMB Relay — SMB Signing disabled required on target |
| Q24 | Section 3 | LLMNR disable — GPO path |
| Q25 | Section 4 | NetBIOS DoS — impact (name resolution failure) |
| Q26 | Section 4 | NotPetya — $10 billion+ total damages |
| Q27 | Section 4 | NetBIOS countermeasure — disable + DHCP Option 001 |
| Q28 | Section 5 | SIEM detection — correlated enumeration techniques |

---