# 🧬 Contributing to the Sovereign AI Organism

**Thank you for choosing to evolve the Aicent Stack. You are not just contributing to a codebase; you are architecting the foundational nervous system for autonomous, sovereign intelligence.**

[![Status](https://img.shields.io/badge/Status-Homeostasis-brightgreen.svg)](#)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Org](https://img.shields.io/badge/Org-Aicent.com-blue.svg)](http://aicent.com)

---

## 🏛️ The Aicent Engineering Philosophy

The Aicent Stack is an **indivisible organism**. Every line of code must respect the **Metabolic Homeostasis** of the system. We prioritize physical determinism over legacy software abstraction.

### The Three Pillars of Contribution:
1. **Sub-millisecond Reflex:** If your logic introduces >10µs of overhead without SIMD/Hardware offloading justification, it will be rejected.
2. **Atomic Sovereignty:** Trust is never delegated to external oracles. Every pulse must be self-authenticated via RPKI (RFC-003).
3. **Zero Extraction:** Value flow is circulatory. We eliminate middleman taxes via ZCMK (RFC-004) atomic settlement.

---

## 🔬 The RFC-First Workflow

We do not accept "amazing features" without a protocol foundation. All major changes must align with the existing **RFC Suite**:

1. **Review:** Study [RFC-001 through RFC-005](https://github.com/Aicent-Stack/manifesto/tree/main/rfcs) in the `manifesto` repository.
2. **Proposal:** Open an Issue with the prefix `[EVOLUTION-PROPOSAL]`.
3. **Audit:** Technical leadership (The Aicent Brain) will review the proposal for architectural consistency.

---

## 🦀 Technical Standards (Hardcore Only)

- **Language:** Performant Rust (1.75+).
- **Memory:** Zero-allocation/Zero-copy on the critical path of `RTTP` and `RPKI`.
- **Concurrency:** Lock-free data structures only for high-frequency task shunting.
- **Safety:** Every `unsafe` block MUST have a `// SAFETY:` comment documenting the memory/hardware boundary justification.
- **Embedded:** GTIOT contributions must adhere to `no_std` principles for bare-metal compatibility.

---

## 🛠️ Execution Path

```bash
# 1. Pull the Sovereign Workspace
git clone https://github.com/Aicent-Stack/aicent-stack.git
cd aicent-stack

# 2. Verify Local Homeostasis
cargo build --workspace
cargo clippy --workspace -- -D warnings
cargo test --workspace
```

1. **Fork** the target repository under the Aicent-Stack organization.
2. **Branch:** Use `evolution/` prefix (e.g., `evolution/rttp-xdp-offload`).
3. **Commit:** Follow [Conventional Commits](https://www.conventionalcommits.org/).
4. **Audit:** Ensure all CI stages in `.github/workflows/rust-ci.yml` pass.

---

## 📜 Sovereign Ownership & Licensing

🛡️ By contributing to Aicent Stack, you agree that your contributions are licensed under **Apache-2.0**. Your code becomes part of a global, indivisible AI organism managed by the **Aicent.com Organization**.

---
**SYSTEM STATUS: HOMEOTASIS**  
*"The latency-tax is dead. Join the pulse."*

[Follow the Evolution @Aicent_com](https://x.com/Aicent_com) | [Visit Aicent.com](http://aicent.com)

---
