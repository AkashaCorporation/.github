<div align="center">

<img src="./Hydra%20Akasha.png" alt="Akasha Corporation" width="300"/>

# AKASHA CORPORATION

### Security research · Reverse engineering · Binary analysis · Offensive tooling

**Evidence-first security tooling for humans and agents.**

<br>

[![HexCore](https://img.shields.io/badge/HexCore-Reverse_Engineering-7c3aed?style=for-the-badge)](https://github.com/AkashaCorporation/HikariSystem-HexCore)
[![Scylla](https://img.shields.io/badge/Scylla-Offensive_Security-dc2626?style=for-the-badge)](https://github.com/AkashaCorporation/HikariSystem-Scylla)
[![Helix](https://img.shields.io/badge/Helix-MLIR_Decompiler-2563eb?style=for-the-badge)](https://github.com/AkashaCorporation/HexCore-Helix)

<br>

[Projects](#-projects) ·
[Architecture](#-the-hikari-ecosystem) ·
[Research](#-research-principles) ·
[Team](#-team) ·
[Community](#-community)

</div>

---

## ◈ About Akasha

**Akasha Corporation** builds open security tooling for reverse engineering, binary analysis, dynamic analysis, vulnerability research, and repeatable security experimentation.

Our projects focus on the layers where high-level abstractions stop being enough:

* native binaries and executable formats;
* disassembly and control-flow recovery;
* LLVM IR and MLIR;
* decompilation and type recovery;
* CPU and OS emulation;
* semantic analysis;
* reproducible automation;
* evidence-driven security research.

The ecosystem is designed for **human analysts and agentic workflows** alike.

We prefer explicit uncertainty over fabricated certainty, reproducible evidence over screenshots, and composable infrastructure over opaque automation.

---

# ✦ Projects

## HexCore

### Reverse-engineering and binary-analysis workbench

[**HikariSystem HexCore**](https://github.com/AkashaCorporation/HikariSystem-HexCore) is our flagship reverse-engineering environment, built on the VS Code workbench.

It combines static analysis, native lifting, MLIR-based decompilation, semantic analysis, controlled emulation, session persistence, and reproducible automation inside one workspace.

**Current stable release:** `v3.8.4`

```text
Binary
  │
  ├── Disassembly / CFG Recovery
  │
  ├── Remill → LLVM IR
  │            │
  │            └── Helix → MLIR → HAST → pseudo-C
  │                              │
  │                              └── HQL + HXDB
  │
  ├── Unicorn / Elixir Dynamic Analysis
  │
  └── Automation → Evidence → Reports
```

Some of the systems developed around HexCore include:

`HXDB` · `HQL` · `Helix` · `Pathfinder` · `Function Atlas` · `Elixir / Azoth` · `Revenant` · `Souper`

[**Explore HexCore →**](https://github.com/AkashaCorporation/HikariSystem-HexCore)

---

## Helix

### MLIR-first native decompiler

[**HexCore Helix**](https://github.com/AkashaCorporation/HexCore-Helix) transforms lifted LLVM IR into structured pseudo-C through a native C++23 / MLIR pipeline.

```text
LLVM IR
   ↓
HelixLow
   ↓
HelixMid
   ↓
HelixHigh
   ↓
C-AST / HAST
   ↓
pseudo-C
```

Helix works on control-flow structuring, calling-convention recovery, stack reconstruction, SSA recovery, type propagation, debug-information integration, and output-confidence tracking.

Its design principle is simple:

> **Fidelity over polish.**

When information cannot be reliably recovered, the pipeline should preserve that uncertainty instead of inventing a clean-looking answer.

[**Explore Helix →**](https://github.com/AkashaCorporation/HexCore-Helix)

---

## Scylla Studio

### Evidence-oriented offensive security workbench

[**HikariSystem Scylla**](https://github.com/AkashaCorporation/HikariSystem-Scylla) is a headless-first environment for web and API security experimentation.

Scylla models more than individual HTTP requests. Its engagement model connects:

```text
Identity
   +
Resource
   +
Expected Policy
   ↓
Governed Experiment
   ↓
HTTP / Scanner Evidence
   ↓
Observation
   ↓
Candidate
   ↓
Validated Finding
```

The goal is repeatable authorization and business-logic research where provenance and evidence remain attached to the result.

**Current development target:** `Scylla 3.0`

[**Explore Scylla →**](https://github.com/AkashaCorporation/HikariSystem-Scylla)

---

# ⌬ The Hikari Ecosystem

Akasha projects are designed as components rather than isolated experiments.

| Project                                                                           | Role                                              |
| --------------------------------------------------------------------------------- | ------------------------------------------------- |
| **[HexCore](https://github.com/AkashaCorporation/HikariSystem-HexCore)**          | Reverse-engineering and binary-analysis workbench |
| **[Helix](https://github.com/AkashaCorporation/HexCore-Helix)**                   | MLIR-first native decompiler                      |
| **[Scylla Studio](https://github.com/AkashaCorporation/HikariSystem-Scylla)**     | Offensive-security experimentation environment    |
| **[HQL](https://github.com/AkashaCorporation/hexcore-hql)**                       | Semantic query and behavioral analysis layer      |
| **[HikariLang](https://github.com/AkashaCorporation/HexCore-HikariLang)**         | Declarative binary-analysis workflow language     |
| **[Elixir / Project Azoth](https://github.com/AkashaCorporation/hexcore-elixir)** | Controlled dynamic analysis and instrumentation   |
| **[Project Pythia](https://github.com/AkashaCorporation/Project-Pythia)**         | Oracle-agent research for live analysis decisions |

### Native infrastructure

The ecosystem also maintains standalone native components used by HexCore:

[Capstone](https://github.com/AkashaCorporation/hexcore-capstone) ·
[Unicorn](https://github.com/AkashaCorporation/hexcore-unicorn) ·
[Remill](https://github.com/AkashaCorporation/hexcore-remill) ·
[Souper](https://github.com/AkashaCorporation/hexcore-souper) ·
[SQLite](https://github.com/AkashaCorporation/hexcore-better-sqlite3) ·
[Revenant](https://github.com/AkashaCorporation/hexcore-revenant)

These repositories keep native engines independently buildable and versionable while HexCore consumes validated prebuilt artifacts.

---

# ⚙ The Hikari Philosophy

### Evidence before conclusions

A successful scanner, decompiler pass, query, or emulation step does not automatically prove a security conclusion.

We deliberately distinguish:

```text
signal → candidate → evidence → validated conclusion
```

### Honest failure

Incomplete analysis should remain visibly incomplete.

Unknown types, unresolved control flow, partial decoding, missing evidence, timeouts, and unsupported semantics are analysis states — not opportunities to fabricate plausible output.

### Reproducibility

Research pipelines should be capable of describing:

* the exact binary being analyzed;
* the engine versions involved;
* the inputs and configuration;
* the evidence used;
* the analysis generation;
* the barriers encountered;
* and the resulting artifacts.

### Human + agent workflows

Akasha tooling is designed so the same underlying analysis infrastructure can be consumed through:

* interactive IDE workflows;
* headless jobs;
* structured query languages;
* command-line tools;
* and agentic analysis systems.

Agents should consume structured evidence rather than scrape a UI and guess what happened.

---

# ◇ Research Groups

Akasha is organized into focused engineering and research groups.
Each group has a technical lead responsible for its direction, while contributors may work across multiple groups when projects overlap.

<table>
<tr>
<td width="50%" valign="top">

### ◉ Binary Analysis Group

**Lead — [LXrdKnowkill](https://github.com/LXrdKnowkill)**

Decompiler architecture · binary lifting · control-flow recovery · type recovery · debug information · compiler infrastructure.

**Core projects**

HexCore · Helix · Pathfinder · Revenant · Souper

**Contributors**

MayaRomanova · ThreatBiih · YasminePayload

</td>

<td width="50%" valign="top">

### ◉ Emulation & Dynamic Analysis Group

**Lead — [ThreatBiih](https://github.com/ThreatBiih)**

CPU emulation · dynamic analysis · instrumentation · execution modeling · runtime evidence · emulation-assisted vulnerability research.

**Core projects**

HexCore Unicorn · Elixir / Project Azoth · Perseus · dynamic-analysis infrastructure

**Contributors**

LXrdKnowkill

</td>
</tr>

<tr>
<td width="50%" valign="top">

### ◉ Offensive Security Group

**Lead — [KrnL777](https://github.com/KrnL777)**

Vulnerability research · exploit development · web/API security · authorization testing · offensive automation.

**Core projects**

Scylla Studio · security research tooling · vulnerability research infrastructure

**Contributors**

ThreatBiih · LXrdKnowkill

</td>

<td width="50%" valign="top">

### ◉ Language Engineering Group

**Lead — [YasminePayload](https://github.com/YasminePayload)**

Semantic query languages · analysis DSLs · AST/HAST transformations · automation languages · structured interfaces for agents.

**Core projects**

HQL · HikariLang · C-AST/HAST analysis infrastructure · Bari Harness

**Contributors**

LXrdKnowkill · MayaRomanova

</td>
</tr>
</table>

> Group membership reflects primary technical responsibility rather than strict project boundaries. Akasha projects intentionally cross group boundaries.


# ⟐ Research Principles

## Open development

A significant portion of the Hikari ecosystem is developed publicly under permissive or open-source licenses appropriate to each component.

We publish implementation details, limitations, failed experiments, benchmarks, and negative results when they provide useful engineering evidence.

## Clean-room engineering where required

Components that replace or interoperate with restrictive ecosystems are developed with explicit license boundaries and documented provenance.

Project Azoth / Elixir, for example, maintains a clean-room development model around its dynamic-analysis infrastructure.

## AI-assisted engineering, disclosed

Modern AI systems are used throughout parts of our development and research process for tasks such as:

* implementation assistance;
* code review;
* test generation;
* architecture review;
* documentation;
* adversarial validation;
* and research exploration.

Material assistance is disclosed where appropriate.

AI output is treated as an input to engineering review — not as evidence by itself.

## Measure instead of assume

New analysis techniques are evaluated against controlled corpora and regression gates.

If an optimization, heuristic, or architecture does not produce measurable value, we prefer documenting that result over pretending otherwise.

---

# ◉ Team

Akasha is built by researchers and engineers working across multiple areas of the security stack.

| Member                                                  | Focus                                                       |
| ------------------------------------------------------- | ----------------------------------------------------------- |
| **[LXrdKnowkill](https://github.com/LXrdKnowkill)**     | Architecture · Binary Analysis · Compiler Infrastructure    |
| **[MayaRomanova](https://github.com/ReiMayaRomanova)**  | C++ · MLIR · Decompilation · AST Optimization               |
| **[ThreatBiih](https://github.com/ThreatBiih)**         | Security Research · Threat Intelligence · Frontend          |
| **[YasminePayload](https://github.com/YasminePayload)** | Automation · Language Engineering · HQL                     |
| **[KrnL777](https://github.com/KrnL777)**               | Reverse Engineering · Offensive Security · Exploit Research |

---

# ✦ Research & Publications

### Helix: Multi-Level IR Decompilation

**Multi-Level IR Decompilation via MLIR Dialect Lowering with Debug-Info-Guided Type Recovery, Empirical Pipeline Loss Analysis, and Output Correctness Validation**

Lukas Machado · Akasha Corporation · 2026

Research around Helix investigates multi-level intermediate representations, semantic-loss localization, type recovery, control-flow reconstruction, and evidence-aware decompiler validation.

---

# ♢ Community

Security tooling gets better when its assumptions are challenged.

Bug reports, reproducible test cases, architectural discussions, benchmarks, research comparisons, and contributions are welcome across the public Akasha repositories.

<div align="center">

[![Repositories](https://img.shields.io/badge/Browse_Repositories-181717?style=for-the-badge\&logo=github\&logoColor=white)](https://github.com/AkashaCorporation?tab=repositories)
[![Discord](https://img.shields.io/badge/Community_Discord-5865F2?style=for-the-badge\&logo=discord\&logoColor=white)](https://discord.gg/uQFb4nUAcT)

<br><br>

**AKASHA CORPORATION**

*Research the machine. Preserve the evidence.*

<sub>HikariSystem · Security tooling for reverse engineering and security research</sub>

</div>
