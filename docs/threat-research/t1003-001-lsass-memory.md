# T1003.001 — OS Credential Dumping: LSASS Memory

**Tactic:** Credential Access (TA0006)

## What it does

The Local Security Authority Subsystem Service (lsass.exe) holds credential material in memory for users with active sessions — hashes, and in some configurations plaintext. An attacker who can read that process memory can harvest credentials without ever cracking a password, then reuse them for lateral movement.

This is the pivot point in most intrusions: it converts access to *one machine* into access to *accounts*, which is what actually spreads.

## Where it shows up in telemetry

**Process access events** — the highest-value signal. Something opening a handle to lsass.exe with read rights. On Windows, Sysmon Event ID 10 (ProcessAccess) captures this; granted access masks of 0x1010 or 0x1410 are the classic dumping patterns.

**Process creation** — Event ID 4688 or Sysmon 1. Look for known tooling (procdump, mimikatz) but also living-off-the-land approaches: rundll32.exe calling comsvcs.dll MiniDump, or Task Manager being used to right-click-dump.

**File writes** — a .dmp file appearing in a temp directory shortly after a process-access event on LSASS.

## Detection approach

Alert on any process opening a handle to lsass.exe where the granted access mask includes memory-read rights, then filter out the legitimate accessors in your own environment (EDR agents, some backup and monitoring tools). The filtering is the real work — the raw event fires constantly on a normal host.

A second, cheaper rule: flag rundll32.exe command lines containing comsvcs and MiniDump together. Low volume, high signal, catches the most common LOLBin route.

## Validating it

In an isolated lab VM only — never against a machine you do not own:

1. Confirm Sysmon is logging Event ID 10 and that LSASS access is in scope of the config.
2. Trigger a benign process-access event and confirm the rule fires.
3. Check what *else* fired. If the alert volume is unmanageable, the exclusion list needs work before this rule is useful.

The point of step 3 is that an undetectable-in-practice rule is the same as no rule. Tuning is the deliverable, not the signature.

## Why it matters for triage

An LSASS access alert is rarely the first event in an intrusion — it usually follows initial access and some discovery. When triaging one, the useful question is not "is this real?" in isolation but "what happened on this host in the twenty minutes before it?" Credential dumping mid-chain is a very different severity from a one-off on an admin workstation running a new EDR agent.

## Self-check

- Why is LSASS the target rather than the SAM database?
- Which Sysmon event ID captures a process opening a handle to another process?
- What makes the rundll32 comsvcs MiniDump rule cheaper to run than a general LSASS-access rule?
- You get an LSASS access alert. What do you look at before deciding severity?
- Why is the exclusion list the hard part of this detection rather than the signature?

## Sources

MITRE ATT&CK T1003.001 — https://attack.mitre.org/techniques/T1003/001/

Technique prioritised from Unit 42's 2023 ATT&CK recommendations report; analysis and detection notes above are my own.
