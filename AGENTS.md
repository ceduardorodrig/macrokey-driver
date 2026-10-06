---
tags: [meta, agents, governance, linux, hardware]
---

# AGENTS.md — MACROKEY-DRIVER Governance Rules

This repository contains **MACROKEY-DRIVER**, a driver and configuration tool for 6-button USB macro keyboards with rotary encoders.

When modifying any file in this repository, follow these mandatory governance rules:

**Language Tier:** A (Public OSS) — see [language-policy.md](file:///mnt/NVME_PCI/agentic-ai/governance/language-policy.md). All logs, CLI strings, documentation, and comments MUST be in English.

**Repository Category: DERIVED (fork)** — see [agent-conventions.md](file:///mnt/NVME_PCI/agentic-ai/governance/agent-conventions.md) §2b.

> This repository is a **fork** of [`nonatofabio/macrokey-driver`](https://github.com/nonatofabio/macrokey-driver).
> It is **not authored code**: upstream is the source of truth for the driver itself, and
> local changes are small, focused contributions (media keys, persistence, docs).
>
> Because of that, the ecosystem's **architectural laws do NOT apply here** —
> `ARCH-NO-PYTHON`, `GOV-AGENT-LAWS` (the 38 Hub laws) and `RUST-*` describe how the
> author builds his own software, not how one contributes to someone else's project.
> A rule that cannot be satisfied without rewriting upstream code is a **dead law**,
> and dead laws erode the living ones.

## 🦀 Standards & Integrity

1. **NO UPSTREAM REWRITE DIRECTIVE** — There is deliberately **no** mandate to port this
   driver to Rust. Promising a rewrite of third-party code that will not happen would
   create a permanently broken gate. New local features should stay consistent with the
   upstream language and style (Python), and contributions are welcome upstream.

2. **MANDATORY STENIOSENTINEL VERIFICATION (RULE 0)** — Before completing any turn or
   committing, run the gate over the subset that applies to a derived repository:
   ```bash
   stenio --scope fork --path .   # quando o escopo existir no motor (proposta v3.3.0)
   stenio --diff                  # hoje: valida o que o escopo padrão já cobre
   ```
   > ⚠️ `--scope fork` é **proposta registrada**, ainda não implementada. Enquanto não
   > existir, **não** rode `--scope all` aqui: ele acusa centenas de `ARCH-NO-PYTHON`
   > por design e o resultado será ruído, não diagnóstico.
   > Ver `governance/stenio-troubleshooting.md` §3.

3. **SECURITY & ZERO SECRETS (`SEC-SECRETS`)** — Never commit credentials, tokens, or
   private secrets. This one **always applies**, derived or not.

4. **UPSTREAM ATTRIBUTION** — Keep the upstream license, authorship and purchase links
   intact. A fork inherits the obligation to credit the original work.

5. **STANDARDIZED README DISCLAIMER** — The root `README.md` must preserve the standardized governance disclaimer:
   ```markdown
   <div align="center">

   ### 🛡️ Human-in-the-Loop Agentic Engineering & Deterministic Governance

   > **Architected by an Anthropologist, Built with Autonomous AI Agents, Governed by Deterministic Code.**
   > 
   > This project was developed through rigorous human-AI pair programming led by **Carlos Eduardo Rodrigues** ([@ceduardorodrig](https://github.com/ceduardorodrig)) — an anthropologist and product architect using autonomous coding agents under strict, sub-millisecond static governance.
   >
   > Every commit, driver, and system architecture is continuously audited and enforced by 🤖 **[StenioSentinel](https://github.com/ceduardorodrig/STENIO-SENTINEL)** (our native Rust quality gate) with zero tolerance for hallucinated tests, blind merges, or bypassed checks.

   </div>
   ```
