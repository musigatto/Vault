---
type: note
module: "02"
lo: "04"
tags: [process, mod/02]
topic: "Security Awareness Training"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-02]]

# Security Awareness Training (§2.4)

## Employee awareness & training
- Employees are a primary asset **and part of the attack surface** — untrained workers risk the org
- Provide **formal security awareness training on join + periodically thereafter**
- Training goals — employees: know how to defend self + org against threats · follow security policies/procedures for IT · know whom to contact on discovering a threat · **identify data nature by data classification** · protect physical/informational assets (secrets, privacy, classified info) · handle critical info (review **NDAs**) · protect critical info (password policy + **two-factor authentication**) · know consequences of failing to secure info (employment loss)
- Training also meets **regulatory requirements** for certain frameworks

## Training methods
- Classroom style · online training · round-table discussions · security awareness website · providing hints · making short films · conducting seminars
- Extended: simulation training · hands-on · lectures · coaching/mentoring · case studies · management-specific activities · group discussions

## Security policy training
- Teaches how to perform duties + comply with the policy
- Train new employees **before granting network access** (or limited access until training completes)
- Advantages: effective policy implementation · policies followed, not just enforced · awareness of compliance issues · enhanced network security

## Physical security training
- Educate: methods to reduce attacks · examine devices + data-attack chances · risks of carrying sensitive information · importance of security personnel · whom to report suspicious activity · what to do when systems/workplaces left unattended · disposal procedures for critical paper documents & storage media
- Minimize breaches · identify hardware-theft-prone elements · assess risks of handling sensitive data · ensure workplace physical security

## Social engineering training
| Area | Attack technique | Train on |
|---|---|---|
| Phone | Impersonation | Provide no confidential info |
| Dumpsters | Dumpster diving | Don't throw sensitive docs in trash; **shred**; **erase magnetic data** |
| Email | Phishing, malicious attachment | Differentiate legitimate vs targeted phishing email; don't download malicious attachments |

- Techniques to be aware of: physical SE (**tailgating, piggy-backing**) · **password change** (attacker as authority) · **name-drop** (higher authority's name) · **relaxing conversation** (build rapport) · **new hire** ruse (tour the office)

## Data classification training
- Security labels mark security level of info assets; manage access clearance
- Classification levels: **Top Secret → Secret → Confidential → Restricted → Official → Unclassified**
  - **Unclassified** — no access permissions; anyone at any level
  - **Restricted** — only a few people
  - **Confidential** — exposure → financial/legal issues
  - **Secret** — access secret + confidential + restricted + unclassified (NOT top secret)
  - **Top Secret** — access everything (top secret, secret, confidential, restricted, unclassified)

## Steps to implement security awareness training
1. **Get buy-in from the top** — explain benefits, tailored & pitched to org goals/values
2. **Gap analysis** — identify frequent attack locations & why employees fall for phishing · ideal future state (savings if nobody falls victim) · current state (breach causes, adequacy of training) · compare → measure victims · plan to bridge gaps
3. **Schedule regular & consistent training** — frequency matters as attacks increase
4. **Review training performance regularly** — short tests, key metrics, real-time training to close gaps
5. **Simulate phishing attacks** — periodic simulations teach mechanics of threats
6. **Educate employees who fail phishing simulations** — frequent exercises, extra resources, rewards for reporting, gamification, consequence stories
7. **Implement policy processes** — clear policy documentation using existing templates (email, password policies); edit to fit org needs

## Cards
Q:: Training cadence for employees?
A:: On joining and periodically thereafter.
#flashcard

Q:: Two data classification top-level rules?
A:: Secret users access secret→unclassified (NOT Top Secret); Top Secret users access all levels; unclassified = anyone, no permissions.
#flashcard

Q:: Social engineering techniques to train against?
A:: Tailgating/piggy-backing · password-change ruse · name-dropping · relaxing conversation · new-hire ruse.
#flashcard

Q:: Steps to implement awareness training?
A:: Buy-in from top → gap analysis → regular schedule → performance review → phishing simulations → educate failures → implement policy processes.
#flashcard