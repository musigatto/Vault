---
type: note
module: "01"
lo: "07"
tags: [threat, mod/01]
topic: "Cloud-specific Attack Techniques"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-01]]

# Cloud-specific Attacks (§1.7)

## Threat list (39) — highlights
Data breach/loss · abuse & nefarious use of cloud services · insecure interfaces & APIs · insufficient due diligence · shared technology issues · unknown risk profile · unsynchronized system clocks · improper data handling/disposal · client-hardening conflicts · loss of operational/security logs · malicious insiders · illegal access · loss of reputation from co-tenant activity · privilege escalation · natural disasters · hardware failure · supply chain failure · modifying network traffic · isolation failure · cloud provider acquisition · management interface compromise · network management failure · authentication attacks · VM-level attacks · lock-in · licensing risks · loss of governance · loss of encryption keys · jurisdiction changes · malicious probes/scans · theft of equipment · cloud service termination · subpoena & e-discovery · backup data loss/modification · compliance risks · **EDoS** (economic denial of sustainability) · lack of security architecture · hijacking accounts · subscribing

## Service Hijacking
- **Via social engineering**: steal CSP/client credentials (phishing, pharming, SE, software vuln); fake login page → user enters creds → attacker logs in; result: exposed customer/credit-card/personal data
- **Via network sniffing**: packet sniffers (**Wireshark**, **Capsa Portable Network Analyzer**) capture passwords, session cookies, UDDI/WSDL files during unencrypted transmission

## Side-channel Attack (cross-guest VM breach)
- Attacker places malicious VM near target (same physical host), monitors shared physical resources (processor cache) to steal crypto keys/plaintext secrets
- Kinds: **timing attack · data remanence · acoustic cryptanalysis · power monitoring · differential fault analysis**
- Possible via vulnerabilities in shared technology (co-residency)

## Wrapping Attack
- Performed during translation of a **SOAP message** in the TLS layer
- Flow: user request → web server → SOAP message (header+body) → attacker intercepts → duplicates document, adds copy to header, modifies original → server authenticates duplicated signature → malicious code runs on cloud

## Man-in-the-Cloud (MITC)
- Advanced MITM; exploits **cloud file sync services** (Google Drive, DropBox) for data compromise, C&C, data exfiltration
- Attacker's sync token is planted/steals victim's token; restores original token afterward to avoid detection; traffic indistinguishable from legitimate

## Cloud Hopper
- Targets **managed service providers (MSPs)**; spear-phishing w/ custom malware to compromise staff accounts
- Uses **PowerShell / PowerSploit** scripting, C2 sites, domain spoofing, **fileless malware** (memory-resident); lateral movement in cloud environments
- Flow: infiltrate MSP → access customer profiles → compress & store in MSP → extract → launch further attacks

## Cloud Cryptojacking
- Unauthorized use of cloud resources to mine digital currency; external attackers + rogue insiders
- Vectors: cloud misconfigurations, compromised websites, client/server-side vulns; hidden via encoding, redirection, obfuscation
- Miners: **CoinHive**, **Cryptoloot** (JavaScript-based, run in victim browser)

## Cloudborne
- Vulnerability in **bare-metal cloud servers** (single tenant); backdoor in firmware survives reallocation
- Exploits **baseboard management controller (BMC)** (remote mgmt via **IPMI**) on SuperMicro hardware; improper firmware re-flash during reclamation keeps backdoor alive → monitoring, disable server, intercept data, ransomware

## OWASP Top 10 Cloud Security Risks (R1–R10)
| Risk | Description |
|---|---|
| R1 | Accountability & Data Ownership — public cloud → loss of control; recoverability risk |
| R2 | User Identity Federation — multiple identities/creds across providers, lifecycle control |
| R3 | Regulatory Compliance — data secure in one country may be insecure in another |
| R4 | Business Continuity & Resiliency — monetary loss if provider fails BC |
| R5 | User Privacy & Secondary Usage of Data — share features jeopardize personal data |
| R6 | Service & Data Integration — unsecured data in transit → eavesdropping/interception |
| R7 | Multi-Tenancy & Physical Security — inadequate logical segregation → tenant interference |
| R8 | Incidence Analysis & Forensic Support — distributed logs across countries hinder forensics |
| R9 | Infrastructure Security — misconfig enables scanning (unused ports, default passwords) |
| R10 | Non-Production Environment Exposure — dev/test envs increase unauthorized access risk |

## Cards
Q:: What is a wrapping attack?
A:: During SOAP message translation in the TLS layer, the attacker duplicates the body, modifies the original, and sends it as a legitimate user; the server authenticates the duplicated signature.
#flashcard

Q:: What is a Man-in-the-Cloud attack?
A:: Advanced MITM exploiting cloud synchronization services (Google Drive, DropBox) via stolen sync tokens for data compromise, C&C, and exfiltration.
#flashcard

Q:: Name five side-channel attack kinds.
A:: Timing attack, data remanence, acoustic cryptanalysis, power monitoring, differential fault analysis.
#flashcard