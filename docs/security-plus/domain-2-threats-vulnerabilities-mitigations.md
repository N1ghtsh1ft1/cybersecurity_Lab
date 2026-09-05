# Domain 2 — Threats, Vulnerabilities & Mitigations (22%)

## Threat Actors

| Actor | Resources | Motivation |
|---|---|---|
| Nation-state | Very high (APT) | Espionage, war, disruption |
| Organized crime | High | Financial |
| Insider threat | Access, not money | Revenge, financial, accidental |
| Hacktivist | Low–moderate | Philosophical, political |
| Unskilled attacker | Low | Notoriety, opportunism |
| Shadow IT | Internal, unsanctioned | Convenience, not malice |

Attributes that separate them on the exam: **internal vs external, funding, sophistication.**

## Threat Vectors

Message-based (email, SMS, IM), images, files, voice calls, removable media, vulnerable or unsupported software, unsecure networks, open service ports, default credentials, supply chain.

## Social Engineering

Phishing (email) → **vishing** (voice) → **smishing** (SMS). Then: pretexting, impersonation, business email compromise, watering hole, brand impersonation, typosquatting, misinformation.

Hook: **v = voice, sm = SMS.**

## Malware

- **Virus** — needs a host file and user action
- **Worm** — self-propagates across the network, no user needed
- **Trojan** — pretends to be something useful
- **Ransomware** — encrypts, demands payment
- **Rootkit** — hides itself, often kernel level
- **Logic bomb** — dormant until a trigger condition
- **Keylogger / spyware** — captures activity
- **Bloatware** — unwanted preinstalled software, an attack surface not a payload

Hook: **a virus needs a ride, a worm drives itself.**

## Vulnerability Types

- **Application** — buffer overflow, race condition (TOCTOU), memory injection
- **Web** — SQL injection, XSS
- **Hardware** — firmware flaws, end-of-life and legacy gear
- **Virtualization** — VM escape, resource reuse
- **Cloud** — misconfigured storage, over-permissive IAM
- **Supply chain** — vendor, MSP, or hardware provider compromise
- **Cryptographic** — weak ciphers, bad key handling
- **Misconfiguration** — the one that shows up most in real SOC work
- **Zero-day** — no patch exists yet

## Indicators of Malicious Activity

Account lockouts, concurrent sessions in two places, **impossible travel**, blocked content, resource consumption spikes, out-of-cycle logging, **missing logs** (someone cleaned up), published/documented breach.

Impossible travel and missing logs are the two most exam-favored indicators — know them cold.

## Mitigation Techniques

Segmentation, access control (ACLs and permissions), application allow lists, isolation, patching, encryption, monitoring, **least privilege**, configuration enforcement, decommissioning.

Hardening specifically: EDR, host-based firewall, HIPS, disable unused ports/protocols, change default passwords, remove unnecessary software.

## Self-check

- What single property separates a worm from a virus?
- A user logs in from Virginia and then from Singapore eleven minutes later. Name the indicator.
- Which vulnerability class covers a VM breaking out into the hypervisor?
- An allow list and a deny list — which one fails safer, and why?
- Your logs stop for a 40-minute window during an incident. What does that itself indicate?

---

*Structured around CompTIA's published SY0-701 exam objectives. Explanations written from scratch, not reproduced from any course or textbook.*
