# Domain 3 — Security Architecture (18%)

## Architecture Models

Cloud (with a **shared responsibility matrix** — know where the provider's job ends), hybrid, IaC, serverless, microservices, on-prem, centralized vs decentralized, virtualization, IoT, **ICS/SCADA**, RTOS, embedded.

Trade-offs the exam asks about: availability, resilience, cost, responsiveness, scalability, ease of deployment, ease of recovery, **patch availability**, power, compute.

ICS/SCADA and embedded systems keep appearing because they're hard to patch and often can't be taken offline — that's the answer to most questions about them.

## Secure Infrastructure

- **Device placement** and security zones — where a control sits determines what it can see
- **Attack surface** — reduce it, don't just defend it
- **Failure modes**: **fail-open** (traffic keeps flowing, availability wins) vs **fail-closed** (traffic stops, security wins)
- **Active vs passive**, **inline vs tap/monitor** — inline can block, a tap can only watch

Appliances: jump server, proxy, IDS/IPS, load balancer, sensors.
Port security: **802.1X**, EAP.
Firewalls: **WAF** (web app layer), UTM (all-in-one), **NGFW** (application-aware), Layer 4 vs Layer 7.

Hook: **Layer 4 sees ports, Layer 7 sees what the traffic actually is.**

## Secure Communication

VPN, remote access, tunneling (**TLS**, **IPSec**), SD-WAN, **SASE**.

## Data Protection

**Classifications**: public, private, sensitive, confidential, restricted, critical.
**Types**: regulated, trade secret, intellectual property, legal, financial, human- vs non-human-readable.

**Three states** — at rest, in transit, in use. *In use* is the hard one, because data has to be decrypted to be processed.

Methods: encryption, hashing, **masking** (partial hide, e.g. last-4 of a card), **tokenization** (swap for a meaningless token, real value stored elsewhere), obfuscation, segmentation, geographic restriction, permission restrictions.

Masking vs tokenization is a favorite distractor: masking hides characters, tokenization substitutes the whole value.

Also: **data sovereignty** — the law that applies is the law where the data physically sits.

## Resilience & Recovery

- **HA**, load balancing vs clustering
- **Site types**: **hot** = running now, **warm** = some setup needed, **cold** = an empty room
- Geographic dispersion, platform diversity, multi-cloud, continuity of operations
- **Testing**: tabletop (talk it through), simulation, failover, parallel processing
- **Backups**: onsite/offsite, frequency, encryption, snapshots, replication, journaling
- **Power**: UPS covers the gap, generator covers the outage

## Self-check

- A firewall loses power. Which failure mode keeps the business running, and which keeps it safe?
- You need to watch traffic without any risk of dropping it — inline or tap?
- Card number shown as `**** **** **** 4471` — masking or tokenization?
- Which data state can't be protected by encryption alone, and why?
- Your RTO is 4 hours and budget is tight. Hot, warm, or cold site?
- Which resilience test involves no actual systems being touched?

---

*Structured around CompTIA's published SY0-701 exam objectives. Explanations written from scratch, not reproduced from any course or textbook.*
