# Threat Research

Working notes mapping attacker behaviour to MITRE ATT&CK, with detection logic developed and tested in a home SOC lab.

## Method

Each technique gets its own file: what the technique does, where it surfaces in telemetry, a detection approach, and how to validate that detection actually fires. Framework data comes from MITRE ATT&CK, which is openly published. Vendor incident-response reports are cited as the source that informed *which* techniques to prioritise — their analysis stays in their documents and is not reproduced here.

## Technique index

Prioritisation below follows Unit 42's 2023 ATT&CK recommendations report, which ranks capabilities by how often they appeared in real incident-response engagements. Working top-down through this list means studying what actually shows up rather than what is merely possible.

### Initial Access (TA0001)

| ID | Technique |
|---|---|
| T1078 | Valid Accounts |
| T1110 | Brute Force (.001 Password Guessing, .003 Password Spraying, .004 Credential Stuffing) |
| T1210 | Exploitation of Remote Services |
| T1566 | Phishing (.001 Spearphishing Attachment) |
| T1608.006 | Stage Capabilities: SEO Poisoning |

### Discovery (TA0007)

| ID | Technique |
|---|---|
| T1018 | Remote System Discovery |
| T1033 | System Owner/User Discovery |
| T1046 | Network Service Discovery |
| T1069 | Permission Groups Discovery (.001 Local, .002 Domain) |
| T1087 | Account Discovery (.001 Local, .002 Domain) |
| T1135 | Network Share Discovery |
| T1482 | Domain Trust Discovery |

### Persistence (TA0003)

| ID | Technique |
|---|---|
| T1053.005 | Scheduled Task |
| T1098 | Account Manipulation |
| T1136 | Create Account (.001 Local, .002 Domain) |
| T1505.003 | Server Software Component: Web Shell |
| T1543.003 | Create or Modify System Process: Windows Service |
| T1547.001 | Registry Run Keys / Startup Folder |

### Defense Evasion (TA0005)

| ID | Technique |
|---|---|
| T1027 | Obfuscated Files or Information |
| T1055 | Process Injection |
| T1140 | Deobfuscate/Decode Files or Information |
| T1218.011 | System Binary Proxy Execution: Rundll32 |
| T1562 | Impair Defenses (.001 Disable Tools, .004 Disable/Modify Firewall, .010 Downgrade Attack) |
| T1620 | Reflective Code Loading |

### Credential Access (TA0006)

| ID | Technique |
|---|---|
| T1003.001 | OS Credential Dumping: LSASS Memory |

### Lateral Movement (TA0008)

| ID | Technique |
|---|---|
| T1021.001 | Remote Services: Remote Desktop Protocol |

### Command & Control (TA0011)

| ID | Technique |
|---|---|
| T1001 | Data Obfuscation |
| T1090 | Proxy |
| T1219 | Remote Access Software |
| T1572 | Protocol Tunneling |

### Exfiltration (TA0010)

| ID | Technique |
|---|---|
| T1537 | Transfer Data to Cloud Account |
| T1567.002 | Exfiltration to Cloud Storage |

### Impact (TA0040)

| ID | Technique |
|---|---|
| T1486 | Data Encrypted for Impact |
| T1490 | Inhibit System Recovery |

## Progress

Techniques with a written file are linked above as they are completed. Untracked entries are still on the list.

## Sources

MITRE ATT&CK — https://attack.mitre.org

Unit 42, *Recommendations to Mitigate Specific Attacker Capabilities Based Upon MITRE ATT&CK*, Palo Alto Networks, March 2023 — used to prioritise which techniques to study first.
