# Session 03 — Cryptographic Fundamentals, Ciphers & Protocols

## 📑 Table of Contents

- [1. Cryptographic Fundamentals](#1-cryptographic-fundamentals)
  - [1.1 What is Cryptography?](#11-what-is-cryptography)
  - [1.2 Goals of Cryptography](#12-goals-of-cryptography)
  - [1.3 Modular Arithmetic](#13-modular-arithmetic)
  - [1.4 Prime Numbers in Cryptography](#14-prime-numbers-in-cryptography)
  - [1.5 GCD and Coprime Numbers](#15-gcd-and-coprime-numbers)
  - [1.6 XOR Operation](#16-xor-operation)
  - [1.7 One-Way Functions](#17-one-way-functions)
  - [1.8 Trapdoor Functions](#18-trapdoor-functions)
  - [1.9 P vs NP — Why Asymmetric Crypto is Hard to Break](#19-p-vs-np--why-asymmetric-crypto-is-hard-to-break)
  - [1.10 Random Number Generation](#110-random-number-generation)
  - [1.11 Avalanche Effect](#111-avalanche-effect)
- [2. Cryptographic Ciphers — Symmetric](#2-cryptographic-ciphers--symmetric)
  - [2.1 Symmetric Encryption — Core Model](#21-symmetric-encryption--core-model)
  - [2.2 Classical Symmetric Ciphers](#22-classical-symmetric-ciphers)
  - [2.3 Caesar Cipher — Deep Dive](#23-caesar-cipher--deep-dive)
  - [2.4 Vigenère Cipher](#24-vigenère-cipher)
  - [2.5 Vernam Cipher — One-Time Pad (OTP)](#25-vernam-cipher--one-time-pad-otp)
  - [2.6 Modern Symmetric Ciphers — Overview Map](#26-modern-symmetric-ciphers--overview-map)
- [3. Cryptographic Ciphers — Asymmetric](#3-cryptographic-ciphers--asymmetric)
  - [3.1 Asymmetric Encryption — Core Model](#31-asymmetric-encryption--core-model)
  - [3.2 How Key Pairs Work](#32-how-key-pairs-work)
  - [3.3 Asymmetric Use Cases — Encryption vs Signing](#33-asymmetric-use-cases--encryption-vs-signing)
  - [3.4 Modern Asymmetric Ciphers — Overview Map](#34-modern-asymmetric-ciphers--overview-map)
  - [3.5 Hybrid Encryption — Why We Use Both](#35-hybrid-encryption--why-we-use-both)
- [4. Cryptographic Protocols](#4-cryptographic-protocols)
  - [4.1 What is a Cryptographic Protocol?](#41-what-is-a-cryptographic-protocol)
  - [4.2 History of Cryptographic Protocols](#42-history-of-cryptographic-protocols)
  - [4.3 Protocol Usage and Purpose Map](#43-protocol-usage-and-purpose-map)
  - [4.4 Key Generation — How Keys Are Produced](#44-key-generation--how-keys-are-produced)
  - [4.5 Ciphering a Message — Step-by-Step Flow](#45-ciphering-a-message--step-by-step-flow)
- [5. 📌 Extra Notes](#5--extra-notes)
  - [5.1 Euler's Totient Function φ(n)](#51-eulers-totient-function-φn)
  - [5.2 Fermat's Little Theorem](#52-fermats-little-theorem)
  - [5.3 Discrete Logarithm Problem](#53-discrete-logarithm-problem)
  - [5.4 Integer Factorization Problem](#54-integer-factorization-problem)
  - [5.5 Elliptic Curve Discrete Logarithm Problem (ECDLP)](#55-elliptic-curve-discrete-logarithm-problem-ecdlp)
  - [5.6 Perfect Forward Secrecy (PFS)](#56-perfect-forward-secrecy-pfs)
  - [5.7 Birthday Paradox and Birthday Attack](#57-birthday-paradox-and-birthday-attack)
  - [5.8 Frequency Analysis — Attack on Classical Ciphers](#58-frequency-analysis--attack-on-classical-ciphers)
  - [5.9 Known Plaintext vs Chosen Plaintext Attacks](#59-known-plaintext-vs-chosen-plaintext-attacks)
  - [5.10 Feistel Cipher Structure](#510-feistel-cipher-structure)
  - [5.11 Symmetric vs Asymmetric — Complete Comparison](#511-symmetric-vs-asymmetric--complete-comparison)
  - [5.12 Classical vs Modern Ciphers — Comparison](#512-classical-vs-modern-ciphers--comparison)
  - [5.13 Quantum Computing Threat to Cryptography](#513-quantum-computing-threat-to-cryptography)
- [6. Abbreviations Table](#6-abbreviations-table)
- [7. Keywords + Concept Map](#7-keywords--concept-map)
- [8. Quick Reference Cheatsheet](#8-quick-reference-cheatsheet)
- [9. Session Revision Snapshot](#9-session-revision-snapshot)

---

## 1. Cryptographic Fundamentals

### 1.1 What is Cryptography?

**Cryptography** is the science of using mathematical techniques to secure information — transforming data so that only intended recipients can understand it, and providing assurances about data origin and integrity.

Modern cryptography operates at the intersection of:
- **Mathematics** — number theory, algebra, probability
- **Computer Science** — algorithms, computational complexity
- **Electrical Engineering** — hardware implementations

> [!IMPORTANT]
> Cryptography is not just about hiding messages (confidentiality).
> Modern cryptography delivers ALL of the following security services:
> - **Confidentiality** — encryption
> - **Integrity** — hashing, MACs
> - **Authentication** — digital certificates, signatures
> - **Non-repudiation** — digital signatures
> - **Key Exchange** — Diffie-Hellman, RSA

---

### 1.2 Goals of Cryptography

Mapped to the services cryptographic primitives deliver:

| Goal | Cryptographic Primitive | Example |
|------|------------------------|---------|
| **Confidentiality** | Symmetric/Asymmetric Encryption | AES, RSA |
| **Integrity** | Hash Functions, MAC | SHA-256, HMAC |
| **Authentication** | Digital Signatures, Certificates | RSA signatures, X.509 |
| **Non-repudiation** | Digital Signatures | RSA + SHA signed messages |
| **Key Exchange** | Key Agreement Protocols | Diffie-Hellman, ECDH |
| **Access Control** | Cryptographic tokens, PKI | Smart cards, TLS client certs |

---

### 1.3 Modular Arithmetic

**Modular arithmetic** is the mathematical foundation of almost every modern encryption algorithm. Understanding it is essential for understanding RSA, Diffie-Hellman, and ECC.

**Definition:**
`a mod n` = the remainder when `a` is divided by `n`

```
Examples:
  17 mod 5  = 2    (17 = 3×5 + 2)
  23 mod 7  = 2    (23 = 3×7 + 2)
  15 mod 5  = 0    (15 = 3×5 + 0)
  7  mod 10 = 7    (7  = 0×10 + 7)
```

**Key properties used in cryptography:**

| Property | Expression | Example |
|----------|-----------|---------|
| **Addition** | (a + b) mod n = ((a mod n) + (b mod n)) mod n | (9 + 7) mod 5 = (4 + 2) mod 5 = 1 |
| **Multiplication** | (a × b) mod n = ((a mod n) × (b mod n)) mod n | (9 × 7) mod 5 = (4 × 2) mod 5 = 3 |
| **Exponentiation** | aᵉ mod n | Core operation in RSA |

**The Clock Analogy:**
Modular arithmetic works like a clock — after 12, it wraps back to 1.
`mod 12`: 13 ≡ 1, 14 ≡ 2, 25 ≡ 1

> [!IMPORTANT]
> RSA encryption and decryption are fundamentally modular exponentiation operations:
> - Encrypt: C = Mᵉ mod n
> - Decrypt: M = Cᵈ mod n
> Where e, d, n are RSA key components — covered in depth in Session 04.

---

### 1.4 Prime Numbers in Cryptography

A **prime number** is a natural number greater than 1 that has no divisors other than 1 and itself.

```
Primes: 2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37...
```

**Why primes are critical in cryptography:**

| Algorithm | How Primes Are Used |
|-----------|-------------------|
| **RSA** | Security relies on the difficulty of factoring the product of two large prime numbers (n = p × q) |
| **Diffie-Hellman** | Uses a large prime modulus p for modular arithmetic |
| **DSA** | Uses prime numbers in its key generation and signing operations |
| **ECC** | Works over prime fields (Fp) or binary fields |

**Fundamental Theorem of Arithmetic:**
Every integer > 1 can be expressed as a unique product of prime numbers.
- Example: 84 = 2² × 3 × 7

**Why factoring is hard:**
- **Multiplying** two large primes: easy and fast (milliseconds)
- **Factoring** the result back into its prime components: computationally infeasible for large numbers

```
Easy:   9,999,991 × 9,999,973 = 99,999,640,000,243
Hard:   Factor 99,999,640,000,243 back to its primes
```

For RSA, these primes are hundreds of digits long — factoring them with current computers would take longer than the age of the universe.

> [!NOTE]
> RSA keys of 2048 bits are currently considered secure.
> RSA-1024 is considered weak and deprecated.
> NIST recommends RSA-2048 minimum, RSA-3072 for post-2030 security.

---

### 1.5 GCD and Coprime Numbers

**GCD (Greatest Common Divisor):**
The largest integer that divides both numbers without a remainder.

```
GCD(12, 8)  = 4
GCD(15, 10) = 5
GCD(17, 13) = 1   ← Coprime
```

**Coprime (Relatively Prime):**
Two numbers are coprime if their GCD = 1. They share no common factors except 1.

```
GCD(8, 15) = 1  → 8 and 15 are coprime
GCD(6, 9)  = 3  → 6 and 9 are NOT coprime
```

**Why coprime numbers matter in cryptography:**

| Use | Context |
|-----|---------|
| **RSA key generation** | The public exponent `e` must be coprime with φ(n) — Euler's totient of n |
| **Modular inverse** | A modular inverse of `a mod n` exists ONLY if gcd(a, n) = 1 |
| **Diffie-Hellman** | The generator `g` must work in a group where coprimality holds |

**Euclidean Algorithm** — Computing GCD:
```
GCD(48, 18):
  48 = 2 × 18 + 12
  18 = 1 × 12 + 6
  12 = 2 × 6  + 0  ← remainder = 0
  GCD = 6
```

---

### 1.6 XOR Operation

**XOR (Exclusive OR)** is the fundamental binary operation underlying many encryption algorithms, stream ciphers, and hash functions.

**XOR Truth Table:**

| A | B | A XOR B |
|---|---|---------|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

**Rule:** XOR = 1 when inputs are DIFFERENT; 0 when inputs are SAME.

**Critical XOR Properties for Cryptography:**

| Property | Expression | Meaning |
|----------|-----------|---------|
| **Self-inverse** | A XOR A = 0 | XOR a value with itself = zero |
| **Identity** | A XOR 0 = A | XOR with zero = unchanged |
| **Commutative** | A XOR B = B XOR A | Order doesn't matter |
| **Associative** | (A XOR B) XOR C = A XOR (B XOR C) | Grouping doesn't matter |
| **Encryption/Decryption** | (A XOR K) XOR K = A | XOR with key twice = original value |

**XOR Encryption Example:**
```
Plaintext  (P):  1010 1100
Key        (K):  0110 1001
─────────────────────────
Ciphertext (C):  1100 0101   ← P XOR K

Decryption:
Ciphertext (C):  1100 0101
Key        (K):  0110 1001
─────────────────────────
Plaintext  (P):  1010 1100   ← C XOR K = P ✅
```

> [!IMPORTANT]
> XOR is the **basis of the Vernam Cipher (One-Time Pad)** — theoretically the only provably unbreakable cipher.
> XOR is used in: stream ciphers (RC4), AES (AddRoundKey step), HMAC, hash functions.
> **XOR cipher weakness:** If the key is shorter than the message and is reused → vulnerable to frequency analysis and statistical attacks.

---

### 1.7 One-Way Functions

A **one-way function** is a function that is:
- **Easy to compute** in one direction
- **Computationally infeasible** to reverse (invert)

```
f(x) = y  →  Easy to compute
f⁻¹(y) = x  →  Computationally infeasible
```

**Examples of one-way functions in cryptography:**

| Function | Easy Direction | Hard Direction |
|----------|---------------|----------------|
| **Hash functions** | Hash(M) = H | Find M given H |
| **Prime multiplication** | p × q = n | Factor n back to p and q |
| **Modular exponentiation** | gˣ mod p = y | Find x given g, p, y (discrete log problem) |
| **Elliptic curve point multiplication** | k × G = P | Find k given G and P |

> [!NOTE]
> One-way functions are the mathematical backbone of:
> - Hash functions (Session 06)
> - RSA (integer factorization — Session 04)
> - Diffie-Hellman (discrete logarithm — Session 05)
> - ECC (elliptic curve discrete logarithm — Session 04)

---

### 1.8 Trapdoor Functions

A **trapdoor function** is a special type of one-way function that becomes easy to invert IF a secret piece of information (the "trapdoor") is known.

```
Without trapdoor:  f(x) = y  →  Easy; f⁻¹(y) = x  →  Hard
With trapdoor:     f(x) = y  →  Easy; f⁻¹(y) = x  →  EASY (using trapdoor)
```

**The trapdoor IS the private key in asymmetric cryptography.**

| Algorithm | One-Way Problem | Trapdoor (Private Key) |
|-----------|----------------|----------------------|
| **RSA** | Factor n = p × q | Knowledge of p and q (and derived d) |
| **Diffie-Hellman** | Discrete logarithm problem | The private exponent x |
| **ECC** | ECDLP | The private scalar k |

> [!IMPORTANT]
> This is why asymmetric cryptography works:
> - **Anyone** can encrypt using the public key (compute the one-way function)
> - **Only the private key holder** can decrypt (has the trapdoor to invert the function)
> Without the trapdoor → computationally infeasible to reverse the operation.

---

### 1.9 P vs NP — Why Asymmetric Crypto is Hard to Break

**Computational complexity** explains why breaking modern cryptography is practically infeasible:

| Class | Definition | Examples |
|-------|-----------|---------|
| **P (Polynomial time)** | Problems solvable efficiently — time grows polynomially with input size | Sorting, searching, symmetric decryption with known key |
| **NP (Non-deterministic Polynomial)** | Solutions are verifiable in polynomial time, but finding solutions may not be | Factoring large integers, discrete logarithm |
| **NP-Hard** | At least as hard as hardest NP problems | General cases of factoring, knapsack |

**In cryptographic context:**

```
Encryption (with key)     →  P problem  →  Fast
Decryption (with key)     →  P problem  →  Fast
Breaking (without key)    →  NP problem →  Computationally infeasible
```

The security of RSA, Diffie-Hellman, and ECC rests on the assumption that:
- **Factoring large integers** is an NP problem
- **Discrete logarithm** is an NP problem
- No polynomial-time algorithm exists for these problems

> [!NOTE]
> The famous **P vs NP question** (whether P = NP) is one of the Millennium Prize Problems.
> If P = NP were ever proven (i.e., NP problems can be solved in polynomial time), most modern public-key cryptography would be broken overnight.

---

### 1.10 Random Number Generation

Strong encryption depends on **truly unpredictable random numbers** — for key generation, IV generation, nonces, and session tokens.

| Type | Full Name | Description | Cryptographically Secure? |
|------|-----------|-------------|--------------------------|
| **TRNG** | True Random Number Generator | Uses physical entropy sources (hardware noise, radioactive decay, mouse movement) | ✅ Yes — best quality |
| **PRNG** | Pseudo-Random Number Generator | Deterministic algorithm seeded with an initial value — same seed = same sequence | ❌ No — predictable |
| **CSPRNG** | Cryptographically Secure PRNG | PRNG designed to be computationally infeasible to predict — even knowing past output | ✅ Yes |

**CSPRNG Examples:**

| Platform | CSPRNG |
|----------|--------|
| Linux/Unix | `/dev/urandom`, `/dev/random` |
| Windows | `BCryptGenRandom`, `CryptGenRandom` |
| Java | `SecureRandom` |
| OpenSSL | Internal CSPRNG seeded from OS entropy |

> [!IMPORTANT]
> Using a weak or predictable PRNG for key generation is catastrophic.
> Real-world example: Android Bitcoin wallets (2013) — weak PRNG caused repeated k values in ECDSA signatures, allowing private key recovery.
> Rule: **Always use CSPRNG for all cryptographic operations.**

> [!NOTE]
> `/dev/random` (Linux) blocks when entropy pool is exhausted — produces fewer but higher-quality random bytes.
> `/dev/urandom` does not block — uses a CSPRNG seeded from hardware entropy. For most cryptographic purposes, `/dev/urandom` is sufficient and preferred.

---

### 1.11 Avalanche Effect

The **Avalanche Effect** is a desirable property of cryptographic hash functions and block ciphers where:

> A small change in the input (even 1 bit) causes a drastic, unpredictable change in the output (approximately 50% of output bits change).

```
Input 1:  "Hello"  → SHA-256 → 185f8db32921bd46d35cc53...
Input 2:  "hello"  → SHA-256 → 2cf24dba5fb0a30e26e83b2a...
```

One character change (H → h) completely transforms the entire hash output.

**Why it matters:**

| Without Avalanche Effect | With Avalanche Effect |
|-------------------------|----------------------|
| Small input changes → small output changes | Small input changes → completely different output |
| Attacker can make small modifications to ciphertext and predict the effect | Attacker cannot predict output changes — makes differential cryptanalysis hard |
| Patterns become visible | No useful patterns emerge |

> [!NOTE]
> The Avalanche Effect is related to both **Confusion** and **Diffusion** (Shannon):
> - Diffusion ensures one plaintext bit change spreads across many ciphertext bits
> - Confusion ensures the relationship between key and ciphertext is complex
> Together they produce the Avalanche Effect in well-designed ciphers and hash functions.

---

## 2. Cryptographic Ciphers — Symmetric

### 2.1 Symmetric Encryption — Core Model

In symmetric encryption, **the same key** is used for both encryption and decryption.

```
Sender:
  Plaintext + Shared Secret Key → Encryption Algorithm → Ciphertext

Receiver:
  Ciphertext + Shared Secret Key → Decryption Algorithm → Plaintext
```

**The Key Distribution Problem:**
How do two parties securely share the secret key before communication begins?
- This is the fundamental weakness of symmetric encryption
- Solved by asymmetric key exchange (Diffie-Hellman — Session 05) or by using asymmetric encryption to transport the symmetric key

> [!IMPORTANT]
> For n users to communicate securely using symmetric encryption, they need:
> **n(n-1)/2 unique keys**
> For 10 users: 10×9/2 = **45 keys**
> For 1000 users: 1000×999/2 = **499,500 keys**
> This key management explosion is why asymmetric cryptography was revolutionary.

---

### 2.2 Classical Symmetric Ciphers

Classical ciphers are the historical predecessors of modern algorithms. They operate on letters/characters rather than bits.

| Cipher | Type | Key | Security | Notes |
|--------|------|-----|----------|-------|
| **Caesar** | Substitution (monoalphabetic) | Shift value (1–25) | Very weak — 25 possible keys | Julius Caesar used shift of 3 |
| **ROT13** | Substitution (monoalphabetic) | Fixed shift of 13 | Trivially broken | rot13(rot13(x)) = x — self-inverse |
| **Atbash** | Substitution (monoalphabetic) | None | Trivially broken | A↔Z, B↔Y — reverse alphabet |
| **Vigenère** | Substitution (polyalphabetic) | Keyword | Weak — broken by Kasiski test | Multiple Caesar ciphers layered |
| **Playfair** | Substitution (digram) | 5×5 key matrix | Weak | Encrypts pairs of letters |
| **Vernam/OTP** | XOR (stream) | Random key = message length | Theoretically perfect | Provably unbreakable under strict conditions |
| **Rail Fence** | Transposition | Number of rails | Very weak | Rearranges letters in zigzag |
| **Columnar** | Transposition | Column order key | Weak | Write in rows, read in column order |
| **Enigma** | Polyalphabetic (electromechanical) | Daily rotor settings | Broken by Turing | Used by Nazi Germany in WWII |

---

### 2.3 Caesar Cipher — Deep Dive

**Caesar Cipher** is the simplest substitution cipher — each letter is shifted by a fixed number of positions in the alphabet.

**Encryption Formula:**
```
C = (P + K) mod 26
```
Where:
- C = ciphertext letter position
- P = plaintext letter position
- K = shift key (1–25)

**Decryption Formula:**
```
P = (C - K + 26) mod 26
```

**Example — Key = 3:**
```
Plaintext:   A  B  C  D  E  F  ...  X  Y  Z
Ciphertext:  D  E  F  G  H  I  ...  A  B  C

"HELLO" → Key 3 → "KHOOR"
"KHOOR" → Key 3 → "HELLO"
```

**Why it is trivially broken:**
- Only **25 possible keys** — brute force in seconds
- Vulnerable to **frequency analysis** — letter frequency of ciphertext matches shifted plaintext frequency
- All instances of the same letter map to the same ciphertext letter

> [!NOTE]
> **ROT13** is a special case of Caesar cipher with K = 13.
> Since 13 + 13 = 26 (the alphabet size), ROT13 is self-inverse: ROT13(ROT13(x)) = x.
> ROT13 is used on forums/newsgroups to hide spoilers — it provides zero security.

---

### 2.4 Vigenère Cipher

**Vigenère Cipher** is a polyalphabetic substitution cipher that uses a **keyword** to apply multiple Caesar ciphers in rotation — making frequency analysis harder.

**How it works:**
```
Plaintext:    A  T  T  A  C  K  A  T  D  A  W  N
Key:          L  E  M  O  N  L  E  M  O  N  L  E
              (key repeats as needed)

Each letter shifted by the position value of the key letter:
A + L(11) = L
T + E(4)  = X
T + M(12) = F
...

Ciphertext:   L  X  F  O  P  V  E  F  R  N  H  R
```

**Key Features:**
- Same plaintext letter can encrypt to different ciphertext letters depending on key position
- Makes simple frequency analysis fail (defeats monoalphabetic weaknesses)

**Breaking the Vigenère Cipher:**

| Method | How |
|--------|-----|
| **Kasiski Test (1863)** | Find repeated sequences in ciphertext → distance between them is likely a multiple of the key length → determine key length → split into Caesar ciphers |
| **Index of Coincidence** | Statistical measure to determine key length |
| **Frequency Analysis** | Once key length known, each Caesar cipher sub-stream is broken individually |

> [!NOTE]
> The Vigenère Cipher was called "le chiffre indéchiffrable" (the indecipherable cipher) for ~300 years.
> It was finally broken by Charles Babbage (~1854, kept secret) and Friedrich Kasiski (1863, published).

---

### 2.5 Vernam Cipher — One-Time Pad (OTP)

**Vernam Cipher** (Gilbert Vernam, 1917) is the only encryption algorithm that has been **mathematically proven to be perfectly secure** — provided its strict conditions are met.

**Mechanism:**
```
Ciphertext = Plaintext XOR Key
Plaintext  = Ciphertext XOR Key
```

**Claude Shannon's Proof (1949):**
The One-Time Pad provides **perfect secrecy** — observing the ciphertext provides absolutely zero information about the plaintext — IF all four conditions are met:

| Condition | Requirement | Why |
|-----------|-------------|-----|
| **1. Key length** | Key must be AT LEAST as long as the message | Shorter key → patterns emerge |
| **2. True randomness** | Key must be truly random — not pseudo-random | Predictable key → cipher broken |
| **3. Single use** | Each key used ONCE only — NEVER reused | Reuse → Crib-dragging attack |
| **4. Secrecy** | Key must be kept completely secret | Obvious |

**Why OTP is impractical for general use:**

| Problem | Explanation |
|---------|-------------|
| **Key as long as message** | Encrypting 1GB of data requires 1GB of key |
| **Key distribution** | Securely delivering a 1GB key to the receiver is as hard as delivering the message itself |
| **Key storage** | Both parties must securely store and then destroy used keys |
| **Single use enforcement** | Extremely difficult to enforce in practice |

**What happens when OTP key is reused:**
```
C1 = P1 XOR K
C2 = P2 XOR K

C1 XOR C2 = (P1 XOR K) XOR (P2 XOR K)
           = P1 XOR P2   ← Key cancels out!
```
The attacker now has P1 XOR P2 — and from this, with known language statistics (**crib-dragging**), both plaintexts can be recovered.

> [!IMPORTANT]
> **Real-world OTP use:** The Moscow-Washington hotline ("Red Phone") used OTP during the Cold War.
> **Lesson from history:** The Venona project (US intelligence, 1940s) broke Soviet OTP-encrypted messages ONLY because Soviet operators reused key material under wartime pressure.

---

### 2.6 Modern Symmetric Ciphers — Overview Map

Deep technical dives happen in Session 04. This is the overview map:

| Cipher | Key Length | Block Size | Type | Status |
|--------|-----------|-----------|------|--------|
| **DES** | 56-bit effective | 64-bit | Block | ❌ Broken — brute-forceable |
| **3DES (Triple DES)** | 112/168-bit | 64-bit | Block | ⚠️ Deprecated — too slow |
| **AES-128** | 128-bit | 128-bit | Block | ✅ Secure — standard |
| **AES-192** | 192-bit | 128-bit | Block | ✅ Secure |
| **AES-256** | 256-bit | 128-bit | Block | ✅ Secure — quantum-resistant candidate |
| **RC4** | 40–2048-bit | N/A | Stream | ❌ Broken — deprecated |
| **RC5** | 0–2040-bit | 32/64/128-bit | Block | ⚠️ Secure but rarely used now |
| **ChaCha20** | 256-bit | N/A | Stream | ✅ Secure — modern alternative to RC4 |
| **Blowfish** | 32–448-bit | 64-bit | Block | ⚠️ Aging — small block size |

---

## 3. Cryptographic Ciphers — Asymmetric

### 3.1 Asymmetric Encryption — Core Model

In asymmetric encryption, **two mathematically linked keys** are used — a public key and a private key.

```
Key Pair:
  Public Key  (KU) — freely distributed, known to everyone
  Private Key (KR) — kept secret by the owner only

Encryption:
  Ciphertext = Encrypt(KU_receiver, Plaintext)

Decryption:
  Plaintext = Decrypt(KR_receiver, Ciphertext)
```

**The mathematical relationship:**
The two keys are mathematically related — but it is computationally infeasible to derive the private key from the public key.

> [!IMPORTANT]
> What one key encrypts, only the OTHER key can decrypt:
> - Encrypt with **Public Key** → Decrypt with **Private Key** (Confidentiality use case)
> - Encrypt with **Private Key** → Decrypt with **Public Key** (Digital Signature use case)

---

### 3.2 How Key Pairs Work

```
Alice wants to receive encrypted messages:

Step 1: Alice generates a key pair
        → Public Key  (KU_Alice)  — she publishes this freely
        → Private Key (KR_Alice) — she keeps this SECRET

Step 2: Bob wants to send Alice a confidential message
        → Bob encrypts message with KU_Alice (Alice's public key)
        → Only KR_Alice (Alice's private key) can decrypt it
        → Even Bob cannot decrypt his own ciphertext

Step 3: Alice decrypts with KR_Alice
        → Plaintext recovered
```

**Visual Summary:**
```
            Alice's Public Key (shared openly)
                         │
Bob → Encrypt(KU_Alice) ──→ Ciphertext ──→ Decrypt(KR_Alice) → Alice
                                                │
                                    Alice's Private Key (secret)
```

---

### 3.3 Asymmetric Use Cases — Encryption vs Signing

This is one of the **most critical concept maps** in the entire PKI module:

| Use Case | Key Used to Encrypt/Sign | Key Used to Decrypt/Verify | Goal |
|----------|--------------------------|---------------------------|------|
| **Confidentiality** | Receiver's **Public Key** | Receiver's **Private Key** | Only the receiver can read the message |
| **Digital Signature (Signing)** | Sender's **Private Key** | Sender's **Public Key** | Anyone can verify — only sender could sign |
| **Key Exchange** | Receiver's **Public Key** | Receiver's **Private Key** | Securely send symmetric key to receiver |

> [!IMPORTANT]
> MCQ trap — always asked:
> - To **encrypt a message** for Alice → use Alice's **PUBLIC key**
> - To **sign a message** as Bob → use Bob's **PRIVATE key**
> - To **verify Bob's signature** → use Bob's **PUBLIC key**
> - To **decrypt a message** sent to Alice → use Alice's **PRIVATE key**

---

### 3.4 Modern Asymmetric Ciphers — Overview Map

Deep technical dives in Session 04. Overview:

| Algorithm | Mathematical Basis | Key Length | Primary Use | Status |
|-----------|-------------------|-----------|-------------|--------|
| **RSA** | Integer Factorization | 2048–4096-bit | Encryption, Signatures, Key Exchange | ✅ Standard |
| **DSA** | Discrete Logarithm | 1024–3072-bit | Digital Signatures only | ⚠️ Aging |
| **Diffie-Hellman (DH)** | Discrete Logarithm | 2048-bit+ | Key Exchange only | ✅ Standard |
| **ECDH** | ECDLP | 256-bit (≈ RSA-3072) | Key Exchange | ✅ Modern standard |
| **ECDSA** | ECDLP | 256–521-bit | Digital Signatures | ✅ Modern standard |
| **ElGamal** | Discrete Logarithm | 1024-bit+ | Encryption, Signatures | ⚠️ Rarely used directly |
| **ECC** | Elliptic Curve DLOG | 256–521-bit | Encryption, Signatures, Key Exchange | ✅ Modern standard |

---

### 3.5 Hybrid Encryption — Why We Use Both

**Hybrid encryption** combines symmetric and asymmetric encryption to get the best of both worlds.

**The problem:**
- Symmetric encryption: **fast** but key distribution is hard
- Asymmetric encryption: **solves key distribution** but is **extremely slow** for bulk data (RSA encryption is ~1000× slower than AES)

**The solution — Hybrid Encryption Pattern:**

```
Step 1: Generate a random symmetric session key (e.g., AES-256 key)

Step 2: Encrypt the actual data using the symmetric session key
        (fast — AES handles bulk data efficiently)

Step 3: Encrypt the session key using the receiver's RSA public key
        (RSA only encrypts a small key, not bulk data — acceptable speed)

Step 4: Send both:
        → Encrypted data (AES ciphertext)
        → Encrypted session key (RSA ciphertext)

Receiver:
Step 5: Decrypt the session key using their RSA private key
Step 6: Use the recovered session key to decrypt the data
```

**Where hybrid encryption is used:**

| System | Symmetric | Asymmetric |
|--------|-----------|-----------|
| **TLS/HTTPS** | AES for data | RSA/ECDH for key exchange |
| **PGP/GPG** | AES/IDEA for data | RSA/ECC for key wrapping |
| **S/MIME** | AES for email body | RSA for key transport |
| **Windows EFS** | AES for file | RSA for FEK protection |
| **SSH** | AES for session | RSA/ECDSA for authentication |

> [!IMPORTANT]
> Hybrid encryption is the **dominant pattern in all real-world secure communications**.
> Pure asymmetric encryption of large data is never done in practice.

---

## 4. Cryptographic Protocols

### 4.1 What is a Cryptographic Protocol?

A **cryptographic protocol** is a defined sequence of steps and rules that specify how cryptographic algorithms are combined and used to achieve one or more security goals between two or more parties.

**A protocol defines:**
- **Who** communicates with whom
- **What** messages are sent and in what order
- **Which** algorithms and keys are used at each step
- **How** trust is established and maintained

> [!NOTE]
> An algorithm alone is NOT a protocol.
> AES is an algorithm — a cipher.
> TLS is a protocol — it specifies how AES (and other algorithms) are combined, negotiated, and used in a complete secure communication system.

---

### 4.2 History of Cryptographic Protocols

| Year | Protocol / Development | Significance |
|------|----------------------|--------------|
| **1976** | **Diffie-Hellman Key Exchange** published | First public-key cryptographic protocol — solved key distribution |
| **1978** | **RSA** published | First practical public-key algorithm for encryption AND signatures |
| **1983** | **Kerberos** developed (MIT) | First major network authentication protocol |
| **1988** | **X.509** standard published (ITU-T) | Foundation of PKI — digital certificate format |
| **1991** | **PGP** (Pretty Good Privacy) — Phil Zimmermann | First widely accessible public-key encryption tool |
| **1993** | **SSL 1.0** developed (Netscape) | Never released — design flaws found |
| **1994** | **SSL 2.0** released | First deployed web encryption — had vulnerabilities |
| **1995** | **SSL 3.0** released | Widely adopted — later found vulnerable (POODLE attack) |
| **1999** | **TLS 1.0** (RFC 2246) | Successor to SSL 3.0 — standardized by IETF |
| **2002** | **TLS 1.1** (RFC 4346) | Added protection against CBC attacks |
| **2008** | **TLS 1.2** (RFC 5246) | Introduced AES-GCM, SHA-256 — still widely used |
| **2018** | **TLS 1.3** (RFC 8446) | Removed weak ciphers, faster handshake, mandatory PFS |
| **2001** | **AES** adopted (NIST FIPS 197) | Replaced DES as US federal standard |
| **2004** | **WPA** (Wi-Fi Protected Access) | Replaced broken WEP in Wi-Fi security |
| **2004** | **WPA2** | Added AES-CCMP — current Wi-Fi standard |

> [!IMPORTANT]
> Key exam fact: **SSL is deprecated** — all versions (SSL 2.0, SSL 3.0) are broken.
> **TLS 1.0 and TLS 1.1** are deprecated (RFC 8996, 2021).
> **TLS 1.2 and TLS 1.3** are the current standards.
> SSL and TLS are covered in depth in Session 13.

---

### 4.3 Protocol Usage and Purpose Map

| Protocol | Primary Security Goal | Layer | Algorithm Used |
|----------|----------------------|-------|----------------|
| **TLS/SSL** | Confidentiality + Integrity + Authentication | Transport (Layer 4) | AES, RSA/ECDH, SHA |
| **SSH** | Confidentiality + Authentication | Application | AES, RSA/ECDSA |
| **IPSec** | Confidentiality + Integrity + Authentication | Network (Layer 3) | AES, DH, RSA |
| **PGP/GPG** | Confidentiality + Integrity + Non-repudiation | Application | AES, RSA/ECC, SHA |
| **S/MIME** | Confidentiality + Integrity + Non-repudiation | Application | AES, RSA, SHA |
| **Kerberos** | Authentication | Application | AES (symmetric only) |
| **HTTPS** | Confidentiality + Integrity + Authentication | Application | TLS underneath |
| **DNSSEC** | Integrity + Authentication | Application | RSA/ECDSA, SHA |

---

### 4.4 Key Generation — How Keys Are Produced

#### Symmetric Key Generation
```
Step 1: Request random bytes from CSPRNG
        (e.g., /dev/urandom on Linux, BCryptGenRandom on Windows)

Step 2: Trim to required key length
        AES-128 → 128 bits = 16 bytes of random data
        AES-256 → 256 bits = 32 bytes of random data

Step 3: Key is ready for use
```

#### Asymmetric Key Generation — RSA (Overview)

Full mathematical detail in Session 04. Process summary:

```
Step 1: Choose two large random prime numbers p and q
        (each typically 1024+ bits for RSA-2048)

Step 2: Compute n = p × q
        (n is the modulus — part of both public and private key)

Step 3: Compute Euler's totient: φ(n) = (p-1)(q-1)

Step 4: Choose public exponent e:
        - Common value: 65537 (2¹⁶ + 1)
        - Must be: 1 < e < φ(n), and gcd(e, φ(n)) = 1

Step 5: Compute private exponent d:
        d = e⁻¹ mod φ(n)  (modular inverse of e)

Step 6: Public Key  = (e, n)
        Private Key = (d, n)
        p, q, φ(n) are discarded / kept secret
```

#### Key Derivation Functions (KDF)

When a key must be derived from a password or another key:

| KDF | Full Name | Use |
|-----|-----------|-----|
| **PBKDF2** | Password-Based Key Derivation Function 2 | Derive encryption keys from passwords — used in WPA2, PKCS#5 |
| **bcrypt** | — | Password hashing + key derivation — adaptive cost |
| **scrypt** | — | Memory-hard KDF — resists GPU/ASIC brute force |
| **HKDF** | HMAC-based Key Derivation Function | Derive session keys from shared secrets (used in TLS 1.3) |

> [!NOTE]
> A **KDF** is different from just hashing a password:
> - KDF is designed to be **slow and expensive** — making brute force attacks costly
> - Hash functions (SHA-256) are designed to be **fast** — unsuitable for direct password protection
> - This is why passwords should be stored using bcrypt/scrypt/PBKDF2 — NOT plain SHA-256

---

### 4.5 Ciphering a Message — Step-by-Step Flow

**Scenario:** Alice wants to send a confidential, authenticated message to Bob.

**Using Hybrid Encryption + Digital Signature:**

```
ALICE (Sender):

1. Write plaintext message M

2. SIGN (Authentication + Non-repudiation):
   a. Compute Hash(M) using SHA-256 → H
   b. Encrypt H with Alice's Private Key → Signature S
      S = Encrypt(KR_Alice, H)

3. ENCRYPT (Confidentiality):
   a. Generate random AES-256 session key SK
   b. Encrypt M + S using SK (AES-CBC or AES-GCM)
      → Encrypted Bundle = AES_Encrypt(SK, M + S)
   c. Encrypt SK with Bob's Public Key
      → Encrypted SK = RSA_Encrypt(KU_Bob, SK)

4. SEND:
   → Encrypted Bundle + Encrypted SK → Bob

─────────────────────────────────────────────────

BOB (Receiver):

5. DECRYPT session key:
   SK = RSA_Decrypt(KR_Bob, Encrypted SK)

6. DECRYPT message bundle:
   M + S = AES_Decrypt(SK, Encrypted Bundle)

7. VERIFY SIGNATURE:
   a. Decrypt S with Alice's Public Key → H'
      H' = Decrypt(KU_Alice, S)
   b. Compute Hash(M) → H
   c. Compare H' with H:
      If H' == H → Signature valid ✅ (message authentic, not tampered)
      If H' ≠ H  → Signature invalid ❌ (message tampered or wrong sender)
```

> [!IMPORTANT]
> This flow is the foundation of every secure communication protocol:
> - TLS uses this pattern for HTTPS
> - PGP/S-MIME use this for email
> - SSH uses this for remote access
> The exact same conceptual flow appears in Session 07 (Digital Signatures), Session 08 (PKI), and Session 13 (TLS).

---

## 5. 📌 Extra Notes

> [!NOTE]
> Everything in this section goes beyond the core syllabus but is directly MCQ-relevant. Cross-referenced from Stallings, NIST publications, and cryptographic standards.

---

### 5.1 Euler's Totient Function φ(n)

> [!NOTE]
> **Euler's Totient Function φ(n)** counts the number of integers from 1 to n that are coprime with n (share no factors with n other than 1).

**Key values:**

| n | φ(n) | Reason |
|---|------|--------|
| p (prime) | p - 1 | All integers from 1 to p-1 are coprime with p |
| p × q (two distinct primes) | (p-1)(q-1) | RSA uses this directly |
| 10 | 4 | Integers coprime with 10: {1, 3, 7, 9} |

**Why it matters in RSA:**
```
RSA uses: φ(n) = (p-1)(q-1)

This value is used to:
1. Generate the public exponent e (must be coprime with φ(n))
2. Compute the private exponent d (d × e ≡ 1 mod φ(n))

Euler's Theorem: a^φ(n) ≡ 1 (mod n) when gcd(a,n) = 1
→ This is the mathematical reason RSA encryption/decryption work correctly
```

---

### 5.2 Fermat's Little Theorem

> [!NOTE]
> **Fermat's Little Theorem:** If p is prime and a is not divisible by p:
> ```
> aᵖ⁻¹ ≡ 1 (mod p)
> ```

**Corollary:**
```
aᵖ ≡ a (mod p)  for any integer a
```

**Use in cryptography:**
- Foundation for **Miller-Rabin primality test** (used to generate RSA primes)
- Used in RSA correctness proof
- Used in Diffie-Hellman security analysis

**Example:**
```
p = 7, a = 3
3⁶ mod 7 = 729 mod 7 = 1 ✅ (since 729 = 104×7 + 1)
```

---

### 5.3 Discrete Logarithm Problem

> [!NOTE]
> **Discrete Logarithm Problem (DLP):**
>
> Given: g, p (prime), and y = gˣ mod p
> Find: x
>
> This is computationally hard for large p.

```
Easy:   g=5, x=3, p=23 → 5³ mod 23 = 125 mod 23 = 10
Hard:   g=5, y=10, p=23 → Find x such that 5ˣ mod 23 = 10
```

For cryptographically large p (2048-bit), finding x is infeasible.

**Algorithms that rely on DLP hardness:**

| Algorithm | How DLP is Used |
|-----------|----------------|
| **Diffie-Hellman** | Key exchange — security = hardness of DLP |
| **DSA** | Digital Signature Algorithm |
| **ElGamal** | Encryption and signatures |

---

### 5.4 Integer Factorization Problem

> [!NOTE]
> **Integer Factorization Problem:**
>
> Given: n = p × q (product of two large primes)
> Find: p and q
>
> Easy when n is small; computationally infeasible for large n (2048-bit+).

**RSA security = hardness of factoring n**

```
Easy:   p=61, q=53 → n = 3233
Hard:   Given n=3233, find p=61 and q=53
```

For RSA-2048 (n is a 617-digit number):
- Best known factoring algorithm: General Number Field Sieve (GNFS)
- Estimated time to factor RSA-2048: longer than the age of the universe with current technology

**Note:** Shor's Algorithm (quantum) can factor in polynomial time — quantum threat is real.

---

### 5.5 Elliptic Curve Discrete Logarithm Problem (ECDLP)

> [!NOTE]
> **Elliptic Curve:**
> A mathematical curve defined by: y² = x³ + ax + b (over a finite field)

**Point multiplication:**
```
P = k × G
Where:
  G = generator point (public, fixed for a curve)
  k = private scalar (secret)
  P = public key (result of multiplying G by k)
```

**ECDLP:** Given G and P, find k — computationally infeasible.

**Why ECC is preferred over RSA in modern systems:**

| Property | RSA-2048 | ECC-256 | RSA-3072 | ECC-384 |
|----------|----------|---------|----------|---------|
| Equivalent Security | 112-bit | 128-bit | 128-bit | 192-bit |
| Key Size | 2048-bit | 256-bit | 3072-bit | 384-bit |
| Performance | Slower | Faster | Slowest | Fast |
| Battery/Bandwidth | High cost | Low cost | Higher | Low |

> [!TIP]
> ECC provides equivalent security to RSA with **much shorter keys**.
> 256-bit ECC ≈ 3072-bit RSA in security strength.
> This makes ECC ideal for constrained environments: mobile devices, IoT, smart cards.

---

### 5.6 Perfect Forward Secrecy (PFS)

> [!NOTE]
> **Perfect Forward Secrecy (PFS)** — also called **Forward Secrecy (FS)** — is a property of a key exchange protocol where:
>
> Compromising the **long-term private key** does NOT compromise past session keys.

**Without PFS:**
```
Attacker records all encrypted TLS traffic for years.
Later, attacker obtains the server's RSA private key.
Attacker decrypts ALL previously recorded sessions.
→ Past data is compromised retroactively.
```

**With PFS (using Ephemeral Diffie-Hellman — DHE or ECDHE):**
```
Each session generates a NEW temporary (ephemeral) DH key pair.
Session key is derived from the ephemeral keys.
Ephemeral private key is discarded immediately after session ends.
Even with long-term private key compromised → past sessions are safe.
→ Each session's key is mathematically independent.
```

**How PFS is achieved:**

| Key Exchange | PFS? | Notes |
|-------------|------|-------|
| RSA key transport | ❌ No PFS | Static RSA — same private key decrypts all sessions |
| DHE (Ephemeral DH) | ✅ PFS | New DH keys per session |
| ECDHE (Ephemeral ECDH) | ✅ PFS | ECC version — faster and more common |

> [!IMPORTANT]
> **TLS 1.3 mandates PFS** — it removed all non-PFS cipher suites.
> TLS 1.2 supports PFS but it is optional.
> PFS is a key reason organizations should migrate to TLS 1.3.

---

### 5.7 Birthday Paradox and Birthday Attack

> [!NOTE]
> **Birthday Paradox:**
> In a group of 23 randomly chosen people, there is a >50% probability that two people share a birthday.
> Despite 365 days in a year, the threshold for collision is far lower than intuition suggests.

**Birthday Attack in Cryptography:**
A birthday attack exploits this mathematical phenomenon to find **collisions** in hash functions — two different inputs that produce the same hash output.

**Mathematical basis:**
```
For a hash function producing n-bit output:
Expected collisions can be found with approximately 2^(n/2) attempts
(not 2^n as you might expect)

SHA-1 (160-bit):   Would expect to need 2^160 attempts
Birthday attack:   Only needs ~2^80 attempts → feasible for well-funded attackers
SHA-256 (256-bit): Birthday attack needs ~2^128 → currently secure
```

**Why it matters:**

| Attack | Hash Function Targeted | Result |
|--------|----------------------|--------|
| **MD5 collision** | MD5 (128-bit) | Two different documents with same MD5 hash — demonstrated in 2004 |
| **SHA-1 SHAttered** | SHA-1 (160-bit) | Google/CWI demonstrated SHA-1 collision in 2017 (first practical attack) |
| **Certificate forgery** | Weak hash in cert signing | Rogue CA certificate creation |

> [!TIP]
> **Defense against birthday attacks:** Use hash functions with output length ≥ 256 bits.
> SHA-256 requires ~2^128 operations for a birthday attack — currently infeasible.
> This is why MD5 and SHA-1 are deprecated for security purposes.

---

### 5.8 Frequency Analysis — Attack on Classical Ciphers

> [!NOTE]
> **Frequency Analysis** — developed by Al-Kindi (~800 AD) — exploits the statistical distribution of letters in a language to break substitution ciphers.

**English letter frequency (approximate):**
```
E  (12.7%) T  (9.1%) A  (8.2%) O  (7.5%) I  (7.0%)
N  (6.7%) S  (6.3%) H  (6.1%) R  (6.0%) D  (4.3%)
...
```

**Attack on Caesar/monoalphabetic ciphers:**
```
Step 1: Count frequency of each ciphertext letter
Step 2: Map most frequent ciphertext letter → 'E' (most common in English)
Step 3: Derive the shift from that mapping
Step 4: Decrypt entire message
```

**Why polyalphabetic ciphers (Vigenère) resist basic frequency analysis:**
The same plaintext letter maps to different ciphertext letters → flattens frequency distribution.

**Breaking Vigenère with Kasiski Test:**
```
Step 1: Find repeated sequences in ciphertext
Step 2: Measure distances between repetitions
Step 3: GCD of those distances = probable key length
Step 4: Split ciphertext into streams (each stream = Caesar cipher)
Step 5: Apply frequency analysis to each stream
```

---

### 5.9 Known Plaintext vs Chosen Plaintext Attacks

> [!NOTE]
> These are formal cryptanalytic attack models — important for understanding cipher strength.

| Attack Model | What Attacker Has | What Attacker Wants |
|-------------|------------------|-------------------|
| **Ciphertext-Only (COA)** | Only ciphertext | Recover plaintext or key |
| **Known Plaintext (KPA)** | Some plaintext + corresponding ciphertext pairs | Recover key or decrypt other ciphertext |
| **Chosen Plaintext (CPA)** | Can choose plaintexts and get corresponding ciphertext | Recover key — stronger than KPA |
| **Chosen Ciphertext (CCA)** | Can choose ciphertexts and get corresponding decryption | Strongest model |
| **Adaptive Chosen Ciphertext (CCA2)** | CCA with ability to adapt based on previous results | Strongest practical model |

**Historical examples:**
- **WWII Enigma breaking (KPA):** Allies knew certain messages would contain predictable phrases ("Heil Hitler", weather reports) — used as cribs (known plaintext) to break Enigma.
- **AES-ECB weakness (CPA):** Identical plaintext blocks → identical ciphertext → chosen plaintext reveals structure.

> [!NOTE]
> A cipher is considered **semantically secure** if it is secure against chosen plaintext attacks (CPA-secure).
> AES in CBC/GCM mode with random IV is CPA-secure.
> AES in ECB mode is NOT CPA-secure — identical plaintexts reveal patterns.

---

### 5.10 Feistel Cipher Structure

> [!NOTE]
> **Feistel Cipher** (Horst Feistel, IBM, 1973) is a symmetric cipher design framework — not an algorithm itself, but a structural approach used by many algorithms including DES.

**Structure:**
```
Input: plaintext block split into Left (L) and Right (R) halves

For each round i:
  L[i+1] = R[i]
  R[i+1] = L[i] XOR F(R[i], K[i])

Where:
  F  = round function (any complex function)
  K[i] = round subkey

Decryption uses the SAME structure with subkeys in REVERSE order.
```

**Key properties of Feistel structure:**

| Property | Benefit |
|----------|---------|
| **Same structure for encrypt/decrypt** | Hardware implementation simpler |
| **F function need not be invertible** | Design flexibility |
| **Security increases with rounds** | More rounds = harder to break |

**Algorithms using Feistel structure:**

| Algorithm | Rounds | Block Size |
|-----------|--------|-----------|
| **DES** | 16 | 64-bit |
| **3DES** | 48 (3×16) | 64-bit |
| **Blowfish** | 16 | 64-bit |
| **Twofish** | 16 | 128-bit |

> [!NOTE]
> **AES does NOT use Feistel structure** — it uses a **Substitution-Permutation Network (SPN)** instead.
> This is a common MCQ trap: DES = Feistel; AES = SPN (not Feistel).

---

### 5.11 Symmetric vs Asymmetric — Complete Comparison

> [!NOTE]

| Property | Symmetric | Asymmetric |
|----------|-----------|-----------|
| **Keys** | 1 shared key | 2 keys: public + private |
| **Key distribution** | ❌ Hard — must share secretly | ✅ Easy — public key openly shared |
| **Speed** | ✅ Very fast (AES: ~1 GB/s) | ❌ Very slow (RSA: ~10 KB/s) |
| **Scalability** | ❌ Poor — n(n-1)/2 keys needed | ✅ Good — each user needs only 1 key pair |
| **Key length for 128-bit security** | 128-bit (AES-128) | 3072-bit (RSA) or 256-bit (ECC) |
| **Mathematical basis** | Substitution + Permutation | Number theory (factoring, DLP, ECDLP) |
| **Use cases** | Bulk data encryption | Key exchange, digital signatures, authentication |
| **Examples** | AES, DES, RC4, ChaCha20 | RSA, ECC, Diffie-Hellman, DSA |
| **Non-repudiation** | ❌ Cannot provide | ✅ Yes — private key is unique to owner |
| **In hybrid systems** | Encrypts data | Encrypts symmetric key |

---

### 5.12 Classical vs Modern Ciphers — Comparison

> [!NOTE]

| Property | Classical Ciphers | Modern Ciphers |
|----------|-----------------|----------------|
| **Operates on** | Letters / characters | Bits |
| **Key basis** | Simple substitution/transposition rules | Complex mathematical functions |
| **Security basis** | Secrecy of technique | Computational hardness |
| **Key size** | Small (0–25 for Caesar) | Large (128–4096 bits) |
| **Resistance to analysis** | Very weak — frequency analysis breaks most | Very strong — no known practical attacks |
| **Standardization** | None | NIST, ISO, IETF standards |
| **Examples** | Caesar, Vigenère, Playfair, Rail Fence | AES, RSA, ECC, ChaCha20 |
| **Computer-based** | No — manual | Yes — require computers |

---

### 5.13 Quantum Computing Threat to Cryptography

> [!NOTE]
> **Quantum computers** use qubits and quantum phenomena (superposition, entanglement) to solve certain mathematical problems exponentially faster than classical computers.

**Threat to current cryptography:**

| Algorithm | Quantum Attack | Impact |
|-----------|---------------|--------|
| **RSA** | Shor's Algorithm | ❌ Broken — factors n in polynomial time |
| **Diffie-Hellman** | Shor's Algorithm | ❌ Broken — solves DLP in polynomial time |
| **ECC** | Shor's Algorithm | ❌ Broken — solves ECDLP in polynomial time |
| **AES-128** | Grover's Algorithm | ⚠️ Weakened — effective key length halved to 64-bit |
| **AES-256** | Grover's Algorithm | ✅ Acceptable — effective 128-bit security remains |
| **SHA-256** | Grover's Algorithm | ⚠️ Weakened — effective 128-bit collision resistance |
| **SHA-3 / SHA-512** | Grover's Algorithm | ✅ Acceptable with sufficient output length |

**NIST Post-Quantum Cryptography (PQC) Standardization:**

| Finalist Algorithm | Type | Basis |
|-------------------|------|-------|
| **CRYSTALS-Kyber** | Key Encapsulation | Lattice-based |
| **CRYSTALS-Dilithium** | Digital Signature | Lattice-based |
| **FALCON** | Digital Signature | Lattice-based |
| **SPHINCS+** | Digital Signature | Hash-based |

> [!IMPORTANT]
> NIST finalized its first set of post-quantum cryptographic standards in **2024**.
> "Harvest now, decrypt later" attacks — adversaries record encrypted traffic today, planning to decrypt it with quantum computers in the future.
> This is why PQC migration is urgent for long-lived sensitive data.
> AES-256 and SHA-384/512 are considered quantum-resistant — symmetric/hash algorithms are less affected.

---

## 6. Abbreviations Table

| Abbreviation | Full Form | One-Line Technical Meaning |
|---|---|---|
| OTP | One-Time Pad | Theoretically perfect cipher — random key ≥ message length, used once only |
| XOR | Exclusive OR | Binary operation: output 1 only when inputs differ — basis of stream ciphers |
| DLP | Discrete Logarithm Problem | Hard math problem: given gˣ mod p and g,p — find x; basis of DH security |
| ECDLP | Elliptic Curve Discrete Logarithm Problem | DLP variant on elliptic curves — basis of ECC security |
| GCD | Greatest Common Divisor | Largest integer dividing two numbers without remainder — used in RSA key gen |
| KDF | Key Derivation Function | Function that derives a cryptographic key from a password or shared secret |
| PBKDF2 | Password-Based Key Derivation Function 2 | Standard KDF applying hash function many times to a password — PKCS#5 |
| HKDF | HMAC-based Key Derivation Function | Extracts and expands cryptographic key material — used in TLS 1.3 |
| PFS | Perfect Forward Secrecy | Property ensuring past sessions stay safe even if long-term key is compromised |
| DHE | Diffie-Hellman Ephemeral | DH key exchange using temporary keys — provides PFS |
| ECDHE | Elliptic Curve Diffie-Hellman Ephemeral | ECC-based ephemeral DH — provides PFS with smaller keys |
| COA | Ciphertext-Only Attack | Attack model where adversary has only ciphertext — weakest attack model |
| KPA | Known Plaintext Attack | Attack model where adversary has plaintext+ciphertext pairs |
| CPA | Chosen Plaintext Attack | Attack model where adversary can choose plaintexts and get ciphertext |
| CCA | Chosen Ciphertext Attack | Attack model where adversary can choose ciphertexts and get decryption |
| SPN | Substitution-Permutation Network | AES cipher structure — alternating substitution and permutation layers |
| TRNG | True Random Number Generator | Hardware-based entropy source — non-deterministic |
| PRNG | Pseudo-Random Number Generator | Deterministic algorithm — not suitable for cryptography |
| CSPRNG | Cryptographically Secure PRNG | PRNG meeting cryptographic unpredictability requirements |
| PQC | Post-Quantum Cryptography | Cryptographic algorithms resistant to quantum computer attacks |
| DSA | Digital Signature Algorithm | Asymmetric algorithm for digital signatures only — based on DLP |
| ECDSA | Elliptic Curve Digital Signature Algorithm | ECC-based digital signature — faster, smaller keys than DSA |
| GNFS | General Number Field Sieve | Best known classical algorithm for factoring large integers |
| DES | Data Encryption Standard | 56-bit symmetric block cipher — broken, replaced by AES |
| AES | Advanced Encryption Standard | 128/192/256-bit symmetric block cipher — current US standard |
| RSA | Rivest–Shamir–Adleman | Asymmetric algorithm based on integer factorization |
| ECC | Elliptic Curve Cryptography | Asymmetric cryptography using elliptic curve math — smaller keys than RSA |

---

## 7. Keywords + Concept Map

| Term | Definition | Connections | Use Cases |
|------|-----------|-------------|-----------|
| **Modular Arithmetic** | Remainder-based arithmetic (a mod n) | Foundation of RSA, DH, ECC | All public key crypto |
| **Prime Numbers** | Numbers divisible only by 1 and themselves | RSA key gen (n=p×q), DH modulus | Public key cryptography |
| **One-Way Function** | Easy to compute forward, infeasible to reverse | Hash functions, RSA, DH, ECC | Backbone of asymmetric crypto |
| **Trapdoor Function** | One-way function reversible with secret trapdoor | Asymmetric encryption, private key = trapdoor | RSA, ECC, DH |
| **XOR** | Binary op — output 1 iff inputs differ | OTP, stream ciphers, AES AddRoundKey | Encryption, hashing |
| **Caesar Cipher** | Monoalphabetic shift cipher (shift K) | Frequency analysis breaks it, Vigenère extends it | Historical context |
| **Vigenère Cipher** | Polyalphabetic cipher using keyword | Kasiski test breaks it, extends Caesar | Historical context |
| **Vernam/OTP** | XOR with random key ≥ message length — perfect secrecy | Shannon's proof, key reuse is fatal | Government comms, theoretical security |
| **Feistel Cipher** | Split-and-round block cipher structure | DES uses it; AES does NOT | DES, 3DES, Blowfish |
| **Hybrid Encryption** | AES for data + RSA for key | TLS, PGP, EFS, S/MIME | All real-world secure comms |
| **PFS** | Session keys independent of long-term keys | ECDHE, TLS 1.3 mandates it | Secure web, VPN |
| **Birthday Attack** | Finding hash collisions using birthday paradox | MD5 broken, SHA-1 broken, SHA-256 safe | Hash function security |
| **Avalanche Effect** | 1-bit input change → ~50% output bits change | Confusion + Diffusion together | All strong block ciphers |
| **CSPRNG** | Unpredictable random number generator | Key/IV generation | All cryptographic systems |
| **Post-Quantum Crypto** | Algorithms resistant to quantum attacks | Lattice-based, NIST PQC standards | Future-proofing |

---

## 8. Quick Reference Cheatsheet

### 🔸 Symmetric vs Asymmetric — One-Page Summary

| Property | Symmetric | Asymmetric |
|----------|-----------|-----------|
| Keys | 1 shared | Public + Private |
| Speed | Fast | Slow |
| Key distribution | Hard | Easy |
| n users need | n(n-1)/2 keys | n key pairs |
| Use | Bulk data | Key exchange, signatures |
| Examples | AES, DES, RC4 | RSA, ECC, DH |
| Non-repudiation | No | Yes |

---

### 🔸 Asymmetric Key Usage — Quick Map

| Operation | Key Used |
|-----------|---------|
| Encrypt message for Alice | Alice's **PUBLIC** key |
| Decrypt message received by Alice | Alice's **PRIVATE** key |
| Sign message as Bob | Bob's **PRIVATE** key |
| Verify Bob's signature | Bob's **PUBLIC** key |

---

### 🔸 Classical Ciphers Quick Reference

| Cipher | Type | Key | Broken By |
|--------|------|-----|-----------|
| Caesar | Monoalphabetic substitution | Shift 1–25 | Brute force / Frequency analysis |
| ROT13 | Monoalphabetic substitution | Fixed shift 13 | Trivially — self-inverse |
| Vigenère | Polyalphabetic substitution | Keyword | Kasiski test + Frequency analysis |
| Vernam/OTP | XOR stream | Random ≥ msg length | Unbreakable (if conditions met) |
| Rail Fence | Transposition | # of rails | Brute force |
| Playfair | Digram substitution | 5×5 matrix | Digram frequency analysis |

---

### 🔸 Cryptographic Protocols Timeline

| Year | Protocol | Status |
|------|----------|--------|
| 1976 | Diffie-Hellman | ✅ Active |
| 1978 | RSA | ✅ Active |
| 1991 | PGP | ✅ Active |
| 1994 | SSL 2.0 | ❌ Broken |
| 1995 | SSL 3.0 | ❌ Broken (POODLE) |
| 1999 | TLS 1.0 | ❌ Deprecated (RFC 8996) |
| 2006 | TLS 1.1 | ❌ Deprecated (RFC 8996) |
| 2008 | TLS 1.2 | ✅ Current |
| 2018 | TLS 1.3 | ✅ Current — recommended |

---

### 🔸 Hard Math Problems → Algorithms They Protect

| Hard Problem | Algorithm Using It |
|-------------|-------------------|
| Integer Factorization | RSA |
| Discrete Logarithm | Diffie-Hellman, DSA, ElGamal |
| ECDLP | ECC, ECDH, ECDSA |
| Lattice Problems | Post-Quantum (CRYSTALS-Kyber, Dilithium) |

---

### 🔸 Attack Models — Strength Order

```
Weakest ──────────────────────────────────────────── Strongest

COA → KPA → CPA → CCA → CCA2 (Adaptive)
(Ciphertext   (Known    (Chosen   (Chosen    (Adaptive
 Only)        Plaintext) Plaintext) Ciphertext) CCA)
```

---

### 🔸 Quantum Impact on Algorithms

| Algorithm | Post-Quantum Status |
|-----------|-------------------|
| RSA-2048 | ❌ Broken by Shor's |
| DH / ECDH | ❌ Broken by Shor's |
| AES-128 | ⚠️ Weakened (→ 64-bit effective) |
| AES-256 | ✅ Acceptable (→ 128-bit effective) |
| SHA-256 | ⚠️ Weakened (→ 128-bit collision) |
| SHA-3 / SHA-512 | ✅ Acceptable |
| CRYSTALS-Kyber | ✅ PQC standard |

---

## 9. Session Revision Snapshot

### ⚡ TL;DR — 5 Bullets

- ✅ Modular arithmetic, prime numbers, GCD, and XOR are the mathematical building blocks of all modern cryptography — everything else builds on these
- ✅ Symmetric = same key both sides (fast, key distribution hard); Asymmetric = public/private key pair (slow, solves key distribution) — hybrid uses both
- ✅ One-way functions + trapdoor functions are WHY asymmetric crypto works — easy to encrypt (one-way), only private key (trapdoor) can decrypt
- ✅ Vernam/OTP is the ONLY provably unbreakable cipher — but impractical; Vigenère was unbroken for 300 years but falls to Kasiski test + frequency analysis
- ✅ TLS 1.0/1.1 and all SSL versions are deprecated; TLS 1.3 is current standard and mandates PFS via ECDHE

---

### 🎯 MCQ-Likely Concepts — Everything Examiners Love

| Concept | Why It's Tricky |
|---------|----------------|
| Asymmetric: encrypt with receiver's PUBLIC key | Students often say "private key" |
| Sign with PRIVATE key, verify with PUBLIC key | Opposite of encryption direction — constantly confused |
| DES = Feistel structure; AES = SPN (NOT Feistel) | Very commonly tested distinction |
| OTP conditions — ALL 4 must be met for perfect secrecy | Many list only 2–3 conditions |
| Key reuse in OTP → C1 XOR C2 = P1 XOR P2 → key cancels | Exact mechanism of OTP key reuse attack |
| n(n-1)/2 keys for symmetric; n key pairs for asymmetric | Formula must be memorized |
| PRNG ≠ CSPRNG — using PRNG for crypto keys is dangerous | Platform-specific CSPRNG names tested too |
| TLS 1.3 mandates PFS — TLS 1.2 does not mandate it | Version-specific difference |
| Birthday attack needs 2^(n/2) not 2^n operations | Counterintuitive — key number |
| AES-256 is Grover-resistant (quantum); RSA is not | Quantum impact varies by algorithm type |
| DLP → DH/DSA; Factoring → RSA; ECDLP → ECC | Hard problem to algorithm mapping |
| `cipher /w` = free space wipe ≠ encryption | Revisited from Session 02 |
| ROT13 is self-inverse: ROT13(ROT13(x)) = x | Special property of 13 mod 26 = 13 |
| Vigenère broken by Kasiski test (1863) — not brute force | Attack method specificity |
| P vs NP: if P=NP proven → all public key crypto breaks | Theoretical but high-value MCQ |

---

<details>
<summary>🔬 Lab Content (Session 03 — No Lab Assigned)</summary>

No lab is assigned for Session 03 in the syllabus.

Lab work for symmetric and asymmetric cipher hands-on begins in **Session 05 using CrypTool**, which covers:
- Classical ciphers: Caesar, Vernam, Substitution, XOR
- Modern symmetric: DES, RC4, AES, Triple DES
- Asymmetric: RSA, ECC

The mathematical foundations covered in Session 03 (modular arithmetic, prime numbers, XOR, Feistel structure, key generation concepts) are prerequisites for understanding what CrypTool is demonstrating in those labs.

</details>

---