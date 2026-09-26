---
type: note
module: "03"
lo: "02"
tags: [concept, mod/03]
topic: "Access Control in Distributed/Mobile World — Zero Trust"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-03]]

# Access Control in the Distributed & Mobile World (§3.2)

- Cloud, mobile, IoT force **redefinition of access controls for distributed environments**; modern models enhance network security against varied threats; focus = **zero-trust model** (inside + outside threats) + architecture + implementation best practices

## Traditional: castle-and-moat model
- Only a **security perimeter** level: firewalls, proxy servers, honeypots, IPS; guards network endpoints by monitoring user activity & data flow
- **Inside the network = automatically trusted**
- Ineffective with cloud/mobile where data spans locations, systems, apps, services

*Practices for castle-and-moat dependents:*
- Annual review of employee access rights to applications
- Find/remove ambiguous & inconsistent access rights
- Review overuse of admin privileged accounts by IT
- Monitor customer data stored in multiple file shares
- Review password management policies
- Review data classification & reporting (know where data lives)
- Monitor frequent **USB flash-drive** file transfers (esp. sensitive data)

### Limitations
| Evolution | Problem |
|---|---|
| Enterprise evolution | Cloud/hybrid sprawl: physical networks, private cloud + SDN, multiple public clouds, WAN edge, IT/OT convergence, mobile workforce → perimeter can't protect; no focus on compromised identities / insider threats |
| Threat landscape evolution | Untrusted websites, web components/dependencies, malicious mobile apps; AV, next-gen firewalls, VPN insufficient; perimeter doesn't stop **lateral movement** |

## Zero Trust — *never trust, always verify*
- **No one trusted by default**, inside or outside; strict identity verification for every user/device
- Managing access to identities, data, devices; protects vs insider + outsider threats; emphasizes **visibility, analytics, automation**; also strengthens compliance
- Treats every user/application/service as a threat (vs firewall/DMZ mindset)

**Technology pillars:** micro-segmentation · multi-factor authentication (MFA) · IAM · orchestration · automation · log & packet analytics · encryption · virtual network functions (VNF)

**Focus areas:** zero trust **data · networks · people · devices · workloads**

**Deployment steps:**
1. **Identify the protect surface**
2. **Map the transaction flows**
3. **Build a zero trust architecture**
4. **Create a zero trust policy**
5. **Monitor and maintain**

## Zero-trust security principles
| Principle | Content |
|---|---|
| Workforce security | Access-control rules + authentication protocols; identify/authenticate before restricting |
| Device security | Identification + authorization of devices connecting to resources (user-controlled or autonomous) |
| Workload security | Safeguard sensitive data/critical services from tampering/unauthorized access |
| Network security | Micro-segmentation + isolation of sensitive resources |
| Data security | Isolate data to authorized individuals; storage location decisions; encryption in transit **and** at rest |
| Visibility & analytics | Automate configuration control, anomaly detection; end-to-end data visibility (AI-assisted) |
| Automation & orchestration | Automate/integrate security tools, orchestrate workflows, minimize manual work |
| Continuous improvement | Monitor/measure/adjust policies as threat landscape, business, user behavior change; use maturity models/roadmaps/scorecards |

## NIST Zero Trust Architecture (ZTA) — SP 800-207
- Produced **2018** by **NIST + NCCoE** (National Cybersecurity Center of Excellence)
- Provides **abstract definition of ZTA** + roadmap to design zero-trust systems (technology-agnostic)
- **Core tenets:** any data source/service = resource · all communication secured regardless of location · resources granted session-by-session · dynamic policy (client identity + app/service + asset + behavioral/environmental attrs) · monitor integrity/security posture of all assets · all authentication/authorization dynamic & strictly enforced before access · collect maximum info about asset/network/comms state

