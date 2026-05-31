# Session 05 — Diffie-Hellman Key Exchange, Attacks Against
Encryption & Cryptographic Issues

## 📑 Table of Contents

- [1. Diffie-Hellman Key Exchange](#1-diffie-hellman-key-exchange)
  - [1.1 The Key Distribution Problem](#11-the-key-distribution-problem)
  - [1.2 What is Diffie-Hellman?](#12-what-is-diffie-hellman)
  - [1.3 DH Mathematical Foundation](#13-dh-mathematical-foundation)
  - [1.4 DH Key Exchange — Step by Step](#14-dh-key-exchange--step-by-step)
  - [1.5 DH Worked Example](#15-dh-worked-example)
  - [1.6 DH Security — Discrete Logarithm Problem](#16-dh-security--discrete-logarithm-problem)
  - [1.7 DH Variants](#17-dh-variants)
  - [1.8 DH in Real Protocols](#18-dh-in-real-protocols)
- [2. Attacks Against Encryption](#2-attacks-against-encryption)
  - [2.1 Attack Classification Framework](#21-attack-classification-framework)
  - [2.2 Brute Force Attack](#22-brute-force-attack)
  - [2.3 Dictionary Attack](#23-dictionary-attack)
  - [2.4 Rainbow Table Attack](#24-rainbow-table-attack)
  - [2.5 Man-in-the-Middle Attack](#25-man-in-the-middle-attack)
  - [2.6 Replay Attack](#26-replay-attack)
  - [2.7 Side-Channel Attacks](#27-side-channel-attacks)
  - [2.8 Cryptanalytic Attacks](#28-cryptanalytic-attacks)
  - [2.9 Protocol-Level Attacks](#29-protocol-level-attacks)
- [3. Cryptographic Issues](#3-cryptographic-issues)
  - [3.1 Key Management Issues](#31-key-management-issues)
  - [3.2 Implementation Weaknesses](#32-implementation-weaknesses)
  - [3.3 Algorithm Selection Issues](#33-algorithm-selection-issues)
  - [3.4 Randomness Issues](#34-randomness-issues)
  - [3.5 Password Storage Issues](#35-password-storage-issues)
  - [3.6 Certificate and PKI Issues](#36-certificate-and-pki-issues)
- [4. 📌 Extra Notes](#4--extra-notes)
  - [4.1 DH vs RSA Key Exchange — Full Comparison](#41-dh-vs-rsa-key-exchange--full-comparison)
  - [4.2 Station-to-Station Protocol (STS)](#42-station-to-station-protocol-sts)
  - [4.3 MITM Against Basic DH — Why Authentication Matters](#43-mitm-against-basic-dh--why-authentication-matters)
  - [4.4 Logjam Attack](#44-logjam-attack)
  - [4.5 FREAK Attack](#45-freak-attack)
  - [4.6 POODLE Attack](#46-poodle-attack)
  - [4.7 BEAST Attack](#47-beast-attack)
  - [4.8 CRIME and BREACH Attacks](#48-crime-and-breach-attacks)
  - [4.9 Padding Oracle Attack](#49-padding-oracle-attack)
  - [4.10 Downgrade Attacks](#410-downgrade-attacks)
  - [4.11 Salt — Why It Defeats Rainbow Tables](#411-salt--why-it-defeats-rainbow-tables)
  - [4.12 Password Hashing Functions Comparison](#412-password-hashing-functions-comparison)
  - [4.13 Cryptographic Agility](#413-cryptographic-agility)
  - [4.14 Export-Grade Cryptography — Historical Context](#414-export-grade-cryptography--historical-context)
- [5. Abbreviations Table](#5-abbreviations-table)
- [6. Keywords + Concept Map](#6-keywords--concept-map)
- [7. Quick Reference Cheatsheet](#7-quick-reference-cheatsheet)
- [8. Session Revision Snapshot](#8-session-revision-snapshot)

---

## 1. Diffie-Hellman Key Exchange

### 1.1 The Key Distribution Problem

Symmetric encryption requires both parties to share
a secret key BEFORE they can communicate securely.

**The fundamental question:**
> *How do two parties establish a shared secret key
> over an insecure channel — without ever having met?*

Before Diffie-Hellman, the only solutions were:
- Meet physically to exchange keys (impractical at scale)
- Use a trusted courier (expensive, risky)
- Use a Key Distribution Center — KDC (single point
  of failure, requires pre-shared keys with the KDC)

**Diffie-Hellman solved this problem in 1976.**

---

### 1.2 What is Diffie-Hellman?

**Diffie-Hellman (DH)** is a **key exchange protocol**
published by **Whitfield Diffie and Martin Hellman**
in **1976** — the paper was titled:
*"New Directions in Cryptography"*

> [!IMPORTANT]
> DH is a **key exchange protocol** — NOT an encryption
> algorithm and NOT a digital signature algorithm.
> It is used ONLY to establish a shared secret over
> an insecure channel. The shared secret is then used
> as a symmetric encryption key.
>
> MCQ trap: "DH encrypts messages" → **FALSE.**
> DH only establishes a shared key — encryption is
> done separately using that key.

**Historical note:**
Ralph Merkle independently developed a similar concept
(Merkle's Puzzles, 1974) but DH's mathematical approach
was more practical. The method was also independently
discovered by Malcolm Williamson at GCHQ in 1975 —
but kept classified until 1997.

---

### 1.3 DH Mathematical Foundation

DH security relies on the **Discrete Logarithm
Problem (DLP):**

```
Given: g, p (prime), and y = gˣ mod p
Find:  x

→ Computing y from g, x, p is EASY (fast exponentiation)
→ Finding x from g, y, p is HARD (no efficient algorithm
  for large p)
```

**Public parameters (agreed openly, known to everyone
including attackers):**
- **p** — a large prime number (modulus)
- **g** — a primitive root modulo p (generator)
  - g is chosen such that g can generate all values
    from 1 to p-1 by taking powers mod p

> [!NOTE]
> p and g are NOT secret. They are publicly known
> domain parameters. The security comes from the
> hardness of computing the discrete logarithm —
> not from keeping p and g secret.
>
> Common DH group parameters are standardized:
> - IETF RFC 3526 defines standard DH groups
> - Group 14 = 2048-bit prime (minimum recommended)
> - Group 16 = 4096-bit prime (high security)

---

### 1.4 DH Key Exchange — Step by Step

```
PUBLIC SETUP (known to everyone):
  p = large prime
  g = generator (primitive root mod p)

─────────────────────────────────────────────

ALICE:                        BOB:
Choose private key a           Choose private key b
(random, kept secret)          (random, kept secret)

Compute public value:          Compute public value:
A = gᵃ mod p                  B = gᵇ mod p

─────────────────────────────────────────────

         Alice sends A to Bob →
         ← Bob sends B to Alice

─────────────────────────────────────────────

ALICE computes shared secret:  BOB computes shared secret:
S = Bᵃ mod p                  S = Aᵇ mod p
S = (gᵇ)ᵃ mod p               S = (gᵃ)ᵇ mod p
S = gᵃᵇ mod p                 S = gᵃᵇ mod p

         SAME SHARED SECRET S = gᵃᵇ mod p ✅

─────────────────────────────────────────────

ATTACKER sees: p, g, A, B
To find S: needs to find a from A = gᵃ mod p
           OR b from B = gᵇ mod p
           → Both require solving DLP → infeasible
```

---

### 1.5 DH Worked Example

**Small numbers for illustration (not secure):**

```
Public parameters:
  p = 23  (prime)
  g = 5   (primitive root mod 23)

Alice chooses: a = 6 (private)
Bob chooses:   b = 15 (private)

Alice computes public value:
  A = 5⁶ mod 23 = 15625 mod 23 = 8
  (Alice sends 8 to Bob)

Bob computes public value:
  B = 5¹⁵ mod 23 = 30517578125 mod 23 = 19
  (Bob sends 19 to Alice)

Alice computes shared secret:
  S = 19⁶ mod 23 = 47045881 mod 23 = 2

Bob computes shared secret:
  S = 8¹⁵ mod 23 = 35184372088832 mod 23 = 2

Shared Secret S = 2  ✅ (both get same value)

Attacker sees: p=23, g=5, A=8, B=19
To find a: needs 5ᵃ mod 23 = 8 → solve for a
           → a = 6, but finding this for
             large p is computationally infeasible
```

> [!NOTE]
> In real DH, p is at least **2048 bits** long
> (~617 decimal digits). The discrete logarithm
> problem for such large values is computationally
> infeasible with current technology.

---

### 1.6 DH Security — Discrete Logarithm Problem

**The Computational Diffie-Hellman (CDH) Problem:**
Given gᵃ mod p and gᵇ mod p — compute gᵃᵇ mod p
without knowing a or b.

**The Decisional Diffie-Hellman (DDH) Problem:**
Given gᵃ, gᵇ, and a third value Z — decide whether
Z = gᵃᵇ mod p or Z is random.

**DH Parameter Requirements:**

| Parameter | Requirement | Reason |
|-----------|-------------|--------|
| **p (prime)** | ≥ 2048 bits | Small p → DLP solvable |
| **g (generator)** | Primitive root mod p | Ensures full group order |
| **a, b (private keys)** | Large random integers | Small private keys → vulnerable |
| **p-1 structure** | p-1 should have a large prime factor | Prevents Pohlig-Hellman attack |

> [!IMPORTANT]
> DH with weak parameters (small p, small subgroup)
> is vulnerable to the **Logjam attack** (2015) —
> covered in Extra Notes 4.4.

---

### 1.7 DH Variants

| Variant | Full Name | Key Feature | Status |
|---------|-----------|-------------|--------|
| **DH** | Diffie-Hellman | Original — discrete log over Zp | ✅ Secure (2048-bit+) |
| **DHE** | DH Ephemeral | New key pair per session → PFS | ✅ Recommended |
| **ECDH** | Elliptic Curve DH | DH on elliptic curves — shorter keys | ✅ Modern standard |
| **ECDHE** | ECDH Ephemeral | New EC key pair per session → PFS | ✅ TLS 1.3 mandatory |
| **MTI** | Menezes-Qu-Vanstone | Authenticated DH variant | ⚠️ Specialized |
| **STS** | Station-to-Station | DH + digital signatures (see 4.2) | ✅ Solves MITM |

**Ephemeral DH (DHE/ECDHE):**
- Non-ephemeral DH: same private keys reused across
  sessions → no PFS
- Ephemeral DH: fresh random private keys per session
  → each session's key is independent
  → **Perfect Forward Secrecy (PFS)**

> [!IMPORTANT]
> **TLS 1.3 mandates ECDHE** — all static DH and RSA
> key transport cipher suites were removed.
> TLS 1.3 cipher suites all use ECDHE for key exchange
> → PFS is mandatory in TLS 1.3.

---

### 1.8 DH in Real Protocols

| Protocol | DH Variant Used | Purpose |
|----------|----------------|---------|
| **TLS 1.2** | DHE or ECDHE (optional) | Session key establishment |
| **TLS 1.3** | ECDHE (mandatory) | Session key establishment + PFS |
| **SSH** | ECDH / DH group exchange | Session key establishment |
| **IPSec / IKE** | DH groups (Group 14+) | VPN session key establishment |
| **Signal Protocol** | ECDH (X25519) | End-to-end encrypted messaging |
| **WhatsApp** | ECDH (X25519) | End-to-end encrypted messaging |
| **PGP** | ECDH or DH | Session key for email encryption |

---

## 2. Attacks Against Encryption

### 2.1 Attack Classification Framework

Attacks against encryption can be organized by:

**By what the attacker targets:**

```
Attacks Against Encryption
│
├── Cryptanalytic Attacks (attack the algorithm)
│   ├── Brute Force
│   ├── Dictionary Attack
│   ├── Known/Chosen Plaintext
│   ├── Differential Cryptanalysis
│   └── Linear Cryptanalysis
│
├── Implementation Attacks (attack the implementation)
│   ├── Side-Channel (timing, power, EM)
│   ├── Fault Injection
│   └── Cache-Timing
│
├── Protocol Attacks (attack the protocol)
│   ├── Man-in-the-Middle
│   ├── Replay Attack
│   ├── Downgrade Attack
│   ├── Padding Oracle
│   └── POODLE, BEAST, CRIME, FREAK
│
└── Social/Operational Attacks (attack key management)
    ├── Key Theft
    ├── Password Attacks
    └── Rainbow Table
```

---

### 2.2 Brute Force Attack

**Definition:** Systematically trying every possible
key in the key space until the correct key is found.

| Property | Detail |
|----------|--------|
| **Type** | Cryptanalytic — exhaustive search |
| **Success guaranteed?** | ✅ Yes — eventually |
| **Time required** | Depends entirely on key size |
| **Countermeasure** | Use sufficiently large keys (AES-128+) |

**Brute force feasibility:**

| Key Size | Keys | Feasibility (modern hardware) |
|----------|------|-------------------------------|
| 40-bit | 2⁴⁰ ≈ 1 trillion | Seconds |
| 56-bit (DES) | 2⁵⁶ ≈ 72 quadrillion | Hours (Deep Crack, 1998) |
| 64-bit | 2⁶⁴ | Days–Months |
| 128-bit (AES) | 2¹²⁸ | Computationally infeasible |
| 256-bit (AES) | 2²⁵⁶ | Infeasible even with quantum computers |

> [!NOTE]
> A **brute force attack on AES-128** using all the
> energy of the sun converted to computation would
> take longer than the age of the universe.
> This is why AES-128 is considered secure against
> brute force — but AES-256 is recommended when
> post-quantum threats are considered (Grover's
> algorithm halves effective key length to 128 bits).

---

### 2.3 Dictionary Attack

**Definition:** Instead of trying all possible keys/
passwords, an attacker uses a pre-compiled list of
likely passwords (a "dictionary") to try common words,
phrases, and variations.

| Property | Detail |
|----------|--------|
| **Target** | Passwords and passphrases |
| **Speed** | Much faster than brute force |
| **Weakness exploited** | Human tendency to use predictable passwords |
| **Countermeasure** | Strong random passwords + salted hashing |

**Dictionary attack variants:**

| Variant | Description |
|---------|-------------|
| **Basic dictionary** | Wordlist of common passwords |
| **Rule-based** | Apply transformations (P@ssw0rd, p4ssword) |
| **Hybrid** | Dictionary words + appended numbers/symbols |
| **Credential stuffing** | Use leaked username/password pairs from other breaches |

**Common wordlists used:**
- **rockyou.txt** — 14 million passwords from 2009
  RockYou breach — standard in penetration testing
- **SecLists** — curated collection of wordlists
- **CrackStation** — 1.5 billion word list

---

### 2.4 Rainbow Table Attack

**Definition:** A rainbow table is a pre-computed
lookup table mapping passwords to their hash values.
An attacker with a stolen hash database can look up
the hash to find the original password — instantly.

**How it works:**
```
Pre-computation phase (done once):
  password1 → Hash → h1
  password2 → Hash → h2
  password3 → Hash → h3
  ...millions of entries stored in table

Attack phase (instant lookup):
  Stolen hash: h2 → look up in table → password2 ✅
```

**Rainbow table vs brute force:**

| Method | Pre-computation | Attack speed | Storage |
|--------|----------------|-------------|---------|
| Brute force | None | Slow — compute hashes live | None |
| Rainbow table | Very high (one time) | Instant lookup | Very high |

> [!IMPORTANT]
> **Rainbow tables are defeated by SALT.**
> A salt is a random value appended to the password
> before hashing — making pre-computation useless
> because the table would need to be rebuilt for
> every unique salt.
> See Extra Notes 4.11 for full salt explanation.

---

### 2.5 Man-in-the-Middle Attack

**Definition:** An attacker secretly intercepts and
relays communications between two parties — each
believing they are communicating directly with the
other.

```
WITHOUT MITM:
Alice ←──────────────────────────→ Bob

WITH MITM:
Alice ←──→ [Mallory/Attacker] ←──→ Bob
  Alice thinks she's talking to Bob
  Bob thinks he's talking to Alice
  Mallory sees and can modify ALL traffic
```

**MITM against DH key exchange (unauthenticated DH):**
```
Alice sends A = gᵃ mod p to Bob
  Mallory intercepts A → sends her own M₁ = gᵐ¹ mod p
  to Bob

Bob sends B = gᵇ mod p to Alice
  Mallory intercepts B → sends her own M₂ = gᵐ² mod p
  to Alice

Result:
  Alice computes shared secret with MALLORY (not Bob)
  Bob computes shared secret with MALLORY (not Alice)
  Mallory decrypts both sides — re-encrypts and forwards

Neither Alice nor Bob can detect this.
```

**Why basic DH is vulnerable:**
DH provides **no authentication** — it establishes
a shared secret but does NOT verify who you are
talking to.

**Countermeasures:**

| Method | How |
|--------|-----|
| **Digital certificates** | Authenticate DH parameters using PKI |
| **Authenticated DH (STS)** | Sign DH public values with private key |
| **Pre-shared keys (PSK)** | Verify identity using previously shared secret |
| **Public key infrastructure** | CA-signed certificates verify identity |

---

### 2.6 Replay Attack

**Definition:** An attacker captures a valid
authenticated message/token and retransmits it later
to trick the system into accepting it as fresh.

```
Step 1: Alice sends valid login token T to Bob's server
Step 2: Mallory captures T during transmission
Step 3: Mallory replays T to Bob's server later
Step 4: Server accepts T — Mallory gains access
```

**Countermeasures:**

| Method | How It Works |
|--------|-------------|
| **Nonce (Number used Once)** | Server includes a unique random value in each challenge — must be in response |
| **Timestamps** | Message includes timestamp — server rejects if too old (e.g., > 5 minutes) |
| **Sequence numbers** | Each message has an incrementing number — duplicates rejected |
| **Session tokens** | One-time-use tokens invalidated after single use |

> [!NOTE]
> **Kerberos** uses timestamps to prevent replay attacks
> — tickets have a short validity window (default 5
> minutes). This is why Kerberos requires synchronized
> clocks (NTP) across all systems.

---

### 2.7 Side-Channel Attacks

**Definition:** Attacks that exploit physical
information leaked by a cryptographic implementation
rather than attacking the algorithm mathematically.

**Types of side-channel attacks:**

| Attack | Information Leaked | Example |
|--------|-------------------|---------|
| **Timing attack** | Time taken for cryptographic operations | RSA private key recovery from decryption timing |
| **Power analysis** | Power consumption during operations | Smart card key extraction |
| **Electromagnetic (EM)** | EM radiation from device | TEMPEST attacks — reading screen from EM emissions |
| **Acoustic** | Sound produced during operations | RSA key extraction from laptop fan noise |
| **Cache-timing** | CPU cache access patterns | Flush+Reload attacks on AES |
| **Fault injection** | Inducing errors (voltage glitching) | Extracting keys by causing intentional computation errors |

**Simple Power Analysis (SPA) vs Differential
Power Analysis (DPA):**

| Type | Method |
|------|--------|
| **SPA** | Single power trace analysis — identify operations from power signature |
| **DPA** | Statistical analysis of many power traces — extract key bit by bit |

> [!NOTE]
> **AES-NI (hardware AES instructions)** provides
> protection against cache-timing side-channel attacks
> in addition to performance benefits — because
> hardware AES operates in constant time regardless
> of input values.

**Countermeasures:**
- Constant-time implementations (no data-dependent
  branching or timing)
- Hardware shielding
- Random delays / noise injection
- Blinding (randomize intermediate values)

---

### 2.8 Cryptanalytic Attacks

These target the mathematical structure of the
algorithm itself.

| Attack | Description | Historically Broke |
|--------|-------------|-------------------|
| **Differential Cryptanalysis** | Studies how differences in plaintext pairs affect ciphertext pairs — works with chosen plaintexts | DES (theoretically), many block ciphers |
| **Linear Cryptanalysis** | Finds linear approximations between plaintext, ciphertext, and key bits | DES (Matsui, 1993 — reduced rounds) |
| **Algebraic attack** | Express cipher as system of equations and solve | Some stream ciphers |
| **Integral / Square attack** | Used against AES-like SPN ciphers | Reduced-round AES |
| **Related-key attack** | Exploit relationships between different keys | AES-192/256 (theoretical, reduced rounds) |
| **Slide attack** | Exploit self-similar round structure | Ciphers with identical rounds |

**Differential cryptanalysis (Biham & Shamir, 1990):**
```
Chosen plaintext pairs (P, P') with known difference:
  ΔP = P XOR P' (fixed)

Observe resulting ciphertext pairs (C, C'):
  ΔC = C XOR C'

Statistical analysis of (ΔP → ΔC) patterns
→ Recover key bits

NSA knew about this in 1974 (before DES was published)
→ DES S-Boxes were secretly designed to resist it
```

> [!IMPORTANT]
> **AES has no known practical cryptanalytic attack
> on full-round AES** — only reduced-round theoretical
> attacks exist. Full AES-128 (10 rounds) has never
> been broken.

---

### 2.9 Protocol-Level Attacks

| Attack | Target | What It Exploits |
|--------|--------|-----------------|
| **POODLE** | SSL 3.0 / TLS CBC | CBC padding in SSL 3.0 |
| **BEAST** | TLS 1.0 CBC | Predictable IV in TLS 1.0 CBC |
| **CRIME** | TLS compression | Compression ratio leaks plaintext |
| **BREACH** | HTTP compression | Same as CRIME but at HTTP layer |
| **FREAK** | TLS | Export-grade cipher downgrade |
| **Logjam** | TLS DHE | Weak DH parameters downgrade |
| **ROBOT** | TLS RSA | Bleichenbacher padding oracle |
| **Heartbleed** | OpenSSL | Buffer over-read (not crypto) |
| **DROWN** | TLS | SSLv2 exposure of TLS keys |

> [!NOTE]
> All major protocol attacks are covered in detail
> in the 📌 Extra Notes section below.
> These are high-frequency MCQ topics.

---

## 3. Cryptographic Issues

### 3.1 Key Management Issues

The majority of real-world cryptographic failures
are not due to broken algorithms — they are due
to poor **key management.**

| Issue | Description | Example |
|-------|-------------|---------|
| **Key exposure** | Private/secret key accidentally revealed | Private key committed to GitHub repository |
| **Weak key generation** | Keys generated with weak randomness | Using PRNG instead of CSPRNG |
| **Key reuse** | Same key used for multiple purposes or sessions | OTP key reuse, ECDSA nonce reuse |
| **No key rotation** | Keys never changed — long exposure window | Same TLS cert key for 10 years |
| **Insecure key storage** | Keys stored in plaintext | Keys in config files, environment variables |
| **No key revocation** | Compromised keys not revoked quickly | Certificate not revoked after private key theft |
| **Hardcoded keys** | Keys embedded in source code | API keys and crypto keys in mobile apps |

> [!IMPORTANT]
> **Real breach examples:**
> - **Uber (2016):** AWS secret keys hardcoded in
>   GitHub repo → 57 million records exposed
> - **Sony PS3 (2010):** ECDSA nonce k reused → 
>   private key recovered
> - **Heartbleed (2014):** OpenSSL memory leak exposed
>   TLS private keys from server memory

---

### 3.2 Implementation Weaknesses

Even a mathematically perfect algorithm fails if
implemented incorrectly.

| Weakness | Description | Consequence |
|----------|-------------|-------------|
| **Reusing IV/Nonce** | Same IV with same key in CBC/CTR mode | Reveals XOR of plaintexts |
| **No padding validation** | Missing check on RSA/CBC padding | Padding oracle attacks |
| **Using ECB mode** | Identical blocks → identical ciphertext | Pattern leakage — ECB penguin |
| **Truncated MACs** | Shorter MAC for performance | Birthday attack feasibility increases |
| **Comparing MACs insecurely** | Early exit on first mismatch | Timing oracle attack |
| **Rolling own crypto** | Custom-designed algorithms | Almost always weaker than standards |
| **Missing certificate validation** | Accepting any cert | Vulnerable to MITM |
| **Using MD5/SHA-1 for security** | Broken hash functions | Collision attacks practical |

---

### 3.3 Algorithm Selection Issues

| Issue | Wrong Choice | Right Choice |
|-------|-------------|-------------|
| **Symmetric cipher** | DES, 3DES, RC4 | AES-128/256 with GCM |
| **Asymmetric cipher** | RSA-1024 | RSA-2048+ or ECC P-256+ |
| **Hash function** | MD5, SHA-1 | SHA-256, SHA-3 |
| **Key exchange** | Static RSA, unauthenticated DH | ECDHE with certificates |
| **Password storage** | MD5, SHA-1, unsalted hashes | bcrypt, scrypt, Argon2 |
| **MAC algorithm** | MD5-based HMAC | HMAC-SHA-256 |
| **Random number** | PRNG (Math.random()) | CSPRNG (SecureRandom, /dev/urandom) |
| **Block cipher mode** | ECB | CBC with random IV, or GCM |

---

### 3.4 Randomness Issues

Cryptographic systems depend critically on
unpredictable random numbers for:
- Key generation
- IV/Nonce generation
- Session tokens
- ECDSA nonce (k)
- DH private keys

**Randomness failure categories:**

| Failure | Description | Real Example |
|---------|-------------|-------------|
| **PRNG seeded with timestamp** | Predictable seed → reproducible output | Early Netscape SSL (1995) |
| **Low-entropy boot** | Virtual machines/embedded devices have little entropy at startup | Debian OpenSSL bug (2008) — 32,767 possible keys |
| **Reused nonce** | Same nonce in ECDSA → private key recovery | Sony PS3 (2010) |
| **Biased output** | Statistical bias in random values | Some hardware RNGs |
| **Dual_EC_DRBG** | NSA-backdoored PRNG standard | NIST SP 800-90A (2006) — removed 2014 |

> [!IMPORTANT]
> **Debian OpenSSL Bug (2008):**
> A Debian developer removed a line of code that
> was flagged by memory debugging tools — not realizing
> it was providing entropy. The result: OpenSSL on
> Debian/Ubuntu generated keys from a pool of only
> 32,767 possible values instead of 2¹²⁸.
> All SSH keys, TLS keys generated on affected
> systems were predictable and needed to be regenerated.

---

### 3.5 Password Storage Issues

How passwords should NOT be stored vs how they SHOULD:

**❌ Wrong approaches:**

| Method | Problem |
|--------|---------|
| **Plaintext** | Immediate exposure if database breached |
| **Encrypted** | Encryption key can be stolen too |
| **Unsalted MD5** | Rainbow tables break instantly |
| **Unsalted SHA-1** | Rainbow tables + birthday attack feasible |
| **Unsalted SHA-256** | Still vulnerable to rainbow tables |
| **Fast hash (any)** | GPU can compute billions/second |

**✅ Correct approach — slow, salted hashing:**

| Function | Type | Key Feature | Recommended? |
|----------|------|-------------|-------------|
| **bcrypt** | Adaptive hash | Cost factor (work factor) — default 10 | ✅ Yes |
| **scrypt** | Memory-hard hash | Memory + CPU cost — resists ASICs | ✅ Yes |
| **Argon2** | Memory-hard hash | PHC winner (2015) — three variants | ✅ Best current |
| **PBKDF2** | Iterated hash | NIST-approved — used in WPA2, PKCS#5 | ✅ Acceptable |

**Why slow hashing matters:**

```
Fast hash (SHA-256):
  GPU can compute 10 billion hashes/second
  → 8-character password cracked in seconds

bcrypt (cost=12):
  ~250ms per hash computation
  → Same 8-character password: years

The slowness is the security feature.
```

> [!NOTE]
> **Argon2 variants:**
> - **Argon2d** — Data-dependent memory access (GPU resistant)
> - **Argon2i** — Data-independent (side-channel resistant)
> - **Argon2id** — Hybrid (recommended for password hashing)

---

### 3.6 Certificate and PKI Issues

| Issue | Description |
|-------|-------------|
| **Self-signed certificates** | No third-party verification — vulnerable to MITM |
| **Expired certificates** | Revoked trust — clients show errors |
| **Revocation not checked** | CRL/OCSP not validated — revoked certs still trusted |
| **Weak signing algorithm** | MD5/SHA-1 signed certs — forgeable |
| **Wrong domain** | Certificate CN/SAN doesn't match hostname |
| **Pinning bypass** | Certificate pinning misconfigured |
| **CA compromise** | DigiNotar (2011) — fraudulent certs for Google, CIA |
| **Wildcard abuse** | *.example.com used for unintended subdomains |

> [!NOTE]
> **DigiNotar breach (2011):**
> Dutch CA DigiNotar was compromised — attackers issued
> fraudulent certificates for google.com, cia.gov,
> mossad.gov.il, and others. Used to MITM Iranian
> Gmail users. DigiNotar was removed from all browser
> trust stores and went bankrupt. This is the canonical
> example of why CA security is critical to all of PKI.

---

## 4. 📌 Extra Notes

> [!NOTE]
> Everything in this section goes beyond the core
> syllabus but is directly MCQ-relevant. Cross-
> referenced from Stallings, RFC standards, and
> published security research.

---

### 4.1 DH vs RSA Key Exchange — Full Comparison

> [!NOTE]

| Property | DH Key Exchange | RSA Key Exchange |
|----------|----------------|-----------------|
| **How shared secret established** | Mathematical computation (gᵃᵇ mod p) | Client encrypts pre-master secret with server's RSA public key |
| **PFS possible?** | ✅ Yes — with DHE/ECDHE | ❌ No — static RSA has no PFS |
| **Authentication** | ❌ None by default — needs certificates | ✅ Server authenticated by RSA cert |
| **If private key stolen** | Past sessions safe (with DHE) | Past sessions decryptable |
| **Used in TLS 1.3?** | ✅ ECDHE — mandatory | ❌ RSA key transport removed |
| **Used in TLS 1.2?** | ✅ Optional (DHE/ECDHE) | ✅ Optional (static RSA) |

---

### 4.2 Station-to-Station Protocol (STS)

> [!NOTE]
> **STS** is an authenticated version of DH — it adds
> digital signatures to prevent MITM attacks against
> basic DH.

```
Basic DH vulnerability: No authentication
→ Attacker can substitute their own public values

STS solution: Each party signs their DH public value
with their long-term private key

Flow:
1. Alice sends: A = gᵃ mod p
2. Bob sends: B = gᵇ mod p, Sign(KR_Bob, A || B)
3. Alice verifies Bob's signature using Bob's public key
4. Alice sends: Sign(KR_Alice, A || B)
5. Bob verifies Alice's signature

Now both parties are authenticated AND have shared secret
→ MITM cannot substitute values without valid signatures
```

STS is the conceptual basis for:
- TLS handshake (certificate-authenticated DH)
- IKE (Internet Key Exchange) in IPSec

---

### 4.3 MITM Against Basic DH — Why Authentication Matters

> [!NOTE]

```
The fundamental rule:
  Key exchange ≠ Authentication

DH establishes a shared secret — but does NOT
tell you WHO you established it with.

Without authentication:
  Alice thinks she has a secure channel to Bob
  But actually has a secure channel to Mallory
  Who has a separate secure channel to Bob
  Mallory decrypts both sides invisibly

With authentication (certificates):
  Bob's DH public value is signed by a trusted CA
  Alice verifies the CA signature
  If Mallory substitutes her own value →
  She cannot forge a valid CA signature
  Alice's browser shows certificate error
```

> This is why HTTPS uses TLS certificates — not just
> for encryption, but for **authentication** of the
> server's identity before key exchange.

---

### 4.4 Logjam Attack

> [!NOTE]
> **Logjam (2015)** — discovered by a team of academic
> researchers (INRIA, Microsoft Research, others).

**What it is:**
A downgrade attack against TLS DHE cipher suites
that forces the use of 512-bit "export-grade" DH
parameters — which can be broken in hours.

**How it works:**
```
1. Attacker performs MITM on TLS handshake
2. Downgrades DHE key exchange to export-grade
   (512-bit DH parameters)
3. Attacker precomputes discrete logarithms for
   common 512-bit DH groups (only ~80 groups used
   by most servers)
4. Real-time DLP computation allows session decryption
```

**Impact:**
- Affected ~8% of the top 1 million HTTPS websites
- Affected government and military sites using
  512-bit export-grade DH
- NSA had likely been exploiting this against VPNs

**Fix:**
- Disable export-grade cipher suites
- Use DH parameters ≥ 2048-bit
- Use ECDHE instead of DHE

---

### 4.5 FREAK Attack

> [!NOTE]
> **FREAK (Factoring RSA Export Keys) — 2015**

**What it is:**
A downgrade attack that forces TLS to use
export-grade RSA keys (512-bit) — which can be
factored in hours on modern hardware.

**Historical context:**
- In the 1990s, US government mandated export-grade
  cryptography (≤512-bit RSA, ≤40-bit symmetric)
  for software exported outside the US
- These "export cipher suites" were never removed
  from many server implementations
- 15 years later, attackers exploited them

**How FREAK works:**
```
1. MITM attacker intercepts TLS ClientHello
2. Modifies it to request only export-grade RSA suites
3. Server (still supporting legacy export suites) agrees
4. Attacker factors the 512-bit RSA key (takes ~7 hours)
5. Decrypts and MITM the session
```

**Fix:** Disable all export-grade cipher suites.
Both Logjam and FREAK were consequences of US
**export-grade cryptography regulations** from the 1990s.

---

### 4.6 POODLE Attack

> [!NOTE]
> **POODLE (Padding Oracle On Downgraded Legacy
> Encryption) — October 2014**
> Discovered by Google security team
> (Bodo Möller, Thai Duong, Krzysztof Kotowicz).

**What it targets:** SSL 3.0

**How it works:**
```
1. Attacker forces TLS downgrade to SSL 3.0
   (via connection errors that trigger fallback)
2. SSL 3.0 uses CBC mode with undefined/random padding
3. Attacker exploits CBC padding oracle in SSL 3.0
4. Through ~256 requests per byte → recovers plaintext
   (cookies, session tokens)
```

**Impact:** Any secure cookie can be stolen by a
network attacker — full session hijacking.

**Fix:**
- Disable SSL 3.0 entirely (RFC 7568 — June 2015)
- Implement TLS_FALLBACK_SCSV to prevent downgrade

> [!NOTE]
> **POODLE for TLS (2014):** A variant was found that
> worked against TLS implementations that incorrectly
> applied SSL 3.0 padding rules — separate from the
> original SSL 3.0 attack.

---

### 4.7 BEAST Attack

> [!NOTE]
> **BEAST (Browser Exploit Against SSL/TLS) — 2011**
> Discovered by Thai Duong and Juliano Rizzo.

**What it targets:** TLS 1.0 CBC mode

**The vulnerability:**
TLS 1.0 uses the last ciphertext block of a message
as the IV for the next message — making the IV
predictable.

```
TLS 1.0 CBC:
  IV for block N+1 = Ciphertext of last block N
  → IV is predictable before the next message

Attacker who can control some plaintext and observe
ciphertext can make guesses about plaintext and verify
→ Chosen plaintext + predictable IV = CBC decryption
```

**Impact:** Session cookie recovery — full session
hijacking possible for a local network attacker.

**Fix:**
- Use TLS 1.2+ (random IV per record)
- Use AES-GCM instead of AES-CBC
- Implement RC4 as workaround (RC4 is a stream cipher
  — but RC4 was later broken too)

---

### 4.8 CRIME and BREACH Attacks

> [!NOTE]

#### CRIME (Compression Ratio Info-Leak Made Easy) — 2012
**Target:** TLS/SPDY compression (DEFLATE)

```
If TLS compresses the request (including headers +
secret cookie) before encrypting:
→ Ciphertext length reveals information about plaintext
→ Attacker controls part of the plaintext (HTTP request)
→ Guess parts of the secret cookie character by character:
   If guess is correct → compression ratio increases
   (matching strings compress better) → shorter ciphertext
→ Correct guess confirmed by shorter encrypted output
```

**Fix:** Disable TLS-level compression.
RFC 7540 (HTTP/2) prohibits TLS compression.

#### BREACH (Browser Reconnaissance and Exfiltration
via Adaptive Compression of Hypertext) — 2013

**Target:** HTTP response compression (gzip/deflate)
Similar to CRIME but works even without TLS compression
by exploiting HTTP body compression.

**Fix:** Disable HTTP compression for sensitive
responses, or use CSRF tokens that change per request.

---

### 4.9 Padding Oracle Attack

> [!NOTE]
> A **padding oracle** is any system that reveals
> whether a decrypted ciphertext has valid padding
> — either through an error message, different response
> time, or different response code.

**Why it's dangerous:**
```
CBC decryption:
  Plaintext block = Decrypt(Key, Ciphertext) XOR Previous_Ciphertext_Block

If you can modify the previous ciphertext block and
ask the server "is this valid padding?" (oracle):
→ You can recover plaintext one byte at a time
→ No encryption key needed
→ Works entirely from the oracle's yes/no responses

Cost: ~256 oracle queries per byte
      ~4096 queries for a 16-byte AES block
```

**Real examples:**
- **Bleichenbacher attack (1998)** — RSA PKCS#1 v1.5
- **POODLE** — SSL 3.0 padding oracle
- **Lucky Thirteen (2013)** — TLS CBC timing oracle
- **ROBOT (2017)** — RSA Bleichenbacher redux

**Fix:**
- Use **authenticated encryption** (AES-GCM) —
  reject modified ciphertext before decryption
- Constant-time padding validation
- Encrypt-then-MAC (not MAC-then-Encrypt)

---

### 4.10 Downgrade Attacks

> [!NOTE]
> A **downgrade attack** tricks two parties into using
> an older, weaker version of a protocol or cipher
> suite than they are both capable of.

```
Modern client (supports TLS 1.3) ←→ Modern server (TLS 1.3)

Attacker in the middle:
  Modifies ClientHello to say "I only support TLS 1.0"
  Server falls back to TLS 1.0
  Now attacker can exploit TLS 1.0 vulnerabilities
```

**Examples:**
- **POODLE** — downgrade to SSL 3.0
- **FREAK** — downgrade to export RSA
- **Logjam** — downgrade to export DH
- **DROWN** — downgrade to SSLv2

**Countermeasure:**
**TLS_FALLBACK_SCSV** (Signaling Cipher Suite Value)
— RFC 7507 (2015)
```
If a client is downgrading (retry after failure),
it includes TLS_FALLBACK_SCSV in its ClientHello.
If the server supports a higher version than requested,
it sends an "inappropriate fallback" alert and aborts.
→ Prevents intentional downgrade by MITM
```

---

### 4.11 Salt — Why It Defeats Rainbow Tables

> [!NOTE]

**What is a salt?**
A salt is a **random value** generated uniquely for
each user and appended (or prepended) to the password
before hashing.

```
WITHOUT SALT:
  hash("password") = 5f4dcc3b...  (same for all users)
  hash("password") = 5f4dcc3b...  (same result)
  → Rainbow table lookup: instant match

WITH SALT (unique per user):
  User A: salt = "xK9mP2"
  hash("xK9mP2" + "password") = a3f7c1...

  User B: salt = "7qR3nW"
  hash("7qR3nW" + "password") = d8b2e4...

  Same password → completely different hashes
  → Rainbow table for "password" is useless
  → Attacker must brute-force each account separately
```

**Salt requirements:**
- Must be **cryptographically random** (CSPRNG)
- Must be **unique per user** — never reuse salts
- Must be **stored alongside the hash** (not secret)
- Minimum **128-bit (16 bytes)** recommended

> [!IMPORTANT]
> A salt does NOT need to be secret.
> Its purpose is uniqueness — making pre-computation
> (rainbow tables) infeasible.
> **Pepper** = a secret value added in addition to
> salt — stored separately from the database
> (provides extra protection if DB is stolen but
> app server is not).

---

### 4.12 Password Hashing Functions Comparison

> [!NOTE]

| Function | Year | Type | Cost Factor | Memory-hard? | Recommended? |
|----------|------|------|-------------|-------------|-------------|
| **MD5** | 1992 | Fast hash | None | ❌ | ❌ Never |
| **SHA-1** | 1995 | Fast hash | None | ❌ | ❌ Never |
| **SHA-256** | 2001 | Fast hash | None | ❌ | ❌ Not for passwords |
| **bcrypt** | 1999 | Adaptive | Work factor (4–31) | ❌ | ✅ Yes |
| **PBKDF2** | 2000 | Iterated HMAC | Iterations | ❌ | ✅ Acceptable |
| **scrypt** | 2009 | Memory-hard | N, r, p params | ✅ | ✅ Yes |
| **Argon2id** | 2015 | Memory-hard | t, m, p params | ✅ | ✅ Best |

**PHC (Password Hashing Competition):**
- Run 2013–2015 by a panel of cryptographers
- Selected **Argon2** as the winner
- Argon2id is the recommended variant for password storage
- Argon2 is specified in RFC 9106 (2021)

---

### 4.13 Cryptographic Agility

> [!NOTE]
> **Cryptographic agility** is the ability of a system
> to easily switch between cryptographic algorithms
> without requiring a complete redesign.

**Why it matters:**
- Algorithms get broken over time (DES → 3DES → AES)
- Quantum computing will break RSA and ECC
- Systems need to migrate to PQC algorithms
- A cryptographically agile system can update its
  cipher suite without replacing all infrastructure

**How it is implemented:**
- Algorithm negotiation (TLS cipher suite negotiation)
- Configuration-driven algorithm selection
- Abstraction layers (HSM, crypto libraries)

**TLS as a model of crypto agility:**
```
TLS defines cipher suites — negotiated per connection:
  TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256
        │         │         │         │
  Key Exchange  Auth   Encryption   Hash
  (ECDHE)      (RSA)  (AES-128-GCM) (SHA-256)

Updating to post-quantum: swap ECDHE → CRYSTALS-Kyber
  while keeping the rest of the protocol intact
```

---

### 4.14 Export-Grade Cryptography — Historical Context

> [!NOTE]
> **Export-grade cryptography** refers to deliberately
> weakened cryptographic algorithms that the US
> government required for software exported outside
> the US during the 1990s (Crypto Wars).

**US export regulations (1990s):**

| Cipher | Export limit | Actual strength |
|--------|-------------|----------------|
| RSA | ≤512-bit | Factorable in hours (today) |
| DH | ≤512-bit | Discrete log in hours (today) |
| Symmetric | ≤40-bit | Brute-forceable in seconds |
| RC4 | ≤40-bit | Trivially broken |

**The Crypto Wars:**
- US government classified strong cryptography as
  munitions — export required Arms Export Control Act
- Phil Zimmermann was investigated for 3 years after
  publishing PGP (released internationally via Usenet)
- Regulations significantly relaxed in 1999–2000

**Modern impact:**
- FREAK and Logjam directly exploited export-grade
  cipher suites left in modern servers
- "Export" cipher suites were never fully removed
  from browser and server implementations
- Lesson: deliberately weakened cryptography
  for government access weakens everyone's security

---

## 5. Abbreviations Table

| Abbreviation | Full Form | One-Line Technical Meaning |
|---|---|---|
| DH | Diffie-Hellman | Key exchange protocol — establishes shared secret over insecure channel |
| DHE | Diffie-Hellman Ephemeral | DH with temporary keys per session — provides PFS |
| ECDH | Elliptic Curve Diffie-Hellman | DH using elliptic curve math — smaller keys |
| ECDHE | Elliptic Curve Diffie-Hellman Ephemeral | ECDH with temporary keys — mandatory in TLS 1.3 |
| DLP | Discrete Logarithm Problem | Hard math problem: find x given gˣ mod p — basis of DH security |
| CDH | Computational Diffie-Hellman | Given gᵃ,gᵇ — compute gᵃᵇ — DH security assumption |
| PFS | Perfect Forward Secrecy | Past sessions safe even if long-term key compromised |
| MITM | Man-in-the-Middle | Attacker secretly intercepts and relays communications |
| STS | Station-to-Station Protocol | Authenticated DH — signs DH public values to prevent MITM |
| POODLE | Padding Oracle On Downgraded Legacy Encryption | 2014 attack — forces SSL 3.0 fallback and exploits CBC padding |
| BEAST | Browser Exploit Against SSL/TLS | 2011 attack — exploits predictable IV in TLS 1.0 CBC |
| CRIME | Compression Ratio Info-Leak Made Easy | 2012 attack — exploits TLS compression length side-channel |
| BREACH | Browser Reconnaissance via Adaptive Compression | 2013 attack — exploits HTTP body compression |
| FREAK | Factoring RSA Export Keys | 2015 attack — forces export-grade 512-bit RSA downgrade |
| ROBOT | Return Of Bleichenbacher's Oracle Threat | 2017 rediscovery of Bleichenbacher padding oracle in TLS |
| SPA | Simple Power Analysis | Single power trace to identify crypto operations |
| DPA | Differential Power Analysis | Statistical analysis of many power traces to extract key |
| OTP | One-Time Password | Single-use authentication token |
| SCSV | Signaling Cipher Suite Value | TLS_FALLBACK_SCSV — prevents intentional protocol downgrade |
| PHC | Password Hashing Competition | Competition (2013–2015) that selected Argon2 as winner |
| KDC | Key Distribution Center | Trusted server that distributes session keys (used in Kerberos) |
| PSK | Pre-Shared Key | Secret value known to both parties before communication |
| PBKDF2 | Password-Based Key Derivation Function 2 | Iterated HMAC for password hashing — NIST-approved |

---

## 6. Keywords + Concept Map

| Term | Definition | Connections | Use Cases |
|------|-----------|-------------|-----------|
| **Diffie-Hellman** | Key exchange protocol — gᵃᵇ mod p shared secret | DLP security, DHE for PFS, ECDH for ECC | TLS, SSH, IPSec, Signal |
| **Discrete Logarithm Problem** | Find x given gˣ mod p — computationally hard | DH security, DSA, ElGamal | Foundation of DH security |
| **DHE** | Ephemeral DH — new keys per session | PFS, TLS 1.2 optional, TLS 1.3 mandatory | Secure session key establishment |
| **Brute Force** | Try every possible key | Key size defense, 2⁵⁶ DES broken | Demonstrates need for large keys |
| **Rainbow Table** | Pre-computed hash→password lookup | Defeated by salt, fast hashes vulnerable | Password database attacks |
| **Salt** | Unique random value per user added before hashing | Defeats rainbow tables, must be CSPRNG | Password storage security |
| **MITM** | Attacker relays between two parties | DH vulnerable without auth, certificates fix | Network attacks, TLS |
| **Replay Attack** | Captured valid message retransmitted | Nonce/timestamp/sequence counter defeats | Authentication protocols |
| **Side-Channel** | Exploit physical leakage (time/power/EM) | Timing, DPA, acoustic, cache | Smart cards, RSA timing |
| **Padding Oracle** | Server reveals valid/invalid padding | POODLE, Bleichenbacher, Lucky13 | CBC mode encryption |
| **Downgrade Attack** | Force weaker protocol/cipher | POODLE, FREAK, Logjam, DROWN | TLS handshake manipulation |
| **Crypto Agility** | System can swap algorithms without redesign | TLS cipher suites, PQC migration | Enterprise security planning |
| **Argon2id** | PHC-winning memory-hard password hash | scrypt, bcrypt, PBKDF2 comparison | Password storage best practice |
| **bcrypt** | Adaptive cost password hash (1999) | Work factor tunable, widely deployed | Web application auth |
| **TLS_FALLBACK_SCSV** | Prevents intentional TLS version downgrade | RFC 7507, POODLE mitigation | TLS security hardening |
| **Export cryptography** | Deliberately weakened crypto for US export | FREAK, Logjam, Crypto Wars | Historical attacks context |

---

## 7. Quick Reference Cheatsheet

### 🔸 Diffie-Hellman — Key Numbers

| Parameter | Value |
|-----------|-------|
| Published | 1976 |
| Authors | Whitfield Diffie + Martin Hellman |
| Paper | "New Directions in Cryptography" |
| Security basis | Discrete Logarithm Problem |
| Minimum key size | 2048-bit (NIST recommendation) |
| DH purpose | Key EXCHANGE only — not encryption, not signing |
| Ephemeral variant | DHE / ECDHE → provides PFS |
| TLS 1.3 | ECDHE mandatory |

---

### 🔸 DH Step Summary

```
Public: p (prime), g (generator)
Alice private: a  |  Bob private: b
Alice public:  A = gᵃ mod p (sent to Bob)
Bob public:    B = gᵇ mod p (sent to Alice)
Shared secret: S = Bᵃ mod p = Aᵇ mod p = gᵃᵇ mod p
```

---

### 🔸 Attacks — Quick Reference

| Attack | Year | Target | Exploits | Fix |
|--------|------|--------|---------|-----|
| BEAST | 2011 | TLS 1.0 CBC | Predictable IV | TLS 1.2+, GCM |
| CRIME | 2012 | TLS compression | Length side-channel | Disable compression |
| BREACH | 2013 | HTTP compression | Length side-channel | No secrets in compressed responses |
| POODLE | 2014 | SSL 3.0 | CBC padding oracle | Disable SSL 3.0 |
| FREAK | 2015 | TLS RSA | Export 512-bit RSA | Disable export suites |
| Logjam | 2015 | TLS DHE | Export 512-bit DH | 2048-bit DH params |
| ROBOT | 2017 | TLS RSA | Bleichenbacher padding | OAEP padding |

---

### 🔸 Password Storage — Right vs Wrong

| Approach | Status | Reason |
|----------|--------|--------|
| Plaintext | ❌ Never | Immediate exposure |
| MD5 (unsalted) | ❌ Never | Rainbow tables instant |
| SHA-256 (unsalted) | ❌ Never | Rainbow tables + fast |
| SHA-256 (salted) | ⚠️ Weak | Still fast — GPU cracks quickly |
| bcrypt | ✅ Good | Slow + adaptive cost |
| scrypt | ✅ Good | Memory-hard |
| Argon2id | ✅ Best | PHC winner — memory + CPU hard |
| PBKDF2 | ✅ Acceptable | NIST-approved — used in WPA2 |

---

### 🔸 Salt vs Pepper

| Property | Salt | Pepper |
|----------|------|--------|
| Purpose | Uniqueness per user | Extra secret factor |
| Secret? | ❌ No — stored with hash | ✅ Yes — stored separately |
| Scope | Per-user | Application-wide |
| Defeats | Rainbow tables | DB-only breach |
| Required? | ✅ Always | Optional extra layer |

---

### 🔸 Side-Channel Attack Types

| Type | Leaks | Example |
|------|-------|---------|
| Timing | Operation duration | RSA decryption timing → key bits |
| Power (SPA/DPA) | Power consumption | Smart card key extraction |
| EM | Electromagnetic radiation | TEMPEST — screen reading |
| Acoustic | Sound | RSA key from fan noise (Genkin 2014) |
| Cache-timing | CPU cache hits/misses | Flush+Reload on AES |

---

### 🔸 Replay Attack — Countermeasures

| Method | How It Prevents Replay |
|--------|----------------------|
| Nonce | Unique random value per challenge — must be in response |
| Timestamp | Reject messages older than N minutes |
| Sequence number | Reject duplicate sequence numbers |
| One-time token | Token invalidated after first use |

---

## 8. Session Revision Snapshot

### ⚡ TL;DR — 5 Bullets

- ✅ Diffie-Hellman (1976, Diffie + Hellman) is a key
  EXCHANGE protocol — security based on Discrete
  Logarithm Problem — NOT encryption, NOT signing
- ✅ Basic DH has no authentication — vulnerable to MITM;
  DHE/ECDHE adds ephemeral keys for PFS; STS adds
  digital signatures for authentication
- ✅ Rainbow tables are defeated by unique random salt
  per user; Argon2id is the current best-practice
  password hashing function (PHC winner 2015)
- ✅ Most real-world crypto failures are implementation
  issues — key reuse, IV reuse, weak randomness,
  padding oracle, downgrade attacks — not broken
  algorithms
- ✅ TLS 1.3 mandates ECDHE (PFS) and removed all
  export-grade, static RSA, and weak cipher suites;
  attacks like POODLE/BEAST/FREAK exploited old
  cipher suites that should have been disabled years ago

---

### 🎯 MCQ-Likely Concepts — Everything Examiners Love

| Concept | Why It's Tricky |
|---------|----------------|
| DH is key exchange ONLY — not encryption | Students say "DH encrypts data" — false |
| DH public params (p, g) are NOT secret | Security comes from DLP — not secret parameters |
| DHE/ECDHE → PFS; static DH → no PFS | "Ephemeral" is the key word for PFS |
| Salt is NOT secret — just unique | Many think salt must be secret like a key |
| Argon2id = PHC winner — NOT bcrypt | bcrypt is good but Argon2 is the current best |
| POODLE attacks SSL 3.0 — not TLS | Year: 2014, target: SSL 3.0 specifically |
| BEAST attacks TLS 1.0 — not SSL | Year: 2011, target: TLS 1.0 CBC predictable IV |
| CRIME exploits TLS compression | Not TLS protocol itself — compression side-channel |
| Downgrade prevented by TLS_FALLBACK_SCSV | RFC 7507 — specific mechanism name |
| DH discovered independently by Williamson (GCHQ) 1975 | Kept classified — Diffie-Hellman published 1976 |
| STS = authenticated DH | Adds signatures — fixes MITM on basic DH |
| Padding oracle = valid/invalid padding response | No key needed — just server response as oracle |
| Timing attack = side-channel — not cryptanalytic | Implementation attack, not algorithm attack |
| Export crypto regulations → FREAK + Logjam | 1990s US export limits caused 2015 attacks |
| Debian OpenSSL 2008 = only 32,767 possible keys | Randomness bug — not algorithmic weakness |

---

<details>
<summary>🔬 Lab — Session 05 (CrypTool)</summary>

**Lab file:** `3-Labs/lab-session-05-cryptool.md`

**Tool:** CrypTool (CrypTool 1 or CrypTool 2)

**Theory ↔ Lab Connection:**

| Theory Concept (Session 05) | What You See in CrypTool |
|-----------------------------|--------------------------|
| DH Key Exchange | DH protocol simulation — see shared secret derivation |
| Brute Force Attack | AES/DES brute force demonstration |
| Caesar/Vigenère (from Session 03) | Classic encrypt → frequency analysis |
| DES encryption | DES encrypt/decrypt — 56-bit key |
| AES encryption | AES-128/256 encrypt/decrypt |
| RSA encryption | RSA key generation + encrypt/decrypt |
| ECC | ECC key generation demonstration |
| RC4 stream cipher | RC4 encrypt/decrypt |
| Hash functions | MD5/SHA-1/SHA-256 computation |

> [!TIP]
> Complete Session 05 theory notes AND Session 06
> (SHA/HMAC) before attempting the full CrypTool lab
> — the lab covers hash functions too.

**Full step-by-step lab guide:**
`3-Labs/lab-session-05-cryptool.md`

</details>

---