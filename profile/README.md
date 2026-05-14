<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=160&section=header&text=AKASHA%20CORPORATION&fontSize=44&fontColor=ffffff&animation=fadeIn&fontAlignY=42&desc=Security%20Tooling%20%C2%B7%20Reverse%20Engineering%20%C2%B7%20Binary%20Analysis&descAlignY=68&descSize=14"/>

<br>

<img src="./Hydra%20Akasha.png" alt="Akasha Corporation — Hydra" width="320"/>

<br><br>

[![Ecosystem](https://img.shields.io/badge/Ecosystem-HikariSystem-00e5ff?style=for-the-badge&logoColor=white)](#)
[![Field](https://img.shields.io/badge/Field-Reverse_Engineering-ff0055?style=for-the-badge&logoColor=white)](#)
[![Arch](https://img.shields.io/badge/Arch-x86_·_ARM_·_RISC--V-7c3aed?style=for-the-badge&logoColor=white)](#)
[![License](https://img.shields.io/badge/License-MIT_·_Apache--2.0-50fa7b?style=for-the-badge&logoColor=white)](#)

<br>

> ### *"To master the machine, one must first read its records."*

<br>

</div>

---

## ⟁ &nbsp; What We Build

Akasha Corporation develops **low-level security tooling for binary analysis, CPU emulation, reverse engineering, and offensive security**. Our work lives at the boundary between software and hardware — where most tools stop, ours begins.

All projects operate under the **HikariSystem** philosophy: lean, composable, built for professionals.

We publish in the open. We document negative results. We credit our tools. We do not ship vaporware.

---

## ✦ &nbsp; Flagship — HexCore IDE `v3.8.0`

**[HikariSystem-HexCore](https://github.com/AkashaCorporation/HikariSystem-HexCore)** is a full reverse engineering IDE purpose-built for malware analysis and binary research. Not a plugin. Not a wrapper around another tool. A complete analysis environment built from scratch on Code-OSS.

<div align="center">

```
Static Analysis → CPU Emulation → IR Lifting → Decompilation → Superoptimization → Dynamic Analysis → Automation
```

</div>

<br>

| Layer | Technology | Status |
| :--- | :--- | :--- |
| **Disassembly** | Capstone v5 (N-API) | Production |
| **CPU Emulation** | Unicorn Engine 2.1.4 (N-API) — SharedArrayBuffer zero-copy hooks *(Project Perseus)* | Production |
| **Assembly & Patching** | LLVM 18 MC (N-API) | Production |
| **IR Lifting** | Remill → LLVM IR (N-API) — format-aware (PE64 / ELF / ET\_REL) | Production |
| **Decompilation** | Helix MLIR — C++23 pipeline, C AST layer, SCC Tarjan, debug-info-guided types | `v0.9.0` |
| **Superoptimization** | Souper — Z3 SMT + alive2 — first Windows N-API port | `v0.2.0` |
| **Dynamic Analysis** | Elixir — Unicorn + Interceptor + Stalker *(Project Azoth, clean-room Qiling replacement)* | `v1.0.0` |
| **Type Recovery** | Pathfinder DWARF 5 + PDB + ET\_REL feeder — 3,864 sigs + 792 structs on `mali_kbase.ko` | Production |
| **Session Persistence** | SQLite-backed `.hexcore_session.db` — renames, retypes, bookmarks, IOCs | Production |
| **Automation Pipeline** | `.hexcore_job.json` — headless batch + Job Queue Manager with priority scheduling | Production |

<br>

**Latest release —** `v3.8.0` *"Souper Era + Pathfinder + Project Azoth + DWARF Type Pipeline"*

> Pathfinder DWARF/PDB/ET\_REL metadata feeder unlocks full debug content on kernel modules · Helix v0.9.0 with debug-info-guided type recovery (0% → 90%+ typed parameters on stripped `.ko`) · Project Azoth clean-room dynamic analysis engine (Rust + C++23, Apache-2.0) · Project Perseus zero-copy Unicorn hooks (1.34× throughput, eliminates 65% TSFN drop rate) · Souper LLVM IR superoptimizer with Z3 SMT solving · Refcount Scanner · Anti-Analysis Detection · API Hash Resolver · Job Queue Manager for concurrent agentic pipelines.

---

## ⌬ &nbsp; HikariSystem Arsenal

| Project | Description | Version |
| :--- | :--- | :--- |
| **[HexCore](https://github.com/AkashaCorporation/HikariSystem-HexCore)** | Full reverse engineering IDE — disassembly, emulation, decompilation, superoptimization | `v3.8.0` |
| **[Scylla Studio](https://github.com/AkashaCorporation/HikariSystem-Scylla)** | Pentesting IDE — recon, HTTP testing, headless automation, browser-driven vuln discovery | Active |
| **[Tsurugi](https://github.com/ThreatBiih/HikariSystem-Tsurugi)** | Offensive security tooling | Active |
| **[Ananke](https://github.com/ThreatBiih/HikariSystem-Ananke)** | Threat intelligence & automation | Active |

---

## ⚙ &nbsp; Native Engine Suite

High-performance N-API bindings. No external installs. No wrappers. Built in-house. All engines published on npm.

| Engine | Role | Version |
| :--- | :--- | :--- |
| **[hexcore-capstone](https://www.npmjs.com/package/hexcore-capstone)** | Multi-arch disassembly (x86, ARM, RISC-V) | `1.3.4` |
| **[hexcore-unicorn](https://www.npmjs.com/package/hexcore-unicorn)** | CPU emulation with SharedArrayBuffer zero-copy hooks (Unicorn 2.1.4) | `1.3.0` |
| **[hexcore-llvm-mc](https://www.npmjs.com/package/hexcore-llvm-mc)** | Binary assembly & patching (LLVM 18) | `1.0.1` |
| **[hexcore-remill](https://www.npmjs.com/package/hexcore-remill)** | Machine code → LLVM IR lifting — format-aware fork with CET / XED-ILD / CALL fall-through patches | `0.4.0` |
| **hexcore-helix** | LLVM IR → C via C++23/MLIR — 24+ passes, three custom dialects, SSA splitting, type recovery | `0.9.0` |
| **hexcore-elixir** | Dynamic analysis — Unicorn + Interceptor + Stalker (Project Azoth, Apache-2.0) | `1.0.0` |
| **[hexcore-souper](https://www.npmjs.com/package/hexcore-souper)** | LLVM IR superoptimizer via Z3 SMT — **first Windows N-API port of Google Souper** | `0.2.0` |
| **[hexcore-better-sqlite3](https://www.npmjs.com/package/hexcore-better-sqlite3)** | SQLite for session persistence & IOC storage | `2.0.1` |

---

## ✺ &nbsp; Roadmap

```
v3.7.4   ████████████████████   Released   ·   Format-Aware Lifting + Helix C AST
v3.8.0   ████████████████████   Released   ·   Souper + Pathfinder + Project Azoth + DWARF
v3.8.1   ████░░░░░░░░░░░░░░░░   Planned    ·   Queue polish (position field + pool size)
v3.9.0   ████░░░░░░░░░░░░░░░░   Planned    ·   BinDiff Integration + Sticky Session Routing
v4.0.0   ██░░░░░░░░░░░░░░░░░░   Research   ·   Oracle Hook — Live AI Callbacks
```

---

## ⟐ &nbsp; Research Groups

Akasha's research operates in three groups, each with distinct objectives and project portfolios. Members may participate across groups when their work crosses domain boundaries.

<br>

### ◉ &nbsp; Binary Analysis Group · *Akasha Corporation*

Decompilation pipeline architecture · binary lifting · CPU emulation · type recovery · debug-info-guided analysis · MLIR dialect design.

**Active projects —** HexCore · Helix · Pathfinder · Souper · Project Azoth (Elixir)

**Members —** LXrdKnowkill · MayaRomanova

<br>

### ◉ &nbsp; Offensive Security Group · *Akasha Corporation*

Pentesting automation · vulnerability discovery · browser-driven exploitation · headless reconnaissance · threat intelligence.

**Active projects —** Scylla Studio · Tsurugi · Ananke

**Members —** ThreatBiih · KrnL777 · LXrdKnowkill

<br>

### ◉ &nbsp; Language Engineering Group · *Akasha Corporation*

Domain-specific query languages over binary IR · semantic pattern matching · CAst optimizers and elimination passes · IR transformation infrastructure.

**Active projects —** HQL *(HikariSystem Query Language — semantic pattern matching engine for HexCore over Helix decompiler output)* · CAst optimization passes

**Members —** YasminePayload · MayaRomanova · LXrdKnowkill

---

## ⚭ &nbsp; Core Team

|  | Handle | Domain |
| :---: | :--- | :--- |
| 🐻 | **[LXrdKnowkill](https://github.com/LXrdKnowkill)** | Founder · Architecture · Compiler Infrastructure |
| 🐺 | **[MayaRomanova](https://github.com/ReiMayaRomanova)** | C++23 · MLIR · Helix Engine · CAst Optimizers |
| 🦂 | **[ThreatBiih](https://github.com/ThreatBiih)** | Threat Intelligence · Unicorn Engine · Frontend |
| 🦆 | **[YasminePayload](https://github.com/YasminePayload)** | Pipeline · Automation · HQL Language Design |
| 🐼 | **[KrnL777](https://github.com/KrnL777)** | Reverse Engineering · Exploit Development |

---

## ⟡ &nbsp; Research Practice

Akasha follows transparent research practice aligned with modern academic standards.

**Open by default —** Our tools are released under MIT and Apache-2.0 licenses. We publish negative results: `hexcore-souper` is documented openly as having near-zero impact on production binaries, useful information for the community.

**LLM-in-the-loop, disclosed —** We use AI assistants (Claude, Gemini) across literature review, design review, and implementation review. All publications credit AI assistance in acknowledgments, following the transparency model established by ReSym (CCS 2024, Distinguished Paper).

**Clean-room when required —** Project Azoth (Elixir dynamic analysis) is developed under strict clean-room separation from upstream references, with `LICENSE_AUDIT` requirements on every contribution.

**Reproducibility —** Pipeline loss analysis methodology, used in our Helix research, produces structured `[P0-TRACE]` logs at every pass boundary. The same methodology that backs our research backs our debugging.

---

## ✦ &nbsp; Publications

| Title | Authors | Venue / Status |
| :--- | :--- | :--- |
| Helix: Multi-Level IR Decompilation via MLIR Dialect Lowering with Debug-Info-Guided Type Recovery and Empirical Pipeline Loss Analysis | LXrdKnowkill (Lukas Machado) | Preprint · Akasha Corporation · 2026 |

---

## ⟁ &nbsp; Community

HikariSystem is an open community working across security research, reverse engineering, malware analysis, and offensive tooling. If you're building something serious — you belong here.

<br>

<div align="center">

[![Repositories](https://img.shields.io/badge/Browse_All_Repositories-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/AkashaCorporation?tab=repositories)
[![Discord](https://img.shields.io/badge/Join_Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/uQFb4nUAcT)

</div>

<br>

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=100&section=footer"/>

<br>

**HikariSystem** &nbsp; · &nbsp; *Security Tools for Professionals*

<sub>Copyright © 2026 Akasha Corporation. All rights reserved.</sub>

<br>

<img src="https://komarev.com/ghpvc/?username=AkashaCorporation&color=ff0055&style=for-the-badge&label=ORGANIZATION+VIEWS"/>

</div>
