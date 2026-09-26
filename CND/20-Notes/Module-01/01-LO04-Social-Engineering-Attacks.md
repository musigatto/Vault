---
type: note
module: "01"
lo: "04"
tags: [threat, mod/01]
topic: "Social Engineering Attack Techniques"
exam_weight: unknown
status: done
unresolved:
  - "'Reverse social engineering' is named in the LO but no definition is present in the extracted text."
---
[[MOC-Module-01]]

# Social Engineering Attacks (§1.4)

## Definition
- Art of convincing/influencing people to reveal confidential information to perform malicious action; targets basic human weaknesses; bypasses even strong policies

## Pre-attack information gathering
- Official websites (employee IDs, names, email addresses)
- Job ads (specific skills → infra hints: Oracle DB, UNIX servers)
- Blogs, forums (personal + organizational info)

## Techniques
| Technique | Description |
|---|---|
| Impersonation | Pretend to be legitimate/authorized person (in person / phone / email): legitimate end user · important user/VIP · technical support (request IDs & passwords) |
| Eavesdropping | Unauthorized listening/reading of conversations or messages (phone lines, email, IM) |
| Shoulder Surfing | Direct observation (passwords, PINs, account numbers); at distance via binoculars |
| Dumpster Diving | Searching trash for phone bills, contact/financial/operations info |
| Piggybacking | Authorized person allows (intentionally or unintentionally) an unauthorized person through a secure door |
| Tailgating | Unauthorized person w/ fake ID badge follows closely behind an authorized person through key-access door |
| Reverse Social Engineering | Named in LO; definition not in extracted text (→ unresolved) |

## Classification
- **Human-based**: physical presence of intruder required to extract personal info
- **Computer-based**: intruder extracts credentials remotely through other systems

## Notes
- Who goes on vacation, where employees work, and security measures in place are the kind of info SE harvests
- Employees must be trained to recognize and counter these tricks

## Cards
Q:: Piggybacking vs tailgating?
A:: Piggybacking: an authorized person lets an unauthorized person pass a secure door. Tailgating: unauthorized person with fake badge follows an authorized person through a key-access door.
#flashcard

Q:: Two classes of social engineering attacks?
A:: Human-based (physical presence needed) and computer-based (remote credential extraction).
#flashcard