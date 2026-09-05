# Domain 4 — Security Operations (28%)

The biggest domain, and the one that maps most directly to Tier 1 SOC work. Weight your study here.

## Incident Response — know this cold

**Preparation → Detection → Analysis → Containment → Eradication → Recovery → Lessons Learned**

- **Preparation** — plans, tooling, training *before* anything happens
- **Detection** — something fires
- **Analysis** — is it real? how bad? (Tier 1 lives here)
- **Containment** — stop the spread, don't fix yet
- **Eradication** — remove the cause
- **Recovery** — restore to normal, verify
- **Lessons Learned** — the step everyone skips

Exam trap: **containment comes before eradication.** Isolate the host first; cleaning it up comes after. If an answer choice says "reimage immediately," check whether containment happened.

Supporting: tabletop exercises, simulation, root cause analysis, **threat hunting** (proactive, no alert required).

## Digital Forensics

Legal hold, **chain of custody**, acquisition, preservation, reporting, e-discovery.

**Order of volatility** — collect fastest-to-disappear first:

CPU cache/registers → **RAM** → swap/page file → disk → remote logs → archived media

Hook: **the more volatile, the sooner you grab it.** Pulling the plug destroys RAM evidence.

## Log Sources

Firewall, application, endpoint, OS security logs, IDS/IPS, network, metadata. Plus packet captures, vulnerability scans, dashboards, automated reports.

Knowing *which log answers which question* is the actual Tier 1 skill: "did they get in?" is auth logs; "what did they talk to?" is network/firewall; "what ran?" is endpoint.

## Monitoring & Alerting

Activities: log aggregation, alerting, scanning, reporting, archiving, alert response and remediation, validation, **quarantine**.

Tools: **SIEM**, SCAP, benchmarks, agent vs agentless, antivirus, **DLP**, SNMP traps, **NetFlow**, vulnerability scanners.

Controls: firewall, IDS/IPS, web filter, DNS filter, **EDR/XDR**, user behavior analytics.
Email security: **SPF** (who may send), **DKIM** (signature proving it wasn't altered), **DMARC** (what to do when SPF/DKIM fail).

Hook: **SPF = allowed sender, DKIM = signed, DMARC = the policy tying them together.**

## Vulnerability Management

1. **Identification** — scanning, threat feeds (OSINT, proprietary, dark web), pen testing, bug bounty, audits
2. **Analysis** — confirm it (false positive vs false negative), **CVSS** score, **CVE** identifier, exposure factor, environmental variables, prioritize
3. **Response** — patch, segment, compensating control, insurance, documented exception
4. **Validation** — rescan, audit, verify
5. **Reporting**

**False positive** = alert fired, nothing there. **False negative** = nothing fired, something *was* there. The second is the dangerous one.

## Hardening & Baselines

Establish → deploy → **maintain** (drift is the enemy).

Targets: workstations, servers, switches, routers, mobile, cloud infra, IoT, ICS/SCADA, embedded, RTOS.
Techniques: disable unused ports and protocols, change default passwords, remove unnecessary software, host firewall, EDR, encryption.

Wireless: site survey, heat map, **WPA3**, RADIUS/AAA.
Mobile deployment: **BYOD** (theirs), **COPE** (company owned, personally enabled), **CYOD** (choose from a list), managed via **MDM**.

## Identity & Access Management

Provisioning/deprovisioning, identity proofing, federation, **SSO** (LDAP, OAuth, SAML), attestation.

**Access control models:**
- **DAC** — owner decides
- **MAC** — system enforces via labels, owner can't override
- **RBAC** — permissions attach to a role/job
- **ABAC** — attributes and context decide
- **Rule-based** — conditions the admin set

**MFA factors:** something you **know** / **have** / **are**, plus somewhere you **are** and something you **do**. Two of the *same* type isn't MFA — password + PIN is still one factor.

Passwords: length beats complexity; also reuse, expiration, age, managers, passwordless.
And always: **least privilege**.

## Automation & Orchestration

Use cases: user/resource provisioning, guard rails, ticket creation, escalation, enabling/disabling services, CI/testing, API integration.
Benefits: efficiency, baseline enforcement, scale, faster reaction time, workforce multiplier.
Costs: complexity, single point of failure, technical debt, ongoing supportability.

## Self-check

- Order the IR phases. Which two get swapped most often in wrong answers?
- A host is actively beaconing to C2. What's your first action — reimage, isolate, or collect memory?
- Rank for collection: disk image, RAM, archived backups, CPU cache.
- An alert fires on benign activity. False positive or false negative? Which of the two would you rather have?
- Password + security question — how many factors is that?
- Which email control tells a receiving server what to do when a message fails authentication?
- Which access control model prevents even the data owner from changing permissions?

---

*Structured around CompTIA's published SY0-701 exam objectives. Explanations written from scratch, not reproduced from any course or textbook.*
