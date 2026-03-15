<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=140&section=header&text=AKASHA%20CORPORATION&fontSize=42&fontColor=ffffff&animation=fadeIn&fontAlignY=55"/>

<br>

[![HikariSystem](https://img.shields.io/badge/Ecosystem-HikariSystem-00e5ff?style=for-the-badge&logoColor=white)](#)
[![Field](https://img.shields.io/badge/Field-Reverse_Engineering-ff0055?style=for-the-badge&logoColor=white)](#)
[![Arch](https://img.shields.io/badge/Arch-x86_·_ARM_·_RISC--V-7c3aed?style=for-the-badge&logoColor=white)](#)


<br>

> *"To master the machine, one must first read its records."*

<br>

</div>

---

## What We Build

Akasha Corporation develops **low-level security tooling for binary analysis, CPU emulation, reverse engineering, and offensive security**. Our work lives at the boundary between software and hardware — where most tools stop, ours begins.

All projects operate under the **HikariSystem** philosophy: lean, composable, built for professionals.

---

## Flagship — HexCore IDE `v3.7.1`

**[HikariSystem-HexCore](https://github.com/AkashaCorporation/HikariSystem-HexCore)** is a full reverse engineering IDE purpose-built for malware analysis. Not a plugin. Not a wrapper around another tool. A complete analysis environment built from scratch on Code-OSS.
```
Static Analysis → CPU Emulation → IR Lifting → Decompilation → Automation Pipeline
```

| Layer | Technology | Status |
| :--- | :--- | :--- |
| Disassembly | Capstone v5 (N-API) | ✅ Production |
| CPU Emulation | Unicorn Engine (N-API) — 70+ API hooks | ✅ Production |
| Assembly & Patching | LLVM 18 MC (N-API) | ✅ Production |
| IR Lifting | Remill → LLVM IR (N-API) | ✅ Stable |
| Decompilation | Helix MLIR — C++23 pipeline (N-API) | ✅ v0.6.0 |
| Superoptimization | Souper (Z3 SMT) | 🔜 v3.8 |
| Automation Pipeline | `.hexcore_job.json` — headless batch analysis | ✅ Production |

**Latest:** `v3.7.1` — Permissive memory mapping, faithful glibc/MSVCRT PRNG emulation, VM detection heuristics, junk instruction filtering, runtime memory disassembly, `onResult` conditional pipeline branching.

---

## HikariSystem Arsenal

| Project | Description | Stage |
| :--- | :--- | :--- |
| **[HexCore](https://github.com/AkashaCorporation/HikariSystem-HexCore)** | Full reverse engineering IDE | `v3.7.1` |
| **[Scylla Studio](https://github.com/AkashaCorporation/HikariSystem-Scylla)** | Pentesting IDE — recon, HTTP testing, headless automation | Active |
| **[Tsurugi](https://github.com/ThreatBiih/HikariSystem-Tsurugi)** | Offensive security tooling | Active |
| **[Ananke](https://github.com/ThreatBiih/HikariSystem-Ananke)** | Threat intelligence & automation | Active |

---

## Native Engine Suite

High-performance N-API bindings. No external installs. No wrappers. Built in-house.

| Engine | Role | Version |
| :--- | :--- | :--- |
| **hexcore-capstone** | Multi-arch disassembly (x86, ARM, RISC-V) | `1.3.2` |
| **hexcore-unicorn** | CPU emulation with hook system | `1.2.1` |
| **hexcore-llvm-mc** | Binary assembly & patching (LLVM 18) | `1.0.0` |
| **hexcore-remill** | Machine code → LLVM IR lifting | `0.1.2` |
| **hexcore-helix** | LLVM IR → pseudo-C (C++23/MLIR, 3-tier pipeline) | `0.6.0` |

---

## Roadmap
```
v3.7.1  ████████████████████  ✅ Dynamic Intelligence + Pipeline Branching
v3.8    ████████████░░░░░░░░  🔧 Souper Superoptimizer + searchMemoryHeadless
v3.9    ████░░░░░░░░░░░░░░░░  📋 BinDiff + Job Queue Manager
v4.0    ██░░░░░░░░░░░░░░░░░░  🔮 Oracle Hook (Live AI Callbacks)
```

---

## Core Team

| | Handle | Role |
| :---: | :--- | :--- |
| 🐻 | **[LXrdKnowkill](https://github.com/LXrdKnowkill)** | Founder · Architecture · Everything |
| 🐺 | **[MayaRomanova](https://github.com/ReiMayaRomanova)** | C++23 · MLIR · Helix Engine |
| 🦂 | **[ThreatBiih](https://github.com/ThreatBiih)** | Threat Intel · Unicorn Engine · Frontend |
| 🦆 | **[YasminePayload](https://github.com/YasminePayload)** | Pipeline · Automation · Features |

---

## Community

HikariSystem is an open community working across security research, reverse engineering, malware analysis, and offensive tooling. If you're building something serious — you belong here.

**[→ Browse all repositories](https://github.com/AkashaCorporation?tab=repositories)**

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=100&section=footer"/>

*HikariSystem — Security Tools for Professionals | Copyright © 2026 **AkashaCorporation**. All rights reserved.*

</div>
