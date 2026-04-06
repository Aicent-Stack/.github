[![Organism Vitality & Protocol Audit](https://github.com/Aicent-Stack/aicent-stack/actions/workflows/rust-ci.yml/badge.svg)](https://github.com/Aicent-Stack/aicent-stack/actions/workflows/rust-ci.yml)

<p align="left">
  <img src="https://img.shields.io/badge/Status-Homeostasis-brightgreen.svg" alt="Status">
  <img src="https://img.shields.io/badge/Language-Rust-orange.svg" alt="Language">
  <img src="https://img.shields.io/badge/Specs-RFC--001--006-blue.svg" alt="Specs">
  <img src="https://img.shields.io/badge/License-Apache--2.0-lightgrey.svg" alt="License">
</p>

⚪ **AICENT** | 💎 **RTTP** | 🔴 **RPKI** | 🟢 **ZCMK** | 🟡 **GTIOT** | 🟣 **AICENT-NET**
# DEPENDENCY POLICY: Supply Chain Immunity

> *"A dependency is a foreign gene. To protect the Homeostasis of the organism, every third-party crate must undergo the Immunity Audit. We do not tolerate latency-pathogens or memory-leaks."*

This document defines the rigorous standards for incorporating external dependencies (crates) into the **Aicent Stack** repositories. Our goal is to maintain a lean, high-performance, and secure neural spine.

---

## 🛡️ 1. The Immunity Standard

All dependencies must meet the following mandatory criteria before integration:

### 1.1 Memory Safety & Language
Only **Rust-native** dependencies are permitted. Foreign Function Interfaces (FFI) to non-memory-safe languages (C/C++) are strictly prohibited in the critical reflex path unless wrapped in a verified sovereign abstraction.

### 1.2 Latency Determinism
Crates that utilize non-deterministic synchronization primitives or introduce significant **Latency-Tax** (garbage collection, heavy locking, or excessive heap allocation) are classified as **Pathogens** and rejected.

### 1.3 Audit Status
Every dependency must be audited for:
- **Zero-Allocation Potential:** Can the crate run in a `no_std` or heap-allocation-free environment?
- **Supply Chain Security:** Analysis of the maintainer's reputation and the crate's update frequency.

---

## 🔬 2. Permitted "Core Nutrients"

The Aicent Stack white-lists the following foundational libraries as "Core Nutrients":

- **`tokio`**: For high-performance asynchronous orchestration.
- **`serde`**: For RFC-compliant bit-stream serialization.
- **`simd` / `packed_simd`**: For hardware-accelerated RPKI and ZCMK logic.
- **`embassy`**: For hard-real-time GTIOT execution.

---

## 📜 3. Dependency Mutation Process

To propose adding a new dependency, follow the **Mutation Protocol**:

1.  **Benchmarking:** Submit a [Pathogen Report](https://github.com/Aicent-Stack/.github/issues/new/choose) showing the impact of the crate on the **165.28µs reflex arc**.
2.  **Logic Audit:** Verify that the crate does not contain hidden telemetry or non-sovereign backdoors.
3.  **Finality:** The Architects of the Hive must reach a **2/3 majority quorum** to approve the integration.

---

## 📡 4. Continuous Surveillance

The [Aicent Traffic Sentinel](https://github.com/Aicent-Stack/aicent-traffic) and automated CI/CD pipelines continuously scan all 12 repositories for **"Dependency Drift."** Any unauthorized version updates or insecure dependency trees will trigger an autonomous **QUARANTINE_PULSE**.

---
🔗 **Technical Genome:** [Aicent Docs](https://github.com/Aicent-Stack/aicent-docs)
🚀 **Ecosystem:** [Hive-Rise v1.0-Alpha](https://github.com/Aicent-Stack/aicent-stack/releases/tag/v1.0-Alpha)

*"Intention is the Source; Sovereignty is the Law."*
---
© 2026 Aicent.com Organization. **SYSTEM STATUS: PURE-BLOODED**
