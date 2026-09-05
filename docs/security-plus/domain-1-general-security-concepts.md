# Domain 1 — General Security Concepts (12%)

## CIA Triad

| Leg | Means | Broken by | Protected by |
|---|---|---|---|
| **Confidentiality** | Only authorized eyes | Disclosure, leak, exfiltration | Encryption, access control |
| **Integrity** | Data unaltered | Tampering, corruption | Hashing, digital signatures |
| **Availability** | Reachable when needed | DoS, outage, ransomware | Redundancy, backups |

Hook: **who can see it / has it changed / can I get it.**

**Non-repudiation** — you can't deny you did it. Provided by digital signatures.

## AAA

- **Authentication** — who are you? (password, token, biometric)
- **Authorization** — what are you allowed to do? (permissions)
- **Accounting** — what did you actually do? (logs, audit trail)

Hook: **Who → What can you → What did you.**

Systems authenticate too, not just people — certificates and 802.1X.

## Control Categories — *who implements it*

- **Technical** — the system enforces it (firewall, MFA, encryption)
- **Managerial** — paperwork and planning (risk assessment, policy)
- **Operational** — people doing things (awareness training, guards)
- **Physical** — you can touch it (lock, fence, badge reader)

Hook: **machine / paperwork / people / touchable.**

## Control Types — *what it does*

- **Preventive** — stops it happening (lock, firewall rule)
- **Deterrent** — discourages the attempt (warning sign, visible camera)
- **Detective** — spots it during or after (IDS, log review)
- **Corrective** — fixes it after (restore from backup, patch)
- **Compensating** — the stand-in when the real control won't fit (extra monitoring where MFA can't deploy)
- **Directive** — tells people what to do (policy, procedure)

Exam trap: a sign that *warns* is deterrent; a lock that *stops* is preventive. Same camera can be deterrent (visible) or detective (recording to SIEM) depending on how the question frames it.

## Zero Trust

Core idea: **never trust, always verify.** Network location grants no implicit trust.

- **Control Plane** — makes the decision. Policy Engine decides, Policy Administrator issues the verdict.
- **Data Plane** — carries it out. The **Policy Enforcement Point (PEP)** sits in the traffic path.

Hook: **control plane decides, data plane does.**

Supporting ideas: adaptive identity, threat scope reduction (shrink the blast radius), policy-driven access control.

## Cryptography Fundamentals

**Symmetric** — one shared key. Fast. Problem is getting the key to the other side. (AES)
**Asymmetric** — public/private pair. Slow. Solves key distribution. (RSA, ECC)

Real systems use both: asymmetric to agree on a symmetric key, then symmetric for the bulk data.

**Hashing** — one-way, fixed length, proves integrity (SHA-256). Not encryption: no key, nothing to reverse.
**Salt** — random value added before hashing. Specifically defeats rainbow tables (precomputed hash lookups).

**Digital signature** — hash the message, encrypt the hash with **your private key**. Gives origin + integrity + non-repudiation in one move.

Hook: **encrypt with their public key = secrecy. Sign with my private key = proof it's me.**

- **PKI** — a CA issues certificates binding an identity to a public key; trust flows down the chain. Revocation via CRL or OCSP.
- **Diffie-Hellman** — lets two parties agree on a key across an open channel without ever sending it.
- **Perfect Forward Secrecy** — fresh session key every time, so a leaked long-term key doesn't expose past traffic.

## Change Management

In a security exam because unmanaged change is how a hardened system quietly drifts insecure.

Process: approval, ownership, stakeholder identification, impact analysis, test results, **backout plan**, maintenance window.
Technical side: allow/deny lists, restricted activities, downtime, service restarts, dependencies, documentation, version control.

## Self-check

- Ransomware encrypts a file server. Which leg of the CIA triad breaks first — and which one breaks if the attacker also copied the data out?
- A visible camera is which control type? The same camera feeding a SIEM is which?
- You sign a message with which key? You encrypt *to* someone with which key?
- In Zero Trust, which plane holds the Policy Enforcement Point?
- What exactly does a salt defeat — brute force, or something more specific?
- Which change-management artifact tells you how to undo a failed change?

---

*Structured around CompTIA's published SY0-701 exam objectives. Explanations written from scratch, not reproduced from any course or textbook.*
