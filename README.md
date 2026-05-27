<div align="center">

<img src="https://readme-typing-svg.herokuapp.com?font=JetBrains+Mono&weight=500&size=34&duration=3500&pause=1000&color=8B0000&center=true&vCenter=true&width=1000&lines=none;Adaptive+Autonomous+Security+Research+Agent;Signal-Driven+Reconnaissance;Validation-First+Offensive+Research;Persistent+Operational+Memory" />

<br/>

<p align="center">
  <img src="https://img.shields.io/github/stars/Sol0-dev/none?style=for-the-badge&color=111111&labelColor=000000" />
  <img src="https://img.shields.io/github/last-commit/Sol0-dev/none?style=for-the-badge&color=1b1b1b&labelColor=000000" />
  <img src="https://img.shields.io/github/license/Sol0-dev/none?style=for-the-badge&color=2d0a0a&labelColor=000000" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Mode-Offensive%20Research-0f0f0f?style=for-the-badge&logo=ghost&logoColor=white" />
  <img src="https://img.shields.io/badge/Validation-Real%20PoC-3d0c0c?style=for-the-badge&logo=hackthebox&logoColor=white" />
  <img src="https://img.shields.io/badge/Focus-High%20Impact%20Only-141414?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Memory-Persistent-1d1d1d?style=for-the-badge" />
</p>

### Adaptive Autonomous Offensive Security Framework

*Signal-driven reconnaissance · adaptive exploitation · validated proof-of-concept generation · persistent operational memory*

</div>

---

<p align="center">

```text
█████████████████████████████████████████████████████████████████

    TARGET → RECON → ANALYZE → EXPLOIT → VALIDATE → LEARN

█████████████████████████████████████████████████████████████████
```

</p>

# Overview

`none` is an **adaptive autonomous offensive security framework** built for **real-world vulnerability research**.

Unlike traditional scanners that prioritize noise and coverage, `none` focuses on:

- **validated exploitability**
- **environment-aware testing**
- **adaptive attack strategies**
- **persistent operational memory**
- **high-confidence findings**

The framework continuously adapts based on observed signals:

```text
Headers
Framework behavior
Authentication flows
Infrastructure patterns
Timing anomalies
Response deltas
Middleware fingerprints
Cloud behavior
```

The objective is simple:

> **Find vulnerabilities that actually matter.**

---

# Mission

`none` exists to optimize for:

### Signal > Noise

Payloads are selected based on observed behavior rather than blind automation.

Environment fingerprinting occurs **before exploitation**.

### Validation > Theory

A vulnerability exists only when:

```text
Impact is verified
A PoC exists
Exploitability is demonstrated
```

No speculative reporting.

No assumption-driven findings.

### Pattern Recognition First

Every target behaves differently.

`none` adapts based on:

- frameworks
- routing behavior
- middleware
- runtime signatures
- auth flows
- infrastructure layers

### Chain Findings Upward

Low severity observations become escalation paths.

```text
Information Disclosure
            ↓
Internal Endpoint Discovery
            ↓
SSRF
            ↓
Privilege Escalation
```

---

# Operator Workflow

<div align="center">

```mermaid
flowchart LR

A[Target Surface] --> B[Recon Pipeline]
B --> C[Stack Fingerprinting]
C --> D[Pattern Recognition]
D --> E[Adaptive Exploitation]
E --> F[PoC Validation]
F --> G[Persistent Memory]
G --> D
```

</div>

---

# Architecture

```text
                           ┌────────────────────┐
                           │   Target Surface   │
                           └─────────┬──────────┘
                                     │
                               Recon Pipeline
                                     │
      ┌──────────────────────────────┼─────────────────────────────┐
      │                              │                             │
      ▼                              ▼                             ▼
┌───────────────┐          ┌────────────────┐         ┌────────────────┐
│ Stack Analysis│          │ Surface Mapping│         │ Burp Replay    │
│ Framework ID  │          │ Endpoint Graph │         │ Request History│
└───────┬───────┘          └────────┬───────┘         └────────┬───────┘
        └───────────────────────────┴──────────────────────────┘
                                     │
                                     ▼
                        ┌────────────────────────┐
                        │ Pattern Recognition    │
                        │ Context Awareness      │
                        └────────────┬───────────┘
                                     │
                                     ▼
                        ┌────────────────────────┐
                        │ Exploitation Engine    │
                        │ Adaptive Payloads      │
                        └────────────┬───────────┘
                                     │
                                     ▼
                        ┌────────────────────────┐
                        │ PoC Validation         │
                        │ Impact Confirmation    │
                        └────────────┬───────────┘
                                     │
                                     ▼
                        ┌────────────────────────┐
                        │ Persistent Memory      │
                        │ Lessons + Sessions     │
                        └────────────────────────┘
```

