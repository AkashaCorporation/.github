<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=160&section=header&text=AKASHA%20CORPORATION&fontSize=44&fontColor=ffffff&animation=fadeIn&fontAlignY=42&desc=Security%20Tooling%20%C2%B7%20Reverse%20Engineering%20%C2%B7%20Binary%20Analysis&descAlignY=68&descSize=14"/>

<br>

<img src="./Hydra%20Akasha.png" alt="Akasha Corporation — Hydra" width="320"/>

<br><br>

[![Ecosystem](https://img.shields.io/badge/Ecosystem-HikariSystem-00e5ff?style=for-the-badge&logoColor=white)](#)
[![Field](https://img.shields.io/badge/Field-Reverse_Engineering-ff0055?style=for-the-badge&logoColor=white)](#)
[![Arch](https://img.shields.io/badge/Arch-x86_·_ARM_·_RISC--V-7c3aed?style=for-the-badge&logoColor=white)](#)
[![License](https://img.shields.io/badge/Open_Source-MIT_·_Apache--2.0_·_GPL--2.0-50fa7b?style=for-the-badge&logoColor=white)](#)

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

## ✦ &nbsp; Flagship — HexCore IDE `v3.8.2.2` stable · `v3.8.3` RC

**[HikariSystem-HexCore](https://github.com/AkashaCorporation/HikariSystem-HexCore)** is a full reverse engineering IDE purpose-built for malware analysis and binary research. It is a complete, integrated analysis environment built on Code-OSS rather than a loose collection of editor plugins.

<div align="center">

```
Static Analysis → CPU Emulation → IR Lifting → Decompilation → Semantic Queries → Dynamic Analysis → Automation
```

</div>

<br>

| Layer | Technology | Status |
| :--- | :--- | :--- |
| **Disassembly** | Capstone v5 (N-API) | Production |
| **CPU Emulation** | Unicorn Engine 2.1.4 (N-API) — SharedArrayBuffer zero-copy hooks *(Project Perseus)* | Production |
| **Assembly & Patching** | LLVM 18 MC (N-API) | Production |
| **IR Lifting** | Remill → LLVM IR (N-API) — format-aware (PE64 / ELF / ET\_REL) | Production |
| **Native Decompilation** | Helix MLIR — C++23 pipeline, structured control flow, C AST, debug-info-guided types | `v0.9.3` |
| **Managed Decompilation** | Revenant — portable ILSpy-based C# / IL recovery, including .NET single-file apphosts | `v0.4.0` |
| **Superoptimization** | Souper — Z3 SMT + alive2 — first Windows N-API port | `v0.2.0` |
| **Dynamic Analysis** | Elixir — Unicorn + Interceptor + Stalker *(Project Azoth, clean-room)* | `v1.0.3` |
| **Semantic Queries** | HQL — behavioral signatures over normalized Helix C ASTs | `v0.1.2` |
| **Type Recovery** | Pathfinder DWARF 5 + PDB + ET\_REL feeder — 3,864 sigs + 792 structs on `mali_kbase.ko` | Production |
| **Session Persistence** | SQLite-backed `.hexcore_session.db` — renames, retypes, bookmarks, IOCs | Production |
| **Automation Pipeline** | `.hexcore_job.json` — validated headless jobs, queueing, capability discovery, and evidence-gated outcomes | Production |

<br>

**Latest stable release —** `v3.8.2.2` · Elixir runtime packaging hotfix

`v3.8.2` added callfuscation analysis, control-flow deflattening, AArch64 lifting, and stronger discovery on obfuscated binaries. The `v3.8.2.1` and `v3.8.2.2` hotfixes hardened pipeline error reporting, file watching, and Elixir runtime packaging.

**Current release candidate —** `v3.8.3` *"Honest Analysis at Scale"*

> The RC focuses on correctness under automation: deterministic job isolation, semantic failure propagation, managed/native routing, HQL packaging, portable Revenant recovery, safer native lifecycles, Helix `v0.9.3`, and reproducible release-driven native prebuilds. It remains an RC until the packaged application completes the controlled acceptance corpus.

---

## ⌬ &nbsp; HikariSystem Arsenal

| Project | Description | Version |
| :--- | :--- | :--- |
| **[HexCore](https://github.com/AkashaCorporation/HikariSystem-HexCore)** | Full reverse engineering IDE — disassembly, emulation, decompilation, semantic analysis, automation | `v3.8.2.2` stable / `v3.8.3` RC |
| **[Scylla Studio](https://github.com/AkashaCorporation/HikariSystem-Scylla)** | Pentesting IDE — recon, HTTP testing, headless automation, browser-driven vuln discovery | Active |
| **[HikariLang](https://github.com/AkashaCorporation/HexCore-HikariLang)** | Language research for binary analysis and future HexCore integrations | Research |
| **[HQL](https://github.com/AkashaCorporation/hexcore-hql)** | Semantic pattern matching over normalized decompiler C ASTs | Active |
| **[Project Pythia](https://github.com/AkashaCorporation/Project-Pythia)** | Evidence-oriented assisted-analysis research for HexCore | Research |

---

## ⚙ &nbsp; Engine Suite

HexCore integrates native modules, compiler pipelines, and portable sidecar engines through versioned standalone repositories. GitHub Actions consumes dependency ZIPs from standalone releases, builds the canonical `.node` prebuilds, publishes them back to those releases, and assembles the IDE without requiring users to install native toolchains.

| Engine | Role | Version |
| :--- | :--- | :--- |
| **[hexcore-capstone](https://github.com/AkashaCorporation/hexcore-capstone)** | Multi-architecture disassembly binding | `1.3.5` |
| **[hexcore-unicorn](https://github.com/AkashaCorporation/hexcore-unicorn)** | CPU emulation with SharedArrayBuffer zero-copy hooks | `1.3.1` |
| **[hexcore-llvm-mc](https://github.com/AkashaCorporation/hexcore-llvm-mc)** | Binary assembly and patching with LLVM 18 MC | `1.0.2` |
| **[hexcore-remill](https://github.com/AkashaCorporation/hexcore-remill)** | Machine code → LLVM IR lifting with format-aware recovery | `0.5.1` |
| **[HexCore-Helix](https://github.com/AkashaCorporation/HexCore-Helix)** | LLVM IR → structured pseudo-C through C++23 and MLIR | `0.9.3` |
| **[hexcore-elixir](https://github.com/AkashaCorporation/hexcore-elixir)** | Dynamic analysis with Unicorn, Interceptor, and Stalker | `1.0.3` |
| **[hexcore-souper](https://github.com/AkashaCorporation/hexcore-souper)** | LLVM IR superoptimization through Z3 SMT | `0.2.0` |
| **[hexcore-better-sqlite3](https://github.com/AkashaCorporation/hexcore-better-sqlite3)** | SQLite-backed session persistence and IOC storage | `2.0.3` |
| **[hexcore-revenant](https://github.com/AkashaCorporation/hexcore-revenant)** | Self-contained managed .NET decompilation via ILSpy | `0.4.0` |

Rellic remains disabled. Souper remains active and is evaluated with corpus evidence rather than assumed optimization wins.

---

## ✺ &nbsp; Roadmap

```
v3.8.0     ████████████████████   Released   ·   Souper + Pathfinder + Project Azoth + DWARF
v3.8.1     ████████████████████   Released   ·   Stability + Helix 0.9.1 + Pythia
v3.8.2.2   ████████████████████   Released   ·   Obfuscation analysis + runtime hotfixes
v3.8.3     ████████████████░░░░   RC         ·   Honest automation + Helix 0.9.3 + Revenant + HQL
v3.9.0     ████░░░░░░░░░░░░░░░░   Planned    ·   BinDiff integration + HikariLang
v4.x       ██░░░░░░░░░░░░░░░░░░   Research   ·   Aletheia/Pythia evidence-gated assisted analysis
```

---

## ⟐ &nbsp; Research Groups

Akasha's research operates in three groups, each with distinct objectives and project portfolios. Members may participate across groups when their work crosses domain boundaries.

<br>

### ◉ &nbsp; Binary Analysis Group · *Akasha Corporation*

Decompilation pipeline architecture · binary lifting · CPU emulation · type recovery · debug-info-guided analysis · MLIR dialect design.

**Active projects —** HexCore · Helix · Pathfinder · Souper · Project Azoth (Elixir) · Revenant

**Members —** LXrdKnowkill · MayaRomanova

<br>

### ◉ &nbsp; Offensive Security Group · *Akasha Corporation*

Pentesting automation · vulnerability discovery · browser-driven exploitation · headless reconnaissance · threat intelligence.

**Active projects —** Scylla Studio · Tsurugi · Ananke

**Members —** ThreatBiih · KrnL777 · LXrdKnowkill

<br>

### ◉ &nbsp; Language Engineering Group · *Akasha Corporation*

Domain-specific query languages over binary IR · semantic pattern matching · CAst optimizers and elimination passes · IR transformation infrastructure.

**Active projects —** HQL *(HikariSystem Query Language — semantic pattern matching over Helix C AST output)* · HikariLang · C AST optimization passes

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

**Open by default —** Our tools are released under MIT, Apache-2.0, or GPL-2.0 licenses as appropriate. We publish negative results: `hexcore-souper` is documented openly as having near-zero impact on production binaries, useful information for the community.

**LLM-in-the-loop, disclosed —** We use AI assistants (including Codex, Claude, and Gemini) across literature review, design review, implementation, and adversarial validation. Publications disclose material AI assistance in their acknowledgments.

**Clean-room when required —** Project Azoth (Elixir dynamic analysis) is developed under strict clean-room separation from upstream references, with `LICENSE_AUDIT` requirements on every contribution.

**Reproducibility —** Pipeline loss analysis methodology, used in our Helix research, produces structured `[P0-TRACE]` logs at every pass boundary. The same methodology that backs our research backs our debugging.

---

## ✦ &nbsp; Publications

| Title | Authors | Venue / Status |
| :--- | :--- | :--- |
| Helix: Multi-Level IR Decompilation via MLIR Dialect Lowering with Debug-Info-Guided Type Recovery, Empirical Pipeline Loss Analysis, and Output Correctness Validation | LXrdKnowkill (Lukas Machado) | Preprint · Akasha Corporation · 2026 |

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
