# Open Futures

**Building foundational, principled, and self-contained software for the future.**

Welcome to the **Open Futures** organization. We are dedicated to creating robust, transparent, and highly controlled software systems. In an era of increasing software complexity, hidden dependencies, and opaque supply chains, we build tools that prioritize reproducibility, minimal dependency footprints, host isolation, and foundational integrity.

---

## 📦 Core Repositories

Our work is currently centered around two foundational projects:

### 1. [os-builder](https://github.com/open-futures/os-builder)
**Build your own custom OS, via kernel + userland.**  
A comprehensive, three-script toolchain for building a custom Linux distribution entirely from source. It packages the OS into a bootable hybrid ISO installer (BIOS + UEFI + USB-bootable) and optionally produces a container image.
- **Key Features:** 9-phase reproducible build pipeline, host-isolation guarantees (never modifies the host system), out-of-tree kernel module support, ZFS snapshot automation, kernel module signing, and TPM/measured boot support.
- **Tech Stack:** Shell, Linux Kernel, OpenZFS, Dracut, GRUB/ISOLINUX.

### 2. [ai-natural-language](https://github.com/open-futures/ai-natural-language)
**TTS SDK — Text Tagged Specification v3.5.2**  
A high-performance C++23 SDK for the TTS (Text Tagged Specification) format, a TIFF-inspired container for structured text. Designed for agent memory, semantic search, and zero-copy data access.
- **Key Features:** Zero-copy TTF/ATTF parsers, real OpenAI embedding integration (with graceful fallbacks), runtime AES-NI hardware detection, pluggable KMS key provider adapters (AWS/GCP/Vault without heavy SDK dependencies), and an interactive TUI browser.
- **Tech Stack:** C++23, CMake, FTXUI, with N-API (Node.js), ctypes (Python), and cgo (Go) bindings.

---

## 🧭 Our Philosophy

Both of our core projects are governed by a strict set of design principles, documented in their respective `PHILOSOPHY.md` files. Our shared values include:

- **Host-Isolation & Security:** Build tools must never silently modify the host system. All operations are strictly confined to designated build directories with robust cleanup traps.
- **Minimal Dependency Surface:** The dependency surface is the API's portability surface. We avoid heavy third-party frameworks (e.g., libcurl, heavy cloud SDKs) in favor of lean, purpose-built implementations or pluggable interfaces.
- **Reproducibility & Determinism:** Pinned versions, config-hash-based caching, and explicit build phases ensure that a build today is identical to a build tomorrow.
- **Zero-Copy & Efficiency:** When dealing with data formats, zero-copy access is not just an optimization—it's a moral position. Agents and systems should think in addresses and raw substrates.
- **Anti-Monopoly & Openness:** Formats and tools should be free for all, forever. We design systems that prevent vendor lock-in and empower users to own their infrastructure and data.

---

## 🚀 Getting Started

Each repository is designed to be self-contained and easy to bootstrap:

- **For `os-builder`:** Ensure you have the required host dependencies (e.g., `gcc`, `make`, `dracut`, `xorriso`), then run `sudo ./os-builder.sh` to interactively build your custom OS, followed by `sudo ./iso-builder.sh` to generate the bootable ISO.
- **For `ai-natural-language`:** Ensure you have CMake ≥ 3.20 and a C++23 compiler. Run `cmake -S . -B build -DCMAKE_BUILD_TYPE=Release && cmake --build build -j` to compile the SDK, CLI tools, and run the 50+ test suite.

Refer to the individual `README.md` files in each repository for detailed quick-start guides, architecture overviews, and troubleshooting steps.

---

## 🤝 Contributing

We welcome contributions that align with our core philosophy. Before submitting a pull request:
1. Read the `PHILOSOPHY.md` file in the respective repository.
2. Ensure your changes do not introduce unnecessary external dependencies.
3. Verify that host-isolation and reproducibility guarantees remain intact.
4. Add or update tests to cover new functionality.

---

## 📜 License

Unless otherwise specified, projects in this organization are licensed under the **BSD-2-Clause License**, ensuring maximum freedom for use, modification, and distribution while maintaining minimal restrictions.

---

*2026 Open Futures. Building the foundation, one principled commit at a time.*
