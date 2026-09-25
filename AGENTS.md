---
tags: [meta, agents, governance, linux, hardware]
---

# AGENTS.md — MACROKEY-DRIVER Governance Rules

This repository contains **MACROKEY-DRIVER**, a driver and configuration tool for 6-button USB macro keyboards with rotary encoders.

When modifying any file in this repository, follow these mandatory governance rules:

**Language Tier:** A (Public OSS) — see [language-policy.md](file:///mnt/NVME_PCI/agentic-ai/governance/language-policy.md). All logs, CLI strings, documentation, and comments MUST be in English.

## 🦀 Standards & Integrity

1. **RUST MIGRATION DIRECTIVE** — Any new feature, daemon, or tool rewrite must be implemented in native Rust (`edition = "2024"`). Do not expand the Python footprint (`ARCH-NO-PYTHON`).

2. **MANDATORY STENIOSENTINEL VERIFICATION (RULE 0)** — Before completing any turn or committing, execute `stenio --diff` or `stenio --path .`. The Quality Gate must pass with zero blocking errors.

3. **SECURITY & ZERO SECRETS (`SEC-SECRETS`)** — Never commit credentials, tokens, or private secrets.

4. **STANDARDIZED README DISCLAIMER** — The root `README.md` must preserve the standardized vibe-coded governance disclaimer:
   ```markdown
   <div align="center">

   > **Yes... This is a Vibe Coded project**
   >
   > Governed by 🤖 **StenioSentinel** (our Rust-based AI Governance Sentinel) with **Carlos Eduardo Rodrigues** ([@ceduardorodrig](https://github.com/ceduardorodrig)).

   </div>
   ```
