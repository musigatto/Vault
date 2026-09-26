---
type: note
module: "04"
lo: "10"
tags: [concept, mod/04]
topic: "IDS Classification"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-04]]

# IDS Classification (§4.10)

Classified by: **approach · protected system · structure · data source · behavior · analysis timing**.

## Approach-based IDS
- **Signature-based (misuse detection)**: monitors data-packet patterns vs pre-configured attack **signatures** via string comparisons
  - ☑ minimal false alarms · quickly identifies specific tools/techniques · helps fast incident handling
  - ☒ **only known threats** (constant signature updates) · tight signatures miss common variants
  - Example signatures: telnet login as root (policy violation); OS log status code 645 = auditing disabled
- **Anomaly-based**: builds **statistics of normal traffic** over a time interval (bandwidth, protocols, ports, connected devices, failed logons, CPU levels); alarms on deviations
  - ☑ detects abnormal behavior/symptoms + **unknown attacks** without clear detail; info feeds misuse-detector signatures; detects probes early, wide attack range
  - ☒ **high false-positive rate** (unpredictable users/networks); needs extensive baseline event set; static model may miss known attacks
- **Stateful protocol analysis**: compares observed events vs predefined benign-activity profiles **per protocol** to find state deviations; detects unpredictable command sequences (repeated/arbitrary commands), command-length variations, attribute min/max anomalies; for authenticated protocols tracks authenticator per session (records suspicious-activity authenticator); analyzes network/transport/application-layer behavior

## Anomaly vs Misuse Detection Systems
- **Anomaly Detection System**: algorithms detect discrepancies; two steps: (1) gather data-flow info, (2) real-time processing to classify normal/anomalous; can detect via AI, neural networks, data mining, statistical methods
  - ☑ detects probes → early warnings · detects wide attack range ☒ legitimate-but-unmodeled behavior = false positive; single model across varying traffic can fail
- **Misuse Detection System**: defines abnormal behavior first, then normal; **predefined rules** (rule-based languages, state-transition analysis, expert systems)
  - ☑ more accurate, fewer false alarms ☒ **can't detect new attacks** (predefined rules)

## Behavior-based IDS (reaction)
- Model of normal/valid behavior extracted from reference info; compare with current activity → alarm on deviation
- **Active IDS**: automatically **blocks suspected attacks** without admin intervention; real-time corrective action (action depends on severity/type)
- **Passive IDS**: only monitors/analyzes + alerts; no protective/corrective function; logs intrusion, admin responds manually

## Protection-based IDS
- **NIDS**: observes traffic of segments/devices → recognizes suspicious activity in network + application protocols; placed at **network boundaries**, behind perimeter firewalls, routers, VPNs, remote access servers, wireless networks
- **HIDS**: installed on a specific host; monitors traffic, logs, process, applications, file access/modification; used for sensitive info on **publicly accessible servers**
- **Hybrid IDS**: combines HIDS + NIDS; agent on almost every host; works with **encrypted networks online**, data stored on a single host; combines NIDS low false-positive rate + HIDS anomaly detection for unknown attacks

## Structure-based IDS
- **Centralized IDS**: all data shipped to a central location for analysis (independent of monitored-host count); centralized coordinator analyzes after intrusion; **harmful in high-speed networks** because of fixed-location analysis load
- **Distributed IDS (dIDS)**: multiple IDSs over a large network communicating with each other or a central server → advanced monitoring, incident analysis, instant attack data; broader network view; centralizes attack records to spot trends/threats across segments; two management styles: centralized control / fully distributed (agent-based)

## Analysis Timing-based IDS
- Analysis timing = elapsed time between event occurrence and analysis
- **Interval-based (offline)**: stores intrusion info for later analysis; checks log files at predefined intervals; non-continuous flow ("store and forward"); **cannot perform active response**; batch mode in early IDS (no real-time capability)
- **Real-time-based**: **on-the-fly processing** — most common for NIDS; continuous information feed; results fast enough to affect the detected attack; online verification + simultaneous response; needs **more RAM + large hard drive** (traces all packets online)

## Source Data-based IDS
- **Audit trails**: documentary evidence of system/app/user activity; helps detect performance problems, security violations, app flaws; avoid single-file storage (intruder tampering)
  - Audit systems: watch file access · monitor system calls · record user commands · record security events · search events · run summary reports
  - Reasons: identify attack signs (event analysis) · recurring intrusions · system vulnerabilities · develop access/user signatures · define anomaly-detection traffic rules · basic defense
- **Network packets**: header (source/dest address, control info) + payload (body/user data); both can carry malicious content — **capture before final destination** = efficient detection

## Cards
Q:: IDS classification bases?
A:: Approach, protected system, structure, data source, behavior (after attack), analysis timing.
#flashcard
Q:: Signature vs anomaly detection tradeoff?
A:: Signature: few false alarms but known attacks only; anomaly: finds unknown attacks but high false-positive rate.
#flashcard
Q:: Active vs passive IDS?
A:: Active auto-blocks without admin; passive only monitors/analyzes/alerts and logs.
#flashcard
Q:: NIDS vs HIDS placement?
A:: NIDS: network boundaries behind FW/routers/VPN/wireless; HIDS: on the host (sensitive public servers).
#flashcard
Q:: Interval-based vs real-time IDS?
A:: Interval: offline "store and forward", no active response; real-time: on-the-fly, continuous feed, more RAM+disk.
#flashcard
Q:: IDS data sources?
A:: Audit trails (system/app/user evidence) and network packets (header+payload captured pre-destination).
#flashcard