---
type: note
module: "04"
lo: "05"
tags: [concept, tool, mod/04]
topic: "Deep Traffic Inspection Firewall Selection"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-04]]

# Selecting Firewalls — Deep Traffic Inspection (§4.5)

Choose a firewall by validating deep-traffic-inspection capability. Three selection drivers:

## 1. Full Data Traffic Normalization
- **Normalization prevents firewall evasion**; blocks known attacks and restricts external-host access to internal machines on probe/attack detection
- Most firewalls are **throughput-oriented** → cannot fully normalize; they can't detect complex/hard-to-see attacks
- Vendors take shortcuts → only **partial normalization** (e.g., TCP segmentation handling limited to selected protocols/ports); evasions exploit these gaps
- Requirement: normalize data traffic **to the maximum at every protocol layer** before payload inspection
- Sanitization = two sensor techniques: **clean up malformed packets** + **drop illegal packets**

## 2. Data Stream-based Inspection
- Most firewalls inspect **segments or pseudo-packets**; attackers spread malicious payloads across those boundaries to enter the network
- Requirement: constantly inspect the **data stream**, not segments/pseudo-packets
- Note: stream inspection **needs more memory + CPU**; hard to retrofit in hardware products (significant R&D) → many vendors sacrifice scope

## 3. Vulnerability-based Detection & Blocking
- Most vendors use **exploit-based** approach: packet-oriented pattern/signature with **100% match** to detect/block evasion
- Impossible to create signatures for every evasion combo (new patterns daily) → exploit-based FWs can't stop all evasions
- Requirement: choose a vendor using the **vulnerability approach** — blocks exploitation attempts at **both network and application layers**

## Cards
Q:: Two techniques of traffic normalization?
A:: (1) clean up malformed packets, (2) drop illegal packets — normalized at every protocol layer before payload inspection.
#flashcard
Q:: Why stream-based inspection for fighten evasion?
A:: Segment/pseudo-packet-only inspection misses malicious payloads spread across boundaries; stream inspection needs more RAM+CPU.
#flashcard
Q:: Exploit-based vs vulnerability-based detection?
A:: Exploit-based: 100% signature match (can't cover every evasion); vulnerability-based: block exploitation at network+application layers (preferred).
#flashcard