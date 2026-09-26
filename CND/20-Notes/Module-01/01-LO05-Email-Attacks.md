---
type: note
module: "01"
lo: "05"
tags: [threat, mod/01]
topic: "Email Attack Techniques"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-01]]

# Email Attacks (§1.5)

## Malicious Email Attachments
- Attachments may deliver viruses, worms, trojans, rootkits, spyware when opened
- Exploit user trust: "account blocked, please run the attached file"
- May halt system-critical programs

## Malicious User Redirection
- Links in email redirect victim to malware-hosting sites
- Redirect categories:
  - **Referrer based**: attack depends on the referring page
  - **User agent based**: gathers device info (name, version, OS) to plan attacks
  - **Cookie based**: exploits stored name/value cookie pairs
  - **OS based**: depends on victim's OS/config
- Indicators: malware warning screen/popup · blank page · redirected to another domain · site unreachable from Google search · bounced back to Google
- Mitigation: be cautious with links; full system scan if suspicious; recognize "one-time offer"/"call to action" social lures

## Phishing
- Email asking for personal/financial info with a link similar to a genuine website; submitted data goes to attacker's database
- Appears to come from valid orgs (banks, partners); may contain hyperlinks that breach company security

## Spamming
- Unsolicited commercial advertisements; email is most common, also online message boards & chat rooms
- Wastes time + bandwidth; exists because people respond
- Harm: pollutes Internet · fake/unreliable content · illegal content · destroys company reputation · legal risk (company name abuse) · productivity loss

## Email Bombs (DoS)
- Overload an inbox/server with countless emails; fills disk space or blocks legit mail; affects all server users; degrades network performance
- Achieved by: activating a botnet · streaming emails with huge zip attachments (server unzips to check → strain)
- Types: **list linking** (subscribe victim to many mailing lists) · **attachment** (many large attachments) · **mass mailing** (all-addresses send) · **reply all** (reply-all to long list) · **zip bomb** (compressed archive that consumes resources on decompression)

## Cards
Q:: Types of malicious email redirects?
A:: Referrer-based, user-agent-based, cookie-based, and OS-based.
#flashcard

Q:: Email bomb types?
A:: List linking, attachment, mass mailing, reply all, zip bomb.
#flashcard