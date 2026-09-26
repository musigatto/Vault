---
type: note
module: "03"
lo: "04"
tags: [crypto, mod/03]
topic: "Cryptographic Security Techniques"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-03]]

# Cryptographic Security Techniques (§3.4)

## Encryption
- Conceals info: **plaintext → ciphertext** via key/scheme; guarantees **confidentiality + integrity** (at rest or in transit)
- Decryption = same steps, keys in reverse order
- Used in smartphones, wireless transmission, Bluetooth

### Symmetric encryption
- **Single secret key** for encrypt + decrypt (secret-key cryptography); oldest technique; encrypts **large** amounts of data
- Sender+receiver must share key beforehand → limited over the internet between strangers → solved by public-key crypto
- **Stream cipher** (bits one at a time) vs **block cipher** (blocks of bits)
- ✔ easy, faster than asymmetric · ✖ key sharing required; compromised key = data compromise at both ends

### Asymmetric encryption (public-key)
- **Public key** (encrypt) + **private key** (decrypt); for **small** amounts of data; solves key-management
- Sequence: find recipient's public key in directory → encrypt with it → recipient decrypts with private key
- Only private-key holder can decrypt; public keys must be bound to usernames securely (→ digital signatures for authentication)
- ✔ more secure, no key distribution · ✖ longer processing time, complex algorithms

## Hashing
- Fixed-length string/key representing original info; checks **integrity** on both sides (sender hash + receiver hash compare)
- Applications: **secure password storage** (hash not plaintext; reversible only via reverse algorithm) · **file integrity** (download hash match) · **message integrity** (encrypted hash travels with message)
- Limitation: **collision** (same hash for different data) — shorter hashes more collision-prone

## Digital signatures
- Cryptographic means of **authentication** via asymmetric keys; sends message + signature to receiver who verifies with public key
- Built on **hash of the message** (hash value smaller than message, unique; tamper → different hash) + sender's private key + signature function; verification = public key + verification function
- Signing slow → use message **hash** instead of the full message for performance
- Asymmetric algorithms with sign+verify functions = **digital signature algorithms**

## Digital certificates
- Solve secure public-key distribution; **trusted intermediary** binds public key with owner's name; intermediary issues certificate
- Sender signs with private key, sends certificate → receiver extracts public key from cert to verify
- **Attributes**: Serial number (unique id) · Issuer (intermediary identity) · Subject (owner) · Valid from / Valid to · Signature algorithm · Key-usage (encryption / signature / both) · Public key · Thumbprint algorithm + **Thumbprint** (hash for integrity)
- Receiver uses **CA's public key** to decode cert; OS/browsers carry authorized CA certs
- Main aim: **non-repudiation**; used in e-mail servers, **code signing**

## Public Key Infrastructure (PKI)
- Hardware, software, people, policies, procedures for **creating, managing, distributing, using, storing, revoking** digital certs; binds public keys to user identities via CA
- Components: **CA** (issues/verifies certs) · **RA** (verifier for CA) · **certificate management system** (generation/distribution/storage/verification) · **directories** (store certs + public keys)
- Digital signatures supported: identification (with whom dealing) · entitlements (who authorized for what) · verification (verifiable transaction record)
- Protocols/services: **SSL, IPsec, HTTPS** (comms) · **S/MIME, PGP** (email) · **SET** (value exchange) · chip cards, e-commerce, home banking, electronic postal
- Benefits: lower transactional cost · lower risk · better efficiency/performance · simpler binary-symmetric systems

## Zero-Knowledge Proofs (ZKP)
- **Prover** proves a statement true to **verifier** without revealing anything beyond "it is true"
- Avoids exposing **PII** (e.g., driver's license as evidence); multiple interaction rounds; verifier gains confidence without learning the statement
- Example: website accepts password → compares to server hash; with ZKP the client's password stays unknown yet login verified
- **Properties**: Completeness (true statement + honest parties → accepted) · Soundness (dishonest prover can't fool honest verifier) · Zero-knowledge (verifier learns only true/false, not content)
- **Elements**: **Witness** (secret info) · **Challenge** (verifier randomly picks multiple questions) · **Response** (prover computes answer; repeats → guessing unlikely)

## Cards
Q:: Symmetric vs asymmetric for data volumes?
A:: Symmetric single key → large data; asymmetric (public/private) keys → small data.
#flashcard

Q:: Hashing applications + limitation?
A:: Password storage, file/message integrity; limitation = collisions (worse with shorter hashes).
#flashcard

Q:: Digital certificate purpose?
A:: Bind public key to owner via trusted CA; ensure non-repudiation.
#flashcard

Q:: PKI components?
A:: CA (issue/verify) · RA (verifier) · certificate management system · directories.
#flashcard

Q:: ZKP properties + elements?
A:: Completeness, soundness, zero-knowledge; Witness, Challenge, Response.
#flashcard