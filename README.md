# LIZO Security OS

A Debian-based Linux distribution for learning and practicing ethical hacking, built around guided workflows, structured reports, and authorized-lab use.

> **Status:** Early development (pre-0.1). The ISO build and core tooling are being built incrementally.

## What is LIZO?

LIZO is a custom Debian live ISO with an XFCE desktop and a small set of security tools, plus its own command-line interface. Instead of being a broad toolbox, LIZO focuses on:

- **Guided workflows**: step-by-step assessment flows instead of memorizing raw commands
- **Learning mode**: built-in lessons for beginners
- **Lab mode**: tools directed only at explicitly authorized local targets
- **CTF mode**: local, intentionally vulnerable challenges
- **Reports**: assessment results stored in a database and turned into reports from real scan data

LIZO orchestrates existing open-source security tools. It does not replace them.

## Planned architecture

```
LIZO/
├── build/      # live-build config for the ISO
├── core/       # Python backend (tool runner, scope check, results DB, reports)
├── cli/        # `lizo` command-line interface
├── gui/        # dashboard (after CLI/core are stable)
├── lessons/    # learning mode content
├── docs/
└── tests/
```

## Roadmap

- [ ] 0.1: Bootable Debian + XFCE ISO with `lizo` CLI and branding
- [ ] 0.2: Core tool runner and target scope enforcement
- [ ] 0.3: Recon workflow and SQLite results database
- [ ] 0.4: Report generator
- [ ] 0.5: Learning mode and CTF mode
- [ ] 0.6: GUI dashboard
- [ ] 1.0: Hardening, tests, documentation, reproducible builds

## Building the ISO

Build inside a Debian VM (e.g. VirtualBox), not on your main OS.

```bash
sudo apt update
sudo apt install live-build git
git clone https://github.com/71ZK1/LIZO.git
cd LIZO/build
lb config
sudo lb build
```

Boot the resulting ISO in a separate test VM.

## Responsible use

LIZO is for education and **authorized** security testing only. Only test systems you own or have explicit written permission to assess. The authors are not responsible for misuse.
