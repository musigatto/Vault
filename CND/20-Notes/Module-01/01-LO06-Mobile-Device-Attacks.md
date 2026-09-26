---
type: note
module: "01"
lo: "06"
tags: [threat, mod/01]
topic: "Mobile Device-specific Attack Techniques"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-01]]

# Mobile Device Attacks (§1.6)

## Rooting (Android)
- Attains privileged control ("root access") within Android subsystem
- Exploits firmware security vulnerabilities; copies `su` binary to PATH location (e.g. `/system/xbin/su`) and grants executable permissions via `chmod`
- Tools: **KingoRoot**, **TunesGo**
- Capabilities: modify/delete system files, ROMs, kernels · remove bloatware · low-level hardware access · higher performance · Wi-Fi/Bluetooth tethering · install apps on SD card
- Risks: void warranty · poor performance · malware infection · bricking

## Jailbreaking (iOS)
- Installs modified kernel patches to run apps not signed by the OS vendor; bypasses manufacturer limits; sideloading
- Provides root access → third-party apps, themes, extensions; removes sandbox restrictions → malicious apps access restricted resources
- Tools: **Cydia · Hexxa Plus · Apricotios · Yuxigon · Sileo · Trimgo**
- Risks (same as rooting): void warranty · poor performance · malware infection · bricking

## Malicious Apps in App Stores
- App stores (official: Apple App Store, Google Play, Microsoft store · third-party: **Amazon, GetJar, APKMirror**) targeted for malware distribution
- Repackaging: legitimate app + malware → third-party store; exfiltrates call logs, photos, videos, sensitive docs
- Insufficient/no vetting lets fake apps in; social engineering pushes downloads outside official stores

## Mobile Spamming
- Unsolicited SMS/MMS/IM/email in bulk (text spam, m-spam)
- Vector: premium-rate phone bait · malicious links · phishing lures
- Consequences: wasted bandwidth · financial loss · malware injection · corporate data breach

## SMiShing (SMS Phishing)
- SMS/IM with a deceptive link to acquire personal/financial info (SSNs, credit cards, banking creds); also pushes malware
- Attacker buys a **prepaid SMS card** with fake identity → sends bait (lottery, gift voucher, account suspension)
- Effective because: most users access Internet via mobile · easy campaign setup · hard to detect/stop · users not accustomed to text spam · no mainstream SMS spam filtering · mobile AV often skips SMS

## Bluebugging
- Remote access to Bluetooth-enabled device; uses features w/o victim's knowledge; creates a backdoor
- Enables: sniff corporate/personal data · receive/intercept/forward calls & messages · connect to Internet · access contacts, photos, videos
- Related: **Bluesnarfing** = stealing information via Bluetooth (vs Bluebugging = gaining control); risks rise on open/unencrypted connections (public Wi-Fi)

## Mnemonic
> [!tip] Mnemonic
> Android=`su`+`chmod` (root) · iOS=kernel patches (jailbreak). Bluebugging = control. Bluesnarfing = steal.

## Cards
Q:: Difference between bluesnarfing and bluebugging?
A:: Bluesnarfing steals information via Bluetooth; bluebugging gains control over the device via Bluetooth.
#flashcard

Q:: How is Android rooting implemented?
A:: Exploiting firmware vulnerabilities and copying the su binary to a PATH location (e.g. /system/xbin/su) with executable permissions via chmod.
#flashcard