### Logical components (NIST 800-207)
| Component | Role |
|---|---|
| **Policy engine (PE)** | Makes & records final grant/deny decision per subject/resource (executed by PA); ~central PDP |
| **Policy administrator (PA)** | Creates session-specific tokens/credentials the client uses to access the resource |
| **Policy enforcement point (PEP)** | Activates/takes down path between subject & resource; communicates with PA, forwards requests, receives policy updates |
| **CDM system** | Determines/enforces policies on non-enterprise devices; collects asset status, configuration/software updates |
| **Industry compliance system** | Policy rules for regulatory regimes (FISMA, healthcare, financial) |
| **Threat intelligence feed(s)** | Internal + external threat/vuln data assisting the policy engine |
| **Activity logs** | Real-time/near-real-time security-posture insights |
| **Data access policies** | Foundation attributes/policies for resource access rights |
| **Enterprise PKI** | Creates/logs certificates for resources, objects, services, apps; may link to Federal CA ecosystem |
| **ID management system** | Creates/stores/manages accounts + identity credentials (e.g., **LDAP**); uses PKI artifacts |
| **SIEM system** | Gathers security-centric data for analysis → improve policies, detect attacks |

### ZTA deployment cycle (shifting to ZTA)
1. **Identify actors** in the enterprise (service accounts etc., for the PE)
2. **Identify assets** owned by enterprise (incl. non-enterprise devices, IoT, digital certs, virtual assets/containers)
3. **Identify key processes** & assess risk / business-process workflows (importance, subjects affected, current resource state; upstream/downstream entities)
4. **Formulate policies** for the candidate workflows (ensure unimpeded access to necessary resources)
5. **Identify candidate solutions** → pilot program (model, don't replace)
6. **Initial deployment & monitoring** (monitoring-only / reporting-only mode first)
7. **Expand the ZTA** (steady-state: log traffic, monitor assets, gradual policy change; continuous feedback loop)

## ZTA vs PoLP vs DiD
| | ZTA | PoLP |
|---|---|---|
| Scope | Authentication + authorization of **user/device/application** | **User access control only** |
| Trust | No trust by default; **continuous monitoring** / re-verification | Grant **minimum access rights** needed for tasks |
| Positioning | More **comprehensive security methodology** | Minimizes attack surface **after a breach**; prevents spread to other components; prevents large-scale data breaches |

| | ZTA | Defense-in-Depth (DiD) |
|---|---|---|
| Verification | **Continuous verification** of users + devices; every access request verified | **Multiple layers** of security defenses; overlapping layers safeguard if one fails |
| Threat focus | Internal **and** external | Primarily **external** |
| Other | Protects against tool-misconfiguration human errors | More cost-effective long-run |

## Best practices for building ZTA
1. **Understand the organization's network architecture** (assets, user base, devices, services/data)
2. **Create a strong device identity** — tied to device not user; identifiable offline/NAT: network-verified · cross-network verifiable · persistently verifiable · unchanged on device replacement
3. **Create a secure communication channel** — defend vs **replay attacks**; guarantee confidentiality, integrity, authenticity (non-repudiation where needed); optionally DoS defense, user/device authorization, time/location-based access
4. **Use network segmentation** — firewalls, **VLANs**, IDS/IPS between segments
5. **Verify the user with MFA** — multiple forms of identification before access
6. **Monitor and maintain continuously** — SOP adherence, dedicated security teams, embed zero trust in culture, train new employees

## Cards
Q:: Castle-and-moat flaw?
A:: Inside = automatically trusted; with cloud/mobile the perimeter is indefinable and lateral movement is unchecked.
#flashcard

Q:: Zero-trust focus areas?
A:: Data · networks · people · devices · workloads.
#flashcard

Q:: ZTA deployment steps?
A:: Identify protect surface → map transaction flows → build ZTA → create policy → monitor & maintain.
#flashcard

Q:: NIST ZTA document?
A:: NIST SP 800-207, produced 2018 with NCCoE — abstract ZTA definition + roadmap.
#flashcard

Q:: ZTA logical components roles?
A:: PE decides · PA issues session tokens/credentials · PEP turns policy on/off between subject & resource.
#flashcard

Q:: ZTA vs DiD?
A:: ZTA = continuous verification, internal + external threats; DiD = layered defenses, primarily external threats.
#flashcard