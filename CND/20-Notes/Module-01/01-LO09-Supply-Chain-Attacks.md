---
type: note
module: "01"
lo: "09"
tags: [threat, mod/01]
topic: "Supply Chain Attack Techniques"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-01]]

# Supply Chain Attacks (§1.9)

## Definition
- Cyberattack infiltrating an organization by targeting suppliers, third-party vendors, or supply-chain elements (value chain / third-party attack)
- Attackers focus on third parties with weaker security to reach the ultimate target; vendors unknowingly release infected updates with valid signatures

## Categories
| Category | Mechanism / Examples |
|---|---|
| Hardware-based | Tamper with hardware in supply chain (malicious hardware, malicious USB, firmware manipulation, manufacturing equipment, malicious microchips on circuit boards) |
| Software-based | Exploit OS/application code weaknesses; malware injection in updates, trojanized libraries, supply-chain backdoors |
| Firmware-based | Malicious code in device boot code (firmware vulns, insecure boot, firmware rootkits, hardcoded backdoors) |
| Malware distribution | Attacks distribution channels of legit software/updates (SolarWinds, fake browser extensions) |
| Third-party vendor supplier | Compromise supplier systems via stolen vendor credentials (outsourced service attack, supplier-email breach) |

## Techniques (Table 1.2)
| Technique | Example |
|---|---|
| Malware infection | Spyware steals employee credentials |
| Social engineering | Phishing, fake apps, typo-squatting, Wi-Fi impersonation |
| Brute-force | Guessing an SSH password, web login |
| Exploiting software vulnerability | SQL injection, buffer overflow |
| Exploiting configuration vulnerability | Mis-configuration / configuration issue |
| Physical attack/modification | Modify hardware, physical intrusion |
| OSINT | Search online for credentials, API keys, usernames |
| Counterfeiting | Malicious-purpose USB imitations |

## Targeted assets (Table 1.3)
| Asset | Example |
|---|---|
| Data | Video feeds, documents, payment data, emails, sales data, flight plans, IP |
| People | Individuals targeted for knowledge or position |
| Software | Modification of customer-access / source code |
| Processes | Documentation of internal processes, schematics, inserting malicious processes |
| Personal data | Employee records, credentials |
| Financial | Hijack bank accounts, money transfers, steal cryptocurrency |
| Bandwidth | DDoS, SPAM, large-scale infection |

## Notable examples
- **SolarWinds (2020)**: trojan embedded in Orion updates via vulnerable SolarWinds FTP update server; backdoor + blended activity; evaded AV
- **Dependency Confusion (2021)**: Alex Birsan exploited app dependencies — Microsoft, Apple, Tesla
- **Mimecast (2021)**: security certificate authenticating Mimecast on Microsoft 365 Exchange Web Services compromised (~10% customers affected)
- **Kaseya VSA (2021)**: REvil exploited a known zero-day; affected 1,500 businesses / 60 direct clients; $70M ransom; master decryption key obtained a week later
- **British Airways (2018)**: Magecart attack; 380,000+ transactions; spread from one vendor to BA, Ticketmaster
- **Event-stream (2018)**: GitHub repository injected with malware used via dependencies
- **ASUS (2018)**: auto-update mechanism injected malware into users' systems (Symantec discover)

## Vulnerabilities & attack surfaces
- Unpatched software/firmware · weak/compromised credentials · lack of encryption · lack of authentication · malware/backdoors
- Software supply-chain surfaces: Git · software dependencies · deployment tools · version control systems · testing tools · cloud hosting providers · applications

## Detection methods
1. **Continuous vulnerability scanning** (automated, dev+security teams; source code, processes, services; component + third-party ratings)
2. **Penetration testing** — simulate probable attack sequences; **honeypot** with dummy data + endpoint-detection for observability

## Prevention (best practices)
Vendor & supplier assessment · secure communication (encrypted channels) · code & software review (open-source + static, verify dependencies) · **signed & verified updates** (code signing) · **PAM** + MFA for privileged/admin accounts · access control & privilege management · monitor supply chain (IDS, **honeytokens**, SIEM) · secure development practices · trustworthy sources (no pirated/unverified) · **Zero Trust Architecture (ZTA)** — PE (policy engine) decides, PA (policy administrator) communicates, PEP (policy enforcement point) blocks/permits · strict **shadow IT** rules · risk assessment (questionnaires, on-site visits) · network segmentation by business function

## Cards
Q:: ZTA operating components?
A:: Policy Engine (PE) decides permitted traffic, Policy Administrator (PA) communicates the decision, Policy Enforcement Point (PEP) blocks or permits requests.
#flashcard

Q:: Two methods for finding supply-chain vulnerabilities?
A:: Continuous (automated) vulnerability scanning and penetration testing with honeypots.
#flashcard

Q:: What is a honeytoken?
A:: A fake resource posing as private information that activates a signal when attackers interact with it, alerting the organization and detailing the breach technique.
#flashcard