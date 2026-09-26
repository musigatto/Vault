---
type: note
module: "04"
lo: "11"
tags: [concept, tool, mod/04]
topic: "IDS Components"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-04]]

# IDS Components (§4.11)

Components: **Network sensors · Analyzer · Alert systems · Command console · Response system · Attack-signature database**. (Visual: [[40-Canvas/04-network-perimeter-map.canvas|Network Perimeter Map]])

## Network sensors
- Hardware/software connected to the network that **reports to the IDS**; primary data-collection point; collects data from the data source → passes to alert systems
- Integrates with event generator (data-collection component); data collection per **event-generator policy** (defines filtering mode for event-notification info)
- **Filters + discards irrelevant data** from event set; checks traffic for malicious packets → triggers alarm → alerts IDS; on IDS confirmation, generates **automatic response to block attack-source traffic**
- Placement: at **common entry points** — internet gateways, between LAN connections, remote-access servers (dial-up), **either side of the firewall**, VPN devices

## Command console
- Software acting as the **admin↔IDS interface**; receives + analyzes security events, alert messages, log files; evaluates events from different security devices; allows processing large activity volumes + fast response (big networks)
- **Install on a dedicated system**: non-dedicated (firewall/backup server) → drastically slower event response

## Alert systems
- Trigger an alert when sensors detect malicious activity; communicate the type + source of the activity; IDS uses triggers to respond/take countermeasures
- Alert delivery: **pop-up windows · email · sounds · mobile messages**
- Three alert outcomes: **true positive** (correctly identified successful attack) · attack correctly identified but failed objectives (irrelevant?) · **false positive** (event misidentified as attack)
- More IDSs → more alerts to analyze; IDSs are imperfect → false positives + non-relevant positives expected

## Response system
- Issues countermeasures on detected intrusion: **log out user · disable account · block attacker source address · restart server/service · close connections/ports · reset TCP sessions**
- Admins can let the response system auto-act or respond themselves; handle false positives by allowing traffic through; define countermeasure level per **severity**
- Real-time corrective action (product/severity-dependent); common active responses: raise IDS sensitivity to gather more intel; reconfigure systems/network devices (routers, firewalls) to stop/block the attacker
- Recommendation: **do not rely solely on the IDS response system**; you must be involved, able to respond on your own, decide false-positive handling and escalation

## Attack signature database
- Stores previously detected signatures; IDS compares in-flow packet signatures vs database entries
- On match → raise alert + block suspicious traffic
- **Periodically update** the database to catch new attack types
- Admins, not the IDS, judge security alerts (IDS can't make such decisions); normal-traffic logs also matched against current traffic

## Intrusion detection process (collaboration)
1. **Install database signatures** (before detection; with IDS software/hardware)
2. **Gather data** (sensors monitor packets allowed by firewall; malicious → sensor alert)
3. **Alert message sent** (match signature/deviate from normal → alert to command console for admin evaluation)
4. **IDS responds** (pop-up/email notify admin; or auto counter-action: drop packet, restart traffic)
5. **Administrator assesses damage** (decide countermeasures; update signature DB to kill false positives)
6. **Escalation procedures if necessary** (policy-written actions on true positive; vary by severity)
7. **Events logged and reviewed** (log intrusion events; review to decide future countermeasures + update signatures)

## Cards
Q:: Six IDS components?
A:: Network sensors, analyzer, alert systems, command console, response system, attack-signature database.
#flashcard
Q:: Alert delivery methods?
A:: Pop-up windows, email, sounds, mobile messages.
#flashcard
Q:: True vs false positive alert?
A:: True positive = correctly identified successful attack; false positive = event misidentified as attack.
#flashcard
Q:: Response system countermeasures?
A:: Log out user, disable account, block attacker source, restart server/service, close connections/ports, reset TCP sessions.
#flashcard
Q:: IDS detection process steps?
A:: Install signatures → gather data → alert sent → IDS responds → admin assesses damage → escalation → events logged/reviewed.
#flashcard
Q:: Where to place sensors?
A:: Internet gateways, between LAN connections, remote-access/dial-up servers, either side of firewall, VPN devices.
#flashcard