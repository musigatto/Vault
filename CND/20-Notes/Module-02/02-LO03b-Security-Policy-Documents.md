---
type: note
module: "02"
lo: "03"
tags: [policy, mod/02]
topic: "Security Policy Documents — Specific Policy Types"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-02]]

# Security Policy Documents (§2.3) — part b

## Acceptable Use Policy (AUP)
- Rules by network/website owners; defines proper use of computing resources; user responsibilities to protect account info
- Covers principles, prohibitions, reviews, penalties; prohibits personal use of corporate resources
- New members **sign the AUP before accessing info systems**; network defenders run regular security audits; penalties range from account disabling to legal action

*Design considerations:* read/copy others' files · modify non-owned read/write files · `.rhosts` usage · account sharing · config copies for personal use · duplicating copyrighted software

## User Account Policy
- Specifies requesting/maintaining an account; creation, deletion, operation; user rights & responsibilities; username/password rules, encryption standards, password-recovery verification, allowed devices
- Network defender responsibilities: 
  1. **Account types** — administrator (admins only) + standard (all employees)
  2. **Permissions** per designation/group (e.g., standard HR set)
  3. **Auto-lock** — length of time for automatic lockout
- Content: approval authority · who may use resources · sharing/multiple accounts · rights & responsibilities · disable & archive timing · inactivity period · password construction & aging rules
- Example wording: *"Employees may only have one official account per system… must read and sign the AUP prior to requesting an account."*

## Remote Access Policy
- Defines acceptable guidelines for remote access; helps geographically dispersed networks; minimize damage from external traffic
- Media: dial-in modems, frame relay, ISDN, DSL, VPN, SSH, Wi-Fi
- Points: strict **user authentication** · **information encryption** on shared infra · restrict reconfiguring network devices/3rd-party networks · **antivirus + OS patches** up to date · **data access** by role
- Defender duties: approved AV/firewall/malware · VPN authentication method · access control on remote system · listed allowed devices

## Information Protection Policy
- Guides employees to defend data/physical devices from unauthorized access; prevents external sharing/modification
- New employees sign the policy
- Draft on: authenticated-user list · process/method of saving sensitive info (archive/encrypt) · **location** where sensitive info is stored (only-authorized location)

## Firewall Management Policy
- Defines access/mgmt/monitoring of firewalls
- Defender duties: service/application **authentication** before "Allow" · set up **dashboard** of threats/vulns · **anti-spoofing protection** (source IP = gateway interface) · **no Telnet** · FTP only for vendor error-log uploads · avoid direct client↔external connection (use **proxy servers**)

## Special Access Policy
- Terms/conditions for granting special access
- Only **privileged users** (top management, administrators) · **password rules** (strength, validity) · **revoking privileges** notification

## Network Connection Policy
- Standards for connecting computers/servers/devices
- Points: connection rules (incl. personal phones — no network changes) · **authenticate** devices on every connection · employee responsibility for their systems meeting security standards (org can deny non-compliant devices)

## Business Partner Policy
- Guidelines partners follow to run business securely; care for geographical/cultural differences
- Areas: **need of policy** (rules/regex differ per org; work out third way) · common security boundaries + regulation · **resource sharing limits** (breach → legal action) · **record maintenance** (log every transaction)

