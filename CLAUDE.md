# Standing rules for this repo

## Writing study notes
- Concise and memorizable over comprehensive. Recall hooks and mnemonics beat long explanations.
- Every note file ends with a short self-check section (a handful of questions or prompts to test recall).
- If a note is derived from someone else's reference material, credit the source at the bottom of the file.

## Organization
- Notes live under `docs/<topic>/`, one folder per topic.
- Each topic folder has its own `README.md` index listing its notes.
- Update the parent index whenever a note is added.
- Filenames: lowercase with hyphens (e.g. `port-scanning-basics.md`).

## Git
- Commit messages: imperative mood, one line subject (e.g. "Add notes on X", not "Added notes" or "Adding notes").
- Never force push to a shared branch.

## Handling sensitive data
- This repo is public. Never commit real IPs, hostnames, usernames, credentials, or VPN configs.
- Substitute RFC 1918 ranges (e.g. `10.0.0.0/8`, `192.168.0.0/16`) and generic hostnames (e.g. `target.local`, `host1`) for real ones.
- If a staged file looks like it holds a real environment detail, stop and ask before committing.
- If a credential is ever committed, rotate it. Removing the commit is secondary — the credential must be treated as compromised regardless of history rewrites.
