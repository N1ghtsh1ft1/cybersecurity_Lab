# Setting up Claude Code for this repo

How this machine was set up to work on this repo with Claude Code, and how to resume work on a fresh machine.

## 1. Install Claude Code

Native install (not via npm):

```sh
curl -fsSL https://claude.ai/install.sh | sh
```

This installs the `claude` binary to `~/.local/bin/claude`. Confirm with:

```sh
which claude
claude --version
```

## 2. Add the install location to PATH

Add this line to your shell profile (`~/.zshrc` for zsh):

```sh
export PATH="$HOME/.local/bin:$PATH"
```

Reload the shell (`source ~/.zshrc`) or open a new terminal, then confirm `claude` resolves from `~/.local/bin`.

## 3. Trust the project folder

The first time you run `claude` inside a project directory, it shows a trust prompt for that folder. Accepting it records `hasTrustDialogAccepted: true` for that path in `~/.claude.json`. Trust is scoped per-folder — a fresh clone of this repo to a new path needs the prompt accepted again.

```sh
cd ~/path/to/cybersecurity_Lab
claude
# accept the trust prompt when shown
```

## 4. Generate an SSH key for GitHub

```sh
ssh-keygen -t ed25519 -C "<your-email>"
```

Accept the default path (`~/.ssh/id_ed25519`) and set a passphrase. This creates a private key (`id_ed25519`, keep this secret and never commit it) and a public key (`id_ed25519.pub`, safe to share).

## 5. Add the public key to GitHub

Copy the public key to the clipboard:

```sh
pbcopy < ~/.ssh/id_ed25519.pub
```

In GitHub: **Settings → SSH and GPG keys → New SSH key**, paste, save.

Test the connection:

```sh
ssh -T git@github.com
```

## 6. Switch the repo remote from HTTPS to SSH

If the repo was cloned over HTTPS, switch it so pushes use the SSH key instead of prompting for credentials:

```sh
git remote set-url origin git@github.com:<owner>/<repo>.git
git remote -v   # confirm it now shows the git@github.com form
```

## 7. Resuming work

```sh
cd ~/path/to/cybersecurity_Lab
claude
```

If it's a brand-new clone on a machine that already has the SSH key and PATH set up, the only extra step is accepting the trust prompt (step 3) for the new path.

## Self-check
- Where does the `claude` binary live, and how does the shell find it?
- Why is trust scoped per-folder rather than global?
- Which of the two SSH key files is safe to share, and which must never be committed?
- What command converts an HTTPS remote to SSH?

## Source
Steps recorded from this machine's own setup session; no external reference material used.
