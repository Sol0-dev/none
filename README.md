<div align="center">

# none

**Adaptive Autonomous Security Research Agent**

Signal-driven offensive research · validated exploitability · persistent operational memory

<br>

![Runtime](https://img.shields.io/badge/runtime-gemini_cli-0f0f0f?style=flat-square)
![Mode](https://img.shields.io/badge/mode-offensive_research-171717?style=flat-square)
![Focus](https://img.shields.io/badge/focus-validated_poc-3b0d0d?style=flat-square)
![Priority](https://img.shields.io/badge/priority-high_impact_only-111111?style=flat-square)
![Status](https://img.shields.io/badge/status-active-1c1c1c?style=flat-square)

</div>

---

## Overview

`none` is an adaptive autonomous offensive security research framework designed to identify, validate, and chain **high-impact vulnerabilities**.

The system prioritizes **real exploitability**, **environmental adaptation**, and **validated proof-of-concept execution** over speculative findings.

Rather than blindly firing payloads, `none` performs:

- Stack fingerprinting
- Surface mapping
- Pattern recognition
- Exploitation adaptation
- Session persistence
- Signal-based prioritization

The objective is not theoretical coverage.

The objective is **real impact**.

---

## Design Philosophy

The framework operates under several core assumptions:

### Signal > Noise

Payloads are adapted to observed behavior.

Response deltas, stack indicators, timing anomalies, framework fingerprints, and infrastructure signals are analyzed before exploitation begins.

### Validation > Theory

A finding only exists when a working proof-of-concept exists.

No speculative reporting.

No assumption-driven exploitation.

### Pattern Recognition First

Every target behaves differently.

`none` fingerprints frameworks, routing behavior, response structures, authentication models, and middleware before selecting attack paths.

### Chain Findings Upward

Low severity observations are treated as escalation paths.

Information disclosure → SSRF  
Weak authorization → IDOR chain  
Misconfiguration → account compromise

---

## Architecture

```text
                           ┌──────────────────────┐
                           │    Target Surface    │
                           └──────────┬───────────┘
                                      │
                              Recon Pipeline
                                      │
        ┌─────────────────────────────┼─────────────────────────────┐
        │                             │                             │
        ▼                             ▼                             ▼
┌────────────────┐         ┌────────────────┐         ┌────────────────┐
│ Stack Analysis │         │ Surface Mapping│         │ Burp History   │
│ Framework ID   │         │ Endpoint Graph │         │ Request Replay │
└────────┬───────┘         └────────┬───────┘         └────────┬───────┘
         └──────────────────────────┴──────────────────────────┘
                                      │
                                      ▼
                         ┌────────────────────────┐
                         │ Pattern Recognition    │
                         │ Target Adaptation      │
                         └────────────┬───────────┘
                                      │
                                      ▼
                         ┌────────────────────────┐
                         │ Exploitation Engine    │
                         │ Context-Aware Testing  │
                         └────────────┬───────────┘
                                      │
                                      ▼
                         ┌────────────────────────┐
                         │ PoC Validation         │
                         │ Impact Verification    │
                         └────────────┬───────────┘
                                      │
                                      ▼
                         ┌────────────────────────┐
                         │ Persistent Memory      │
                         │ Lessons / Iterations   │
                         └────────────────────────┘
```

---

## Operational Workflow

```text
Recon
   ↓
Surface Mapping
   ↓
Stack Fingerprinting
   ↓
Pattern Recognition
   ↓
Target-Specific Exploitation
   ↓
PoC Validation
   ↓
Chain Escalation
   ↓
Session Persistence
```

Every phase is stateful.

Sessions persist across interruptions and can be resumed without losing:

- Recon output
- Surface maps
- Stack fingerprints
- Findings
- Lessons learned
- Exploitation state

---

## Capabilities

### Reconnaissance

Automated background enumeration and attack surface discovery.

| Capability | Description |
|------------|-------------|
| Subdomain Discovery | Passive enumeration and expansion |
| DNS Resolution | A/CNAME resolution and infrastructure mapping |
| HTTP Fingerprinting | Framework, status, redirects, titles |
| Historical URL Mining | Wayback + archival collection |
| JavaScript Crawling | Endpoint discovery |
| Parameter Extraction | Query and POST parameter harvesting |
| Secret Discovery | JS secret extraction |
| Endpoint Enumeration | Surface expansion |

---

### Stack Fingerprinting

Before exploitation begins, `none` fingerprints:

```text
Headers
Frameworks
Runtime behavior
Error signatures
Authentication models
Infrastructure layers
Caching behavior
Cloud providers
Reverse proxy chains
```

Observed signals dynamically alter exploitation priority.

Example:

| Signal | Priority Shift |
|--------|----------------|
| Express | Prototype pollution / SSRF |
| GraphQL | Schema abuse / IDOR |
| Rails | SSTI / traversal |
| Spring | Actuator / SSRF |
| JWT Auth | Token confusion |
| Cloudflare | Cache poisoning |

---

### Vulnerability Classes

`none` supports adaptive testing for:

```text
XSS
SSRF
IDOR / BOLA
SQL Injection
SSTI
XXE
JWT Exploitation
OAuth / SSO Abuse
2FA Bypass
Access Control Failures
CORS Misconfiguration
HTTP Request Smuggling
Cache Poisoning
Race Conditions
GraphQL Abuse
Business Logic Vulnerabilities
File Upload Exploitation
Path Traversal / LFI
Command Injection
```

Payload selection is context-aware and signal-driven.

---

## Session Persistence

State is continuously maintained.

```json
{
  "session_id": "<uuid>",
  "target": "<domain>",
  "phase": "recon",
  "stack_fingerprint": {},
  "surface_map": {},
  "tested_classes": [],
  "findings": [],
  "chains": [],
  "lessons": [],
  "iteration_count": 0
}
```

Sessions can be:

```bash
resume
pause
stop
restore
continue
```

Interruptions do not lose operational state.

---

## Toolchain

### Recon

```text
subfinder
assetfinder
dnsx
httpx
katana
gau
waybackurls
ffuf
dalfox
nuclei
sqlmap
ghauri
trufflehog
interactsh-client
```

### Integrations

```text
Burp Suite MCP
Kali MCP
Gemini CLI
Shell execution
Web fetch
File persistence
```

---

## Quick Start

### Clone Repository

```bash
git clone https://github.com/yourusername/none.git
cd none
```

### Install Dependencies

```bash
go install github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
go install github.com/projectdiscovery/httpx/cmd/httpx@latest
go install github.com/projectdiscovery/dnsx/cmd/dnsx@latest
go install github.com/projectdiscovery/katana/cmd/katana@latest
go install github.com/projectdiscovery/nuclei/v3/cmd/nuclei@latest
```

### Start Session

```bash
none start target.com
```

Resume previous operation:

```bash
none resume
```

---

## Example Operation

### Recon Dispatch

```bash
TARGET="example.com"

subfinder -d $TARGET
assetfinder --subs-only $TARGET
httpx -tech-detect
katana -jc -d 4
gau $TARGET
nuclei -severity high,critical
```

### Stack Fingerprinting

```bash
curl -si https://$TARGET | grep \
"server:|x-powered-by:|x-runtime:"
```

### Adaptive Exploitation

```text
Signal:
X-Powered-By: Express

Priority Shift:
→ Prototype Pollution
→ SSRF
→ NoSQL Injection
```

---

## Research Principles

`none` follows a strict operational model:

```text
Observe
Adapt
Validate
Escalate
Persist
Learn
```

The framework does not optimize for scan volume.

It optimizes for **high-confidence exploitability**.

---

## Repository Structure

```text
.
├── agents/
│   └── none/
│       ├── session.json
│       ├── lessons/
│       ├── findings/
│       └── fullrecon/
│
├── prompts/
├── configs/
├── tools/
└── docs/
```

---

## Security Research Notice

This project is intended for:

- Authorized security research
- Adversary emulation
- Defensive validation
- Red team operations
- Bug bounty research

Operators are responsible for ensuring all activity complies with applicable law, organizational policy, and authorization boundaries.

---

<div align="center">

**Built for offensive research.**

Signal-driven. Context-aware. Validation-first.

</div>
