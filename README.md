# 🔮 CEL2CLI

**Common Expression Language for Agent Control**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.11+](https://img.shields.io/badge/python-3.11+-blue.svg)](https://www.python.org/downloads/)
[![Project Status: Design/Architecture](https://img.shields.io/badge/status-Design%2FArchitecture-orange.svg)](https://github.com/cel2cli/cel2cli)

> ⚠️ **Project Status: Under Active Development**  
> This project is currently in the final design and architecture phase. Implementation is not yet available.

---

## 📖 Overview

CEL2CLI provides a unified, secure, and observable interface for controlling AI agents across multiple platforms using Google's Common Expression Language (CEL).

**Key Features:**
- 🤖 **Unified Agent Control** - Manage agents on LangGraph, CrewAI, AutoGen, n8n, and more through a single language
- 🔒 **Enterprise-Grade Security** - RBAC, comprehensive audit logging, and "Deny by Default" security model
- 💎 **Resilient & Observable** - Built-in retry for failed operations, partial failure handling, structured logging and metrics
- 🎯 **Flexible Interfaces** - Interact via CLI, REST API, or interactive REPL

---

## 🎯 What Problem Does It Solve?

Managing AI agents across different platforms is fragmented. Each platform has its own API, CLI, and operational model. CEL2CLI provides:

- A **single expression language** for all platforms
- A **consistent interface** regardless of backend technology
- **Type-safe operations** with security built-in from the ground up
- A complete **audit trail** for all agent operations, ensuring compliance and accountability

---

## 🚀 Quick Start

*Coming soon - project is under development*
```bash
# Install (not yet available)
pip install cel2cli

# Execute CEL expressions
cel2cli exec -e "agents.list()"
cel2cli exec -e "agents.filter(agents.list(), a -> a.status == 'failed').restart_parallel(max=5)"

# Start interactive REPL
cel2cli repl
```

---

## 🏗️ Architecture

CEL2CLI is built with a clean, layered architecture ensuring maintainability, testability, and security:
```
┌─────────────────────────────────────────────────────────┐
│                  PRESENTATION LAYER                     │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐               │
│  │   CLI    │  │   REST   │  │   REPL   │               │
│  │  Click   │  │  FastAPI │  │  prompt  │               │
│  └──────────┘  └──────────┘  └──────────┘               │
└─────────────────────────────────────────────────────────┘
                         │
┌──────────────────────────────────────────────────────┐
│                     ENGINE LAYER                     │
│  ┌────────────────────────────────────────────────┐  │
│  │       CELEngine (Orchestrator)                 │  │
│  │  - Execute pipeline                            │  │
│  │  - Retry functionality                         │  │
│  │  - State tracking                              │  │
│  └────────────────────────────────────────────────┘  │
└──────────────────────────────────────────────────────┘
          │              │              │
┌─────────┴──────┐  ┌───┴────┐  ┌──────┴──────┐
│   STDLIB       │  │SECURITY│  │   ADAPTER   │
│  - agents.*    │  │ - RBAC │  │ - Protocol  │
│  - system.*    │  │ - Audit│  │ - HTTP      │
│  - utils.*     │  │        │  │ - Mock      │
└────────────────┘  └────────┘  └─────────────┘
          │              │              │
┌─────────┴──────────────┴──────────────┴─────────┐
│                  CORE LAYER                     │
│  ┌────────┐  ┌─────────┐  ┌──────────┐          │
│  │ Parser │  │  Type   │  │Evaluator │          │
│  │        │  │ Checker │  │          │          │
│  └────────┘  └─────────┘  └──────────┘          │
└─────────────────────────────────────────────────┘
```

**Full architecture documentation:** [Coming soon]

---

## 🛠️ Supported Platforms

**Current Development Focus:**
- ✅ HTTP/REST APIs (generic)
- 🚧 LangGraph
- 🚧 CrewAI
- 📋 AutoGen (planned)
- 📋 n8n (planned)

**Want support for another platform?** [Open an issue](https://github.com/cel2cli/cel2cli/issues)

---

## 📚 Documentation

- 🏗️ [Architecture Documentation](./docs/architecture.md) *(in progress)*
- 📖 [User Guide](./docs/user-guide.md) *(coming soon)*
- 🔧 [Developer Guide](./docs/developer-guide.md) *(coming soon)*
- 🎓 [Examples](./examples/) *(coming soon)*

---

## 🤝 Contributing

We welcome contributions! The project is in early development, but you can:

- ⭐ **Star this repo** to show support
- 👀 **Watch** for updates
- 💡 **Open issues** for feature requests or bugs
- 📖 **Improve documentation**
- 💻 **Contribute code** (once implementation starts)

**Development Status:** Currently finalizing complete architecture and design specification.

---

## 🗺️ Roadmap

### Phase 1: Foundation *(Current)*
- [x] Complete architecture design
- [x] Domain registration (cel2cli.com, .dev, .org)
- [x] GitHub organization setup
- [ ] Finalize API and data model specification
- [ ] Prepare initial project scaffolding

### Phase 2: MVP Implementation
- [ ] Core Layer (Parser, Type Checker, Evaluator)
- [ ] Security & Stdlib Layers
- [ ] Mock & HTTP Adapters
- [ ] Engine Layer with State Store
- [ ] CLI implementation (exec, retry, repl)

### Phase 3: Platform Expansion
- [ ] LangGraph Adapter
- [ ] CrewAI Adapter
- [ ] REST API Server (FastAPI)

### Phase 4: Production Ready
- [ ] Comprehensive testing (coverage > 80%)
- [ ] Performance optimization
- [ ] Complete documentation
- [ ] v1.0.0 Release

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🔗 Links

- 🌐 **Website:** [cel2cli.com](https://cel2cli.com) *(coming soon)*
- 📦 **PyPI:** [pypi.org/project/cel2cli](https://pypi.org/project/cel2cli) *(placeholder)*
- 🐳 **Docker:** [hub.docker.com/r/cel2cli/cel2cli](https://hub.docker.com/r/cel2cli/cel2cli) *(coming soon)*
- 📧 **Contact:** info@cel2cli.com

---

## ⭐ Show Your Support

If you find this project interesting, please consider:
- ⭐ Starring the repository
- 👀 Watching for updates
- 🔄 Sharing with others

---

<p align="center">
  <sub>Built with ❤️ by the CEL2CLI team</sub>
</p>
