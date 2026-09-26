---
type: note
module: "01"
lo: "03"
tags: [threat, mod/01]
topic: "Application-level Attack Techniques"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-01]]

# Application-level Attacks (§1.3)

## SQL Injection
- Series of malicious SQL queries manipulating the database; works when app doesn't validate input before building SQL
- Classic bypass: `SELECT * FROM tablename WHERE UserID = 2302 OR 1=1`
- Entry points: address bar, form fields, queries, searches
- Enables: login w/o valid credentials · unauthorized data queries · modify/drop DB · pivot via trust relationships

## Cross-site Scripting (XSS)
- Injects client-side script (JavaScript, VBScript, ActiveX, HTML, Flash) into dynamic web pages viewed by other users; server can't control dynamic page rendering
- Untrusted input sources: URL parameters, form elements, cookies, DB queries
- Exploitations: script execution · redirect to malicious server · exploit user privileges · ads in hidden IFRAMEs/pop-ups · data manipulation · session hijacking · brute-force pw cracking · data theft · intranet probing · keylogging
- Variants in module: attack via email (bank.com `clientprofile` example) · stealing users' cookies · sending unauthorized requests · stored XSS via blog/comment field

## Parameter Tampering
- Manipulation of params exchanged client↔server (price, quantity, permissions, credentials stored in cookies, query strings, hidden fields)
- Types: **query string tampering** (Burp Suite scans POST params) · **HTTP header tampering** (referer-based access decisions) · **cookie parameter tampering**
- Exploits integrity/logic validation → may yield XSS, SQLi

## Directory Traversal
- Aka path traversal / forceful browsing; forces app to access unintended files via `../` (dot-dot-slash) sequences
- Example: `http://www.example.com/process.aspx=../../../../some dir/some file`
- Exposes app structure, source code, password files, client data; as a first step for privilege escalation

## CSRF
- Forces unsuspecting user's browser to send malicious requests; needs **user + trusted website + malicious website**
- Malicious site injects HTTP request into victim's active session (session cookie) → state-changing actions (fund transfers, email changes); admin victims affect whole app
- Exploits app's trust in already-validated end-user

## Application-level DoS
- Resource-intensive requests exhausting CPU, memory, sockets, disk/database bandwidth, worker processes
- Why vulnerable: environment bottlenecks · implementation flaws · poor data validation
- Examples: **user registration DoS** (spurious users) · **user enumeration** (error msg reveals which of user/password is wrong) · **login attacks** (overload auth) · **account lockout attacks** (valid user + wrong passwords → lockout)
- Emulates legitimate request syntax → undetectable by existing DoS protections

## Session Hijacking
- Attacker seizes a valid TCP communication session; source of attack = **session cookie** (also called cookie hijacking / side-jacking)
- Activities: transfer funds · pose as buyer · identity theft · steal client data · encrypt info & demand ransom · SSO access to multiple apps
- Methods:
  - **Session side jacking**: packet sniffing of session cookies after auth; possible if site lacks SSL/TLS for the **entire** session
  - **Session fixation**: impersonate user, obtain cookie via malicious links
  - **Cookie theft** by malware or direct access to browser temp storage
  - Client-side script injection — if server does **not** set **HttpOnly** on session cookies
  - Short/guessable session IDs

## OWASP Top 10 (2021)
1. Broken Access Control (least privilege / deny-by-default violations)
2. Cryptographic Failures (MD5, SHA1, PKCS#1 v1.5, default keys)
3. Injection (SQL, NoSQL, OS command, ORM, LDAP, EL/OGNL)
4. Insecure Design (missing/ineffective control design)
5. Security Misconfiguration (default accounts, unnecessary features)
6. Vulnerable and Outdated Components
7. Identification and Authentication Failures (weak/default passwords, session ID in URL)
8. Software and Data Integrity Failures (untrusted CDNs/plugins, CI/CD, insecure deserialization)
9. Security Logging and Monitoring Failures
10. Server-Side Request Forgery (SSRF) — fetch of user-supplied URL to unintended destination

## Cards
Q:: XSS definition?
A:: Injection of client-side script into dynamic web pages viewed by other users, that executes in the victim's browser.
#flashcard

Q:: Requirement for a CSRF attack?
A:: Three things: a user, a trusted website, and a malicious website.
#flashcard

Q:: Which cookie attribute prevents XSS-based session hijacking?
A:: HttpOnly — if the server does not set HttpOnly on session cookies, client-side script injection can enable session hijacking.
#flashcard