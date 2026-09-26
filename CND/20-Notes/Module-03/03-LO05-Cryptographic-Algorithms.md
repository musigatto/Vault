---
type: note
module: "03"
lo: "05"
tags: [crypto, mod/03]
topic: "Cryptographic Algorithms"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-03]]

# Cryptographic Algorithms (§3.5)

## Symmetric block/stream ciphers
### DES & 3DES
- **DES**: symmetric; 64-bit blocks under a **56-bit key** (8 bits = error detection); block cipher (fixed-length plaintext → same-length ciphertext); archetypal; hardware-implementable, single-user encryption
- ~72 quadrillion+ possible keys; random key per message
- **3DES**: interim since DES insecure; DES **three times with three keys** (K1, K2, K3 in a key bundle): **encrypt K1 → decrypt K2 → encrypt K3**
  - Option 1: three independent keys (**most secure**) · Option 2: K1=K3 · Option 3: all three identical (**least secure**)

### AES
- **NIST** spec; symmetric-key, **iterated block cipher** (repeats defined steps); 128-bit block, keys **128/192/256** (AES-128/-192/-256)
- US government: secures **sensitive but unclassified** material; efficient in software + hardware; works at multiple network layers

### RC4 / RC5 / RC6 (Rivest)
| Algorithm | Type | Key traits |
|---|---|---|
| **RC4** | variable-length key **stream cipher**, byte-oriented, random permutation | period > 10^100; fast in software; SSL traffic encryption |
| **RC5** | fast symmetric **block cipher**, parameterized (variable block/key size + rounds) | blocks 32/64/128 bit, rounds 0–255, keys 0–2040 bit; operations: integer addition, XOR, data-dependent rotation (key table) |
| **RC6** | symmetric block cipher derived from RC5 | adds **integer multiplication** (diffusion + speed) and **four 4-bit working registers** (RC5 has two 2-bit) |

## Asymmetric / signature algorithms
### DSA
- **FIPS 186** (NIST → DSS); generation + verification of digital signatures, sensitive/unclassified apps; 320-bit signature with 512–1024-bit security
- Processes: **generation** (private key → who signed) · **verification** (public key → genuine?)
- Benefits: less forgery than written signatures · quick business transactions · reduces fake-currency problem

### RSA (Rivest-Shamir-Adleman)
- Public-key cryptosystem for internet encryption + authentication; **two large prime numbers**, modular arithmetic; de-facto standard (Microsoft, Apple, Sun, Novell, secure phones, ethernet cards, smart cards)
- Hybrid exchange example: 1) sender encrypts message with random **DES** key 2) RSA-encrypts the DES key with recipient's public key 3) transmits **RSA digital envelope** (DES-encrypted message + RSA-encrypted DES key) 4) recipient decrypts DES key → decrypt message ⇒ **speed of DES + key-management convenience of RSA**

## Message digest / hash
- Message digest = unique fixed-size bit string (128–256 bits) of arbitrary input; one-way hash functions (almost impossible to invert); ~50% output change per input-bit change; computationally infeasible collision
- Role: **integrity** in document management; part of digital signatures; faster than signature algorithms; hides contents/source

### MD5 / MD6
- **MD5**: 128-bit (16-byte) digest; digital-signature apps, file-integrity checking, password storage; **not collision resistant** → prefer MD6/SHA-2/SHA-3
- **MD6**: **Merkle-tree-like structure** → massive parallel hashing of long inputs; resistant to differential cryptanalysis

### SHA family
- NIST = Secure Hash Standard (**FIPS PUB 180**); cryptographically secure one-way hash; slower than MD5 but larger digest → safer vs brute-force collision/inversion
| | Digest | Notes |
|---|---|---|
| SHA-0 | 160-bit | original 1993, withdrawn due to "significant flaw" |
| SHA-1 | 160-bit | from max message (2^64−1) bits; resembles MD5 (NSA design); **no longer approved** (collision weaknesses) |
| SHA-2 | 224/256/384/512 | family: **SHA-256** (32-bit words), **SHA-512** (64-bit words); truncated: SHA-224, SHA-384 |
| SHA-3 | 224/256/384/512 (+ SHAKE128/256) | **sponge construction**: message blocks XOR'd into initial state, then invertibly permuted; same hash lengths as SHA-2, different internals |

## HMAC
- **Message authentication code** using a cryptographic key + hash function (embedded SHA-1 or MD5)
- Strength depends on embedded hash function, key size, hash-output size
- Two stages: input key → **inner key + outer key**; stage 1 hashes inner key+message (internal hash); stage 2 hashes stage-1 output + outer key (final HMAC)
- Runs underlying hash **twice** → protects from **length-extension attacks**; key/output size e.g., 128-bit (MD5) or 160-bit (SHA-1); verifies data integrity + message authentication

## Cards
Q:: DES vs 3DES keys?
A:: DES 64-bit block / 56-bit key; 3DES = DES thrice (encrypt K1, decrypt K2, encrypt K3) — independent keys most secure, identical keys least.
#flashcard

Q:: AES parameters?
A:: 128-bit block; key sizes 128/192/256; iterated block cipher (NIST).
#flashcard

Q:: RC6 vs RC5?
A:: RC6 adds integer multiplication + four 4-bit working registers.
#flashcard

Q:: DSA basis + hash size?
A:: FIPS 186 digital signature standard; 320-bit signature, 512–1024-bit security.
#flashcard

Q:: RSA digital envelope?
A:: DES-encrypted message + RSA-encrypted DES key.
#flashcard

Q:: SHA generations?
A:: SHA-1 (160-bit, deprecated), SHA-2 (SHA-256/512 + truncations), SHA-3 (sponge construction).
#flashcard

Q:: HMAC key property?
A:: Uses inner+outer keys; executes hash twice → resists length-extension attacks.
#flashcard