## Email Security Policy
- Proper corporate email use; a personal email from corporate account can leak info
- Gains: competitive accomplishment (email etiquette) · employee productivity · less employer liability
- Defender duties: **use & limitations** (don't open malicious attachments) · define personal-use extent · **monitoring** disclosure · **email duration** (archive timing) · **encryption** policy awareness · **actions against non-compliance**

## Password Policy
- Encourages robust passwords:
  - Length **8–14 characters**; uppercase + lowercase + digits + special (`@ % $ & ;`) · case-sensitive · **unique** (history: no reuse) · **max age 60 days**, min age no limit
- Formation: digits · special chars · upper/lower · avoid personal info · no company name
- Duration: change regularly — usually **every 90 or 180 days**
- Common practices: don't share account/passwords · different passwords per app · never write down · never email/phone/IM password (even to admin) · **log off/lock** when leaving desk · disclaimer (warnings → termination)

## Physical Security Policy
- Physical assets prone to damage (installations, offshore transfers)
- Design: building protection deficiency review · identify outsiders (visitors/contractors/vendors) · lighting systems · entry points blocked · badges/locks/keys/auth controls audited · video surveillance monitored

## Information System Security Policy
- Safeguards information systems from malicious use
- Points: **antivirus installation** · **regular software updates** · **firewall** · **OS upgrades** · **password policy** · **physical security standards**

## BYOD (Bring Your Own Device) Policy
- Guidelines to maximize benefits/minimize risks for personal devices on the org network
- Aspects: **permissible devices** (by designation) · **permissible resources** · **disabled services** (verify/disable vulnerable) · **data storage** (separate drive) · **security measures** for data/device (monitor)
- Admin duties: device/software list (smartphones/laptops with model, OS version) · resources by designation (email/contact/calendar/process docs) · disable illicit material, proprietary info, harassment, other business activities · store via device/server/cloud · password+encryption policies, monitor data transfer

## Software/Application Security Policy
- Secures inbuilt & purchased applications across the life cycle; threats: software tampering, parameter manipulation, authorization, cryptography
- Key factors: **data validation · session management · authentication · authorization · encryption**
- Defender role: data-validation criteria · authentication process (no 3rd-party installs w/o admin rights) · authorization standards (only those who need it) · limited data access · monitoring every session

## Data Backup Policy
- Recover/safeguard during security incident/network failure; align backup/recovery with actual risk (virus/attack/natural disaster)
- Elements: **what files** (business/financial/tax/personal) · **who can access backups** (assigned privileges, backup logs) · **how often** (schedule by business + criticality; usually after business hours) · **type**:
  - **Full** — all data; simplest, most time-consuming
  - **Incremental** — only data changed since last **full** backup; less time-consuming
  - **Differential** — selected files new/changed since last full backup
- **Where** — physical external device, cloud, or both; test & evaluate all policies

## Confidential Data Policy
- High-protection info: salary, product, org-structure details
- Design: treatment (storage/access/transmission/sharing/disposal/handling/disclosure) · security controls · emergency access · use of confidential data

## Data Classification Policy
- Framework to classify org data by **sensitivity, value, criticality**; levels: **restricted, private, public**
- Points: avoid distribution of restricted/confidential internally & externally · send confidential data **encrypted via email** · secure backups with strong credentials · scan device/file after receiving confidential data · delete found-public confidential data · actions for non-adherence · regular audits
- Design: classification by **data owners** · protecting data **at rest** & **in transit** · data labeling

## Internet Usage Policy
- Rules for corporate Internet; accepted + **signed by all employees**
- Defender duties: **limited usage** (official only) · **timeframe for personal use** · **monitoring method** for web use · decide blocked content (non-trusted-site list)

## Server Policy
- Standard base configuration; restricts unauthorized access
- Documented server info: name · location · function/purpose · hardware (make/model) · software list (OS, programs, services) · configuration (event-log settings, services, lockdown tools, account settings)
- Enforcement: user restriction (permissioned only) · configuration compliance (monitor changes) · server registration per corporate enterprise management system · update the management system · parallelism in modifications (change-management procedure)

## Wireless Network Policy
- Rules for accessing org wireless resources; protects against wireless intrusion
- Defender duties: **access point** (register/approve; connect to org network) · **configuration** (configure SSID) · **permissible devices** (management-approved) · **permissible technologies**

## User Access Control Policy
- Controls interaction users↔systems↔resources; defines who can access (people/process/machines), what resources/files read/programs executed/data sharing
- Practices: prohibit unknown/undefined logins · **monitor powerful/admin accounts** continuously · **lock accounts after limited failed attempts** · remove unused accounts · strict access criteria · enforce **need-to-know & least privilege** · disable unrequired features & unused ports · restrict global access rules

## Switch Security Policy
- Minimal security config for switches
- Aspects: monitor data regularly · block unrequired/vulnerable services · **encrypt stored passwords/data** · restricted-area physical storage · L3 switch configured like router
- Duties: **enable password** (encrypted) · session timeouts · privileges at all levels · **SSH over Telnet** · **port security** (MAC-based) · disable unused ports (assign to unused VLAN) · configure trunk ports (unused VLAN) · static VLAN + limit trunk VLANs · **AAA framework** · switch logs to secure log host · disable CDP/dynamic trunking/Tcl scripting if unused · password-encryption + NTP config · ACLs per hierarchy · disable VTP or set transparent mode (mgmt domain, password, pruning)

## IDS/IPS Policy
- Facilitates detection/prevention of intrusions
- Design: **deploy standard IDS system** · **monitor IDS log files continuously** · **regular updates** of intruder definitions for evolving threats · **deploy IPS** for large orgs (threat detection + prevention)

## Encryption Policy
- Acceptable use & management of encryption across enterprise; applies to all network resources, users, LAN/Wi-Fi, remote WAN
- Design standards for: wired/wireless communication, servers, desktops, laptops, smartphones, removable storage, USB sticks, VPN, Wi-Fi
- Design points: **encryption algorithm** research · **hash-function changes** if required · **key type** (symmetric/asymmetric) · **verified certificates** (authenticity + provider) · **SSL/TLS certificates with trusted cert**

## Router Policy
- Minimal security config for all routers
- Points: **no local accounts** — use TACACS authentication · **enable secret password** (encrypted) · include in corporate enterprise management system (+ POC) · "Do Not Touch" warnings · comply with Router IOS Template · standardized corporate SNMP strings (avoid public/private community strings) · syslog to local RAM buffer + syslog server · VTY accepts only required protocols · **block**: invalid/spoofed source addresses, TCP/UDP small services, source routing, web services on router, IP directed broadcasts, CDP on 3rd-party interfaces

## Policy Implementation Checklist (post-build, revision, update)
- Officially adopted as company policy (senior management backed)
- Review each policy → enforcement approach
- Correct tools/techniques in place to conform
- Change plan for network + policy
- Coordinate other departments (legal, IT, HR) for supporting procedures
- **Basic security awareness training** to everyone
- Make policy available to affected employees
- Information Security Officer / IT Security Program Manager implements & manages
- Equipped with mgmt technology & tools
- **Visitors given the AUP** if allowed to use the network

## Cards
Q:: Password example length & expiration (courseware)?
A:: 8–14 chars; max age 60 days; official guidance: change every 90 or 180 days.
#flashcard

Q:: Full vs incremental vs differential backup?
A:: Full=all data, slowest · Incremental=changes since last full, faster · Differential=selected files new/changed since last full.
#flashcard

Q:: Firewall policy — Telnet & FTP stance?
A:: No Telnet (insecure); FTP only for vendor error-log uploads; use proxy servers to avoid direct connections.
#flashcard

Q:: User access control practices?
A:: Prohibit unknown logins · monitor admin accounts · lock after failed attempts · remove unused accounts · strict access criteria · need-to-know + least privilege · disable unrequired features/ports.
#flashcard

Q:: Switch security — SSH vs Telnet, port security?
A:: SSH preferred over Telnet; port security limits MAC-based access.
#flashcard

Q:: Encryption key types + certs?
A:: Symmetric or asymmetric per org needs; verify certificate authenticity/provider; servers use trusted SSL/TLS certificates.
#flashcard