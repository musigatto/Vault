---
type: moc
module: "04"
tags: [concept, mod/04]
topic: "Module 04 — Network Perimeter Security"
exam_weight: unknown
status: done
unresolved:
  - "Exam blueprint per-module weights are not stated in the courseware (Exam 312-38: 4 h, 100 questions)."
  - "Table 4.1 (LO02 firewall technology comparison) was unreadable in OCR; facts kept only from readable prose."
---
# Module 04 — Network Perimeter Security

> [!abstract] Scope
> 17 LOs · 17 sections · courseware pp. 453–624. Perimeter defense: firewall concerns/capabilities/limitations, firewall technologies, topologies, types & placement, deep-traffic-inspection selection, implementation + deployment, secure-implementation best practices, administration, IDS role/capabilities/limitations, IDS classification, IDS components, NIDS/HIDS deployment, false positive/negative alerts, IDS/IPS selection, NIDS/HIDS solutions, router/switch security, and zero-trust via SDP.

## Sections
| LO   | §    | Section                                               | Course pp. |
| ---- | ---- | ----------------------------------------------------- | ---------- |
| LO01 | 4.1  | Firewall Security Concerns, Capabilities, Limitations | 457        |
| LO02 | 4.2  | Firewall Technologies                                 | 463        |
| LO03 | 4.3  | Firewall Topologies                                   | 482        |
| LO04 | 4.4  | Hardware/Software · Host/Network · External/Internal  | 487        |
| LO05 | 4.5  | Deep Traffic Inspection (Adaptive Profile) Selection  | 495        |
| LO06 | 4.6  | Firewall Implementation and Deployment                | 499        |
| LO07 | 4.7  | Secure Firewall Implementation Best Practices         | 521        |
| LO08 | 4.8  | Firewall Administration Activities                    | 529        |
| LO09 | 4.9  | IDS Role, Capabilities, Limitations, and Concerns     | 535        |
| LO10 | 4.10 | IDS Classification                                    | 542        |
| LO11 | 4.11 | IDS Components                                        | 555        |
| LO12 | 4.12 | Effective Deployment of Network- and Host-Based IDS   | 564        |
| LO13 | 4.13 | False Positives and False Negatives                   | 570        |
| LO14 | 4.14 | Considerations for Selection of Appropriate IDS/IPS   | 579        |
| LO15 | 4.15 | Network-Based and Host-Based IDS Solutions            | 591        |
| LO16 | 4.16 | Router and Switch Security                            | 597        |
| LO17 | 4.17 | Zero-Trust Security using Software-Defined Perimeter  | 603        |

## Technical focus
- **Firewall core:** capabilities vs limitations → tech types (packet filter L3 → circuit-level session → application-level proxy → stateful multilayer → NAT/VPN/NGFW/cloud) → topologies (bastion, screened subnet, multi-/dual-homed) → placement (hardware/software, host/network, external/internal).
- **Lifecycle:** implementation phases (Plan→Configure→Test→Deploy→Manage) → best practices → administration → DPI selection (normalization, data-stream inspection, vulnerability-based).
- **IDS/IPS:** role (inside the network) → classification axes (approach: signature/anomaly/stateful-protocol; activity; structure; source; timing) → components (sensors, analyzer, alert, console, response, signature DB) → staged deployment (L1–L4) → false positive/negative rates & fixes → selection criteria → products (Snort, Zeek/Bro, Suricata, OSSEC, Wazuh).
- **Device hardening + zero trust:** router/switch measures → SDP (black cloud, CSA) defeats six traditional drawbacks; dynamic firewall, SPA, deployment models, workflow, NAC comparison, tools.

## Exam facts
- Exam **312-38** · **4 hours** · **100 questions**.
- Blueprint per-module weights: **not in courseware** → `exam_weight: unknown`.
- Strong question sources: firewall technology layers (packet filter L3 vs circuit-level session vs app-level proxy) · IDS alert math (FP rate = FP/FP+TN; FN rate = FN/FN+TP) · IDS sensor deployment levels L1–L4 · false-negative cure (behind VPN termination w/ SSL) · four alert types · SDP components/workflow (SPA, controller, gateway) · Snort vs Zeek vs Suricata vs OSSEC/Wazuh · router/switch measures (IP directed broadcast, source routing; port security static/dynamic/sticky; DHCP snooping, DAI, STP root/BPDU guards).

## Notes
```base
filters:
  and:
    - 'type == "note"'
    - file.inFolder("CND/20-Notes/Module-04")
views:
  - type: list
    name: Notes
    order:
      - file.name
```

## Module map
- Canvas: [[40-Canvas/04-network-perimeter-map.canvas|Network Perimeter Map]]
- Flows to visualize: firewall technology stack (L3 → session → app → stateful multilayer) · firewall topology (screened subnet DMZ) · firewall implementation phases · IDS alert process (signature DB → sensor → alert → response → damage assessment) · IDS deployment levels L1–L4 · false positive/negative loop · SDP workflow (client–controller–gateway, SPA → mutual VPN).

## Cross-links
- [[00-Home]]
- [[Question-Bank]] · [[Answer-Key]] · [[Mock-Exam-100]]
- Related modules: [[MOC-Module-01]] (attacks these perimeter controls stop) · [[MOC-Module-02]] (policies → router/switch baselines, change management) · [[MOC-Module-03]] (firewall/IDS/SIEM/VPN foundations, NAC) · [[MOC-Module-19]] (architecture resilience) · [[MOC-Module-05]] (endpoint hardening — Windows systems).

## Unresolved
- Per-module exam blueprint weights (not stated in courseware).
- Table 4.1 (LO02) OCR-unreadable; firewalls/tech details kept from readable prose only.

## Cards
Q:: Module 04 covers which perimeter devices?
A:: Firewalls, IDS/IPS, routers, switches, and SDP for zero-trust.
#flashcard
Q:: False positive rate formula?
A:: FP / (FP + true negative); false negative rate = FN / (FN + true positive).
#flashcard
Q:: Where should an IDS sit for encrypted traffic?
A:: Behind a VPN termination with SSL decryption, so it can match decrypted payloads.
#flashcard
Q:: SDP reverse of TCP?
A:: TCP connects → authenticates → transfers data; SDP verifies identity/device first, then connects (mutual VPN).
#flashcard