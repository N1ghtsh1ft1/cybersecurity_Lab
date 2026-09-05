# Domain 5 — Security Program Management & Oversight (20%)

Mostly non-technical, and easy to under-study because of that. It's a fifth of the exam.

## Governance

- **Policies** — high level intent (AUP, incident response, business continuity, disaster recovery, SDLC, change management)
- **Standards** — the specific requirement (password, encryption, access control, physical)
- **Procedures** — the step-by-step (onboarding/offboarding, playbooks, change management)
- **Guidelines** — recommended, not mandatory

Hook: **policy says why, standard says what, procedure says how, guideline just suggests.**

External drivers: regulatory, legal, industry, and local/regional/national/global requirements.
Structures: boards, committees, government entities; centralized vs decentralized.

**Data roles:**
- **Owner** — accountable for the data
- **Controller** — decides why and how it's processed
- **Processor** — processes it on the controller's behalf
- **Custodian/steward** — day-to-day handling and protection

## Risk Management

**The two formulas — memorize, they're calculable questions:**

- **SLE = AV × EF** (Single Loss Expectancy = Asset Value × Exposure Factor)
- **ALE = SLE × ARO** (Annualized Loss Expectancy = SLE × Annual Rate of Occurrence)

Worked example: a $50,000 asset, 20% destroyed per incident, twice a year →
SLE = 50,000 × 0.2 = **$10,000**. ALE = 10,000 × 2 = **$20,000/yr**.
If a control costs more than $20k/yr, accepting the risk is the rational answer.

**Risk responses — only four:**
- **Mitigate** — reduce it
- **Transfer** — insurance, or push it to a third party
- **Accept** — eat it (with exemption/exception documented)
- **Avoid** — stop doing the activity

Also: risk register, key risk indicators, risk owners, risk threshold, appetite (expansionary / neutral / conservative), assessment cadence (ad hoc, one-time, recurring, continuous), qualitative vs quantitative analysis.

**Business impact analysis metrics:**
- **RTO** — how long until we're back up
- **RPO** — how much data we can afford to lose
- **MTTR** — mean time to repair
- **MTBF** — mean time between failures

Hook: **RTO = time, RPO = data.** These two get swapped constantly.

## Third-Party Risk

Assessment: penetration testing, **right-to-audit clause**, evidence of internal audits, independent assessments, supply chain analysis.
Selection: due diligence, conflict of interest.

**Agreements:**
- **SLA** — performance guarantees
- **MOU / MOA** — intent to work together (MOA is more binding)
- **MSA** — master terms for ongoing work
- **SOW / WO** — the specific deliverables
- **NDA** — confidentiality
- **BPA** — business partners agreement

## Compliance

Non-compliance consequences: fines, sanctions, reputational damage, **loss of license**, contractual impacts.
Monitoring: due diligence and due care, attestation and acknowledgement, internal and external, automation.
Privacy: data subject, controller vs processor, ownership, data inventory, **retention**, right to be forgotten.

## Audits & Assessments

**Internal** — self-assessments, audit committee, internal compliance.
**External** — regulatory examinations, independent third-party audit.

**Penetration testing environments:**
- **Known** (full info given — was "white box")
- **Partially known** ("gray box")
- **Unknown** (no info — "black box")

Recon: **passive** (no contact with the target — OSINT, public records) vs **active** (scanning, touching the target).

## Security Awareness

Phishing campaigns and recognition, anomalous behavior recognition (risky / unexpected / unintentional), user guidance (handbooks, insider threat, password management, removable media, social engineering, operational security, hybrid work), reporting and monitoring (initial and recurring), plus development and execution of the program.

## Self-check

- A $200,000 asset, exposure factor 25%, occurring 0.5 times per year. What's the SLE? The ALE?
- You buy cyber insurance. Which of the four risk responses is that?
- Which BIA metric answers "how much data can we lose" — RTO or RPO?
- Nmap scan against a target: passive or active recon?
- Policy, standard, procedure, guideline — which one is optional?
- Which agreement type would contain uptime guarantees?
- A company processes data on behalf of another. Controller or processor?

---

*Structured around CompTIA's published SY0-701 exam objectives. Explanations written from scratch, not reproduced from any course or textbook.*
