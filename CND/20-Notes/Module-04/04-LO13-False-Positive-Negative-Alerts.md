---
type: note
module: "04"
lo: "13"
tags: [concept, bestpractice, mod/04]
topic: "False Positive & False Negative IDS Alerts"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-04]]

# Dealing with False Positives / Negatives (§4.13)

## What is an alert
- **Graduated event** notifying a particular event (or series) reached a specified threshold; paging/ticketing systems signal "something wrong, requires immediate attention" — includes what, duration, when, where, which device, OS/version

## Four alert types
- **True positive** (attack → alert): alarm raised on an actual attack (also triggered during drills using hacker tools)
- **False positive** (no attack → alert): normal system activity treated as attack; desensitizes users, reduces reaction to real intrusions; used by admins to test IDS discrimination
- **False negative** (attack → no alert): IDS fails to react to actual attack — **most dangerous failure**
- **True negative** (no attack → no alert): acceptable behavior correctly ignored; IDS performing as expected

## Acceptable false-alarm level & rates
- An uncustomized IDS raises false alarms **90% of the time** depending on traffic + deployment; **fine-tune** to minimize
- When intrusions are low vs usage, false-alarm rate is high; effective IDS inspects **both inbound + outbound**; set threshold per network tolerance
- False alarms depend on two phases: (1) **detection phase** — enhance config/approach (data mining, data clustering reduce false alarms); (2) **alert processing phase** — study causes, use case scenarios, alert filtering/fuzzy processing/statistical aggregation to discard false alarms
- Threshold depends on **sensitivity** (legitimacy of alerts detected) and **specificity** (filters accuracy of detected alerts)
- **False positive rate** = FP / (FP + TN)
- **False negative rate** = FN / (FN + TP)

## False-positive causes
- **Reactionary-traffic false alarms**: non-malicious traffic event (e.g., packets not reaching destination due to device failure)
- **Network equipment**: device (e.g., **load balancer**) generates unknown/odd packets
- **Non-malicious software bugs**: poorly written software generates odd/unknown packets
- **IDS software bugs**: alarm raised for no reason
- Also classified: protocol violations, IDS software bugs

## Reducing false positives
- Understand device weaknesses; implement effective countermeasures
- **Differentiate alerts**: separate priority vs less-important alerts; verify against earlier alerts (e.g., signature alerting at regular intervals = important); keep alert logs; classify by attack behavior / suspicious behavior; set **thresholds** to reduce alerts of the same attack

## False-negative causes
- **More dangerous than false positives**; reduce FN without raising FP
- **Network design issues**: improper port spanning on switches, traffic imbalance, multiple entry points defeating NIDS, improper IDS config
- **Encrypted-traffic design flaws**: IDS can't match encrypted payloads to signatures → place IDS **behind a VPN termination with SSL**
- **Misleading/improperly written signatures**: vendors can't write signatures for unknown attacks; some tools can't determine legitimate signatures
- **Unpublicized attacks** · poor NIDS device management · NIDS design flaws · lack of inter-departmental communication

## Reducing false negatives
- Proper **network design** parallel to security policies
- **Placement of IDS behind the firewall** (raises alerts for port scans, automated scans, DoS); detect illegitimate signatures
- **Active network analysis + monitoring** (analysis tools/utilities); nullify FN-triggering rules
- **Include additional data** in security events (org assets, users, networks, device sources) via automated/manual processes

## Cards
Q:: Four IDS alert types?
A:: True positive, false positive (no attack-alert), false negative (attack-no alert — most dangerous), true negative.
#flashcard
Q:: False positive rate formula?
A:: FP / (FP + true negative).
#flashcard
Q:: False negative rate formula?
A:: FN / (FN + true positive).
#flashcard
Q:: Sensitivity vs specificity?
A:: Sensitivity = legitimacy of alerts detected; specificity = filters/accuracy of detected alerts (set IDS threshold).
#flashcard
Q:: Encrypted-traffic false-negative fix?
A:: Place IDS behind a VPN termination with SSL so it can inspect decrypted traffic.
#flashcard
Q:: False-positive sources?
A:: Reactionary traffic (device failure), network equipment (load balancer odd packets), non-malicious software bugs, IDS software bugs.
#flashcard