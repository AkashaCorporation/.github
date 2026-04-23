<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=140&section=header&text=AKASHA%20CORPORATION&fontSize=42&fontColor=ffffff&animation=fadeIn&fontAlignY=55"/>

<br>

<img src="./Hydra%20Akasha.png" alt="Akasha Corporation — Hydra" width="320"/>

<br><br>

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

## Flagship — HexCore IDE `v3.8.0`

**[HikariSystem-HexCore](https://github.com/AkashaCorporation/HikariSystem-HexCore)** is a full reverse engineering IDE purpose-built for malware analysis. Not a plugin. Not a wrapper around another tool. A complete analysis environment built from scratch on Code-OSS.


Static Analysis → CPU Emulation → IR Lifting → Decompilation → Superoptimization → Dynamic Analysis → Automation Pipeline


| Layer | Technology | Status |
| :--- | :--- | :--- |
| Disassembly | Capstone v5 (N-API) | Production |
| CPU Emulation | Unicorn Engine 2.1.4 (N-API) — SharedArrayBuffer zero-copy hooks (Project Perseus) | Production |
| Assembly & Patching | LLVM 18 MC (N-API) | Production |
| IR Lifting | Remill → LLVM IR (N-API) — format-aware (PE64/ELF modes) | Production |
| Decompilation | Helix MLIR — C++23 pipeline, C AST layer, type recovery, SCC Tarjan | `v0.9.0` |
| Superoptimization | Souper (Z3 SMT + alive2) — LLVM IR rewrite verification | `v0.1.0` |
| Dynamic Analysis | Elixir (Project Azoth) — Unicorn + Interceptor + Stalker, clean-room Qiling replacement | `v1.0.0` |
| Type Recovery | DWARF 5 + PDB + ET_REL feeder (Pathfinder) — 3,864 sigs + 792 structs on `mali_kbase.ko` | Production |
| Session Persistence | SQLite-backed `.hexcore_session.db` — renames, retypes, bookmarks | Production |
| Automation Pipeline | `.hexcore_job.json` — headless batch analysis + Job Queue Manager | Production |

**Latest:** `v3.8.0` "Souper Era + Pathfinder + Project Azoth + DWARF Type Pipeline" — Pathfinder DWARF/PDB/ET_REL metadata feeder (kernel modules now surface full debug content), Helix v0.9.0 with type recovery, Project Azoth clean-room dynamic analysis engine, Project Perseus zero-copy Unicorn hooks (1.34× throughput), Souper LLVM IR superoptimizer, Refcount Scanner, Anti-Analysis Detection, API Hash Resolver, Job Queue Manager for concurrent agentic pipelines.

---

## HikariSystem Arsenal

| Project | Description | Version |
| :--- | :--- | :--- |
| **[HexCore](https://github.com/AkashaCorporation/HikariSystem-HexCore)** | Full reverse engineering IDE — disassembly, emulation, decompilation, superoptimization | `v3.8.0` |
| **[Scylla Studio](https://github.com/AkashaCorporation/HikariSystem-Scylla)** | Pentesting IDE — recon, HTTP testing, headless automation | Active |
| **[Tsurugi](https://github.com/ThreatBiih/HikariSystem-Tsurugi)** | Offensive security tooling | Active |
| **[Ananke](https://github.com/ThreatBiih/HikariSystem-Ananke)** | Threat intelligence & automation | Active |

---

## Native Engine Suite

High-performance N-API bindings. No external installs. No wrappers. Built in-house. All engines published on npm.

| Engine | Role | Version |
| :--- | :--- | :--- |
| **[hexcore-capstone](https://www.npmjs.com/package/hexcore-capstone)** | Multi-arch disassembly (x86, ARM, RISC-V) | `1.3.4` |
| **[hexcore-unicorn](https://www.npmjs.com/package/hexcore-unicorn)** | CPU emulation with SharedArrayBuffer zero-copy hooks (Unicorn 2.1.4) | `1.3.0` |
| **[hexcore-llvm-mc](https://www.npmjs.com/package/hexcore-llvm-mc)** | Binary assembly & patching (LLVM 18) | `1.0.1` |
| **[hexcore-remill](https://www.npmjs.com/package/hexcore-remill)** | Machine code → LLVM IR lifting (format-aware) | `0.4.0` |
| **hexcore-helix** | LLVM IR → C via C++23/MLIR (type recovery, SCC Tarjan, DCE) | `0.9.0` |
| **hexcore-elixir** | Dynamic analysis — Unicorn + Interceptor + Stalker (Project Azoth) | `1.0.0` |
| **[hexcore-souper](https://www.npmjs.com/package/hexcore-souper)** | LLVM IR superoptimizer via Z3 SMT solving | `0.1.0` |
| **[hexcore-better-sqlite3](https://www.npmjs.com/package/hexcore-better-sqlite3)** | SQLite for session persistence & IOC storage | `2.0.1` |

---

## Roadmap

<br>
v3.7.4 ████████████████████ Released — Format-Aware Lifting + Helix C AST

<br>
v3.8.0 ████████████████████ Released — Souper + Pathfinder + Project Azoth + DWARF Pipeline
<br>

v3.8.1 ████░░░░░░░░░░░░░░░░ Planned — Queue polish (position field + pool size setting)
<br>
v3.9.0 ████░░░░░░░░░░░░░░░░ Planned — BinDiff Integration + Sticky Session Routing
<br>
v4.0.0 ██░░░░░░░░░░░░░░░░░░ Research — Oracle Hook (Live AI Callbacks)




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

**[Browse all repositories →](https://github.com/AkashaCorporation?tab=repositories)**
<br>
**[Join our Discord server →](https://discord.gg/uQFb4nUAcT)**

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=100&section=footer"/>

*HikariSystem — Security Tools for Professionals*
*Copyright © 2026 Akasha Corporation. All rights reserved.*

</div>