---

# Capability Matrix

| Module | Description |
|:--|:--|
| **Reconnaissance** | Surface discovery, endpoint expansion |
| **Fingerprinting** | Framework, runtime, auth identification |
| **Exploitation** | Context-aware vulnerability testing |
| **Persistence** | Session recovery + operational memory |
| **Validation** | PoC generation and exploit verification |
| **Automation** | Burp MCP + Kali MCP + shell tooling |

---

# Supported Vulnerability Classes

<div align="center">

`XSS` • `SSRF` • `IDOR/BOLA` • `SQL Injection`

`SSTI` • `XXE` • `JWT Abuse` • `OAuth`

`Race Conditions` • `2FA Bypass`

`HTTP Smuggling` • `Cache Poisoning`

`GraphQL Abuse` • `Business Logic Vulnerabilities`

`Path Traversal` • `Command Injection`

</div>

---

# Repository Structure

```text
none/
│
├── .gemini/
│   ├── GEMINI.md
│   └── settings.json
│
├── agents/
│   └── none/
│       ├── session.json
│       ├── findings/
│       ├── lessons/
│       └── fullrecon/
│
├── prompts/
├── configs/
├── docs/
│
├── mcp-proxy.jar
│
└── README.md
```

---

# Environment Setup

## 01 — Clone Repository

```bash
git clone https://github.com/Sol0-dev/none.git
cd none
```

---

## 02 — Install Gemini CLI

Install Gemini CLI globally:

```bash
npm install -g @google/gemini-cli
```

Verify installation:

```bash
gemini --version
```

---

## 03 — Configure `.gemini`

Move the provided Gemini configuration into the hidden folder:

```bash
mv gemini .gemini
```

Final structure:

```text
none/
└── .gemini/
    ├── GEMINI.md
    └── settings.json
```

`GEMINI.md` acts as the **persistent operational instruction source**.

At startup, Gemini automatically loads:

```text
Recon methodology
Persistence model
Vulnerability logic
Session state
Operational behavior
Burp MCP usage
Kali MCP integration
```

---

# Burp MCP Setup

## Install Burp Suite Pro

Install:

```text
Burp Suite Professional
```

Launch Burp.

---

## Install Burp MCP via BApp Store

Open:

```text
Extensions → BApp Store
```

Search for:

```text
MCP
```

Install the **Burp MCP extension**.

---

## Extract MCP Proxy JAR

After installation, locate the installed extension.

Extract the extension:

```bash
unzip burp-mcp.jar -d burp-mcp
```

Move:

```bash
mv burp-mcp/mcp-proxy.jar ~/none/
```

Expected structure:

```text
~/none/
├── .gemini/
├── mcp-proxy.jar
└── README.md
```

---

## Configure Burp MCP

Edit:

```text
~/none/.gemini/settings.json
```

Burp configuration:

```json
"burp": {
  "command": "/usr/bin/java",
  "args": [
    "-jar",
    "~/none/mcp-proxy.jar",
    "--sse-url",
    "http://127.0.0.1:9876/"
  ],
  "timeout": 30000,
  "trust": true
}
```

This enables:

```text
Request replay
History analysis
Traffic inspection
Manual validation
PoC verification
```

---

# Kali MCP Setup

Install Kali MCP:

```bash
npm install -g mcp-server
```

Start server:

```bash
mcp-server --server http://127.0.0.1:9999/
```

Verify:

```bash
curl http://127.0.0.1:9999/
```

Your Gemini agent can now access:

```text
subfinder
httpx
katana
gau
ffuf
nuclei
dalfox
sqlmap
ghauri
trufflehog
dnsx
interactsh-client
```

---

# `.gemini/settings.json`

Create:

```text
~/none/.gemini/settings.json
```

Paste:

```json
{
  "theme": "Default",
  "selectedAuthType": "oauth-personal",
```
