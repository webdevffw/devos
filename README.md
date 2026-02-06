# Consolidated & completed layer model

## Intention

I want to improve my developer tooling & setup, and I would like to be strategic & deliberate about the process of doing so.

We want to centralize the maintenance and configuration of our setup as much as possible. Making it idempotent and transferable across machines/devices, utilizing scripts, packages, and general configuration files to enable fast and easy setup across multiple machines or envionments. Rendering total portability across devices or environments.

### A layered developer environment

An opinionated, reproducible “developer OS” mean to run on any given developer machine.

Every meaningful choice (tools, preferences, visuals, behavior) is:

* Centralized
* Versioned
* Reproducible

The setup is:
* Idempotent (safe to re-run, always converges to the same state)
* Portable (new laptop, VM, container, remote box → same experience)
* Device-independent (no hidden state or manual tweaking)

Configuration is:
* Mostly declarative
* Script-driven with a single entry point
* Capable of fully overwriting existing configs when desired

Research is treated as a first-class artifact:
* Maintian a durable decision record
* A future lookup resource
* A way to compare alternatives at each functional layer before committing

Here’s a more complete layering model, from hardware-adjacent → cognitive interface:

1. **Operating System & Package Layer**
2. **System Configuration / Dotfile Orchestration & Config Managers**
3. **Terminal Emulator**
4. **Shell**
5. **Prompt / Status Line**
6. **Terminal Multiplexer**
7. **Editor / IDE**
8. **Language Toolchains & Runtimes**
9. **Developer UX Enhancements**
10. **Fonts & Visual Assets**
11. **Remote & Sync Layer**

[Additional details can be found here](./subject/README.md)

[First pass implementation](./research/glossary/first-pass.term.md)