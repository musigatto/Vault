---
type: moc
module: "03"
tags: [concept, mod/03]
topic: "Module 03 — Technical Network Security"
exam_weight: unknown
status: done
unresolved:
  - "Exam blueprint per-module weights are not stated in the courseware (Exam 312-38: 4 h, 100 questions)."
  - "IPsec layer: module body classifies it at the network layer (AH/ESP), but one slide line says 'works at the application layer'."
---
# Module 03 — Technical Network Security

> [!abstract] Scope
> 8 LOs · 8 sections · courseware pp. 299–452. Technical network security: access-control models, zero trust, IAM, cryptographic techniques & algorithms, network segmentation, security solutions (firewalls, IDS/IPS, honeypots, proxies, UTM, SIEM, NAC, VPN, SOAR), and essential security protocols (RADIUS, TACACS+, Kerberos, PGP, S/MIME, S-HTTP, HTTPS, TLS, SSL, IPsec).

## Sections
| LO   | §    | Section                                                       | Course pp. |
| ---- | ---- | ------------------------------------------------------------- | ---------- |
| LO01 | 3.1  | Access Control Models                                         | 302        |
| LO02 | 3.2  | Zero-Trust and Distributed Access                             | 323        |
| LO03 | 3.3  | IAM — Authentication, Authorization, Accounting               | 339        |
| LO04 | 3.4  | Cryptographic Techniques                                      | 370        |
| LO05 | 3.5  | Cryptographic Algorithms                                      | 383        |
| LO06 | 3.6  | Network Segmentation                                          | 395        |
| LO07 | 3.7  | Essential Network Security Solutions                          | 402        |
| LO08 | 3.8  | Essential Network Security Protocols                          | 436        |

> [!note] LO07 splits into two notes: `a` (firewalls, IDS/IPS, honeypots, proxy servers, protocol analyzers, web content filters, pp. 402–423) and `b` (load balancers, UTM, SIEM, NAC, VPN, SOAR, pp. 423–435).

## Technical focus
- **Access control fence:** MAC/DAC/RBAC/ABAC + Bell-LaPadula/Biba + XACML (PDP/PEP/PAP) → **Zero Trust** (NIST SP 800-207) → **IAM** (authn factors vs authz, PAM, SSO, EAP).
- **Crypto pairing:** symmetric vs asymmetric → algorithms (DES/3DES/AES, RC4/5/6, DSA/RSA, MD5/MD6/SHA-1/2, HMAC) → applied protocols (SSL/TLS, IPsec AH/ESP, PGP/S/MIME, RADIUS/TACACS+/Kerberos).
- **Perimeter:** segmentation (DMZ) → layered solutions (firewall → IDS/IPS → Honeypot → UTM/SIEM/NAC/SOAR) → VPN tunneling (L2/L3: IPsec, PPTP, L2TP, SSL).

## Exam facts
- Exam **312-38** · **4 hours** · **100 questions**.
- Blueprint per-module weights: **not in courseware** → `exam_weight: unknown`.
- Strong question sources: NAC actions/detection checks · RADIUS vs TACACS+ (ports/UDP-TCP, encryption) · Kerberos ticket flow · IPsec AH vs ESP · UTM pros/cons · honeypot types · load-balancer characterizations.

## Notes
```base
filters:
  and:
    - 'type == "note"'
    - file.inFolder("CND/20-Notes/Module-03")
views:
  - type: list
    name: Notes
    order:
      - file.name
```

## Module map
- Canvas: [[40-Canvas/03-technical-network-security-map.canvas|Technical Network Security Map]]
- Flows to visualize: access-control journey (AC model → zero trust → IAM → crypto) · IDS detection chain (signature → anomaly → stateful protocol) · Kerberos ticket flow (AS → TGT → TGS → service) · network segmentation (DMZ) · RADIUS vs TACACS+ AAA difference.

## Cross-links
- [[00-Home]]
- [[Question-Bank]] · [[Answer-Key]] · [[Mock-Exam-100]]
- Related modules: [[MOC-Module-01]] (attacks these controls defend against) · [[MOC-Module-02]] (policies governing access) · [[MOC-Module-19]] (architecture resilience) · [[MOC-Module-04]] (logging/audit of the events SIEM collects)

## Unresolved
- Per-module exam blueprint weights (not stated in courseware).
- IPsec layer contradiction (network-layer AH/ESP vs one application-layer line in the module body).