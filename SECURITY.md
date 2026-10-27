# Security

NexoLLM reads text through macOS Accessibility and types on your behalf, so security reports are taken
seriously and answered first.

## Reporting a vulnerability

Please don't open a public issue. Use GitHub's private reporting instead:
**Security → Report a vulnerability** on https://github.com/NexoLLM/NexoLLM/security/advisories/new

Include the NexoLLM version (Settings → About), your macOS version and the steps to reproduce.
You'll get an answer within a few days.

## Supported versions

Only the latest beta receives fixes.

## Verifying a download

Every release lists the SHA-256 of its files in `SHA256SUMS.txt`. Check yours with:

```bash
shasum -a 256 NexoLLM-*.dmg
```

## How the app protects you

The app has no network code, stores your history and memory encrypted (AES-256-GCM, key in the Keychain)
in an owner-only folder, never reads password fields or secure input, and is signed with the hardened
runtime, which blocks code injection.
