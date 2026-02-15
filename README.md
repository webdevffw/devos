# Consolidated & completed layer model

Development and deployment strategies

## Intention

> A **portable, declarative, idempotent developer environment**—treating the *entire dev setup as code*, not as a pile of snowflake machines.

I want to improve my developer tooling & setup, and I would like to be strategic & deliberate about the process of doing so.

We want to centralize the maintenance and configuration of our setup as much as possible. Making it idempotent and transferable across machines/devices, utilizing scripts, packages, and general configuration files to enable fast and easy setup across multiple machines or envionments. Rendering total portability across devices or environments.

### Approaches to configuration

- Configuration by file (a `config.json`)
- Configuration by plugin system
- Configuration by downloadable resources (including fonts)
- Configuration by server pull (autocomplete etc)

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
* A durable decision record
* A future lookup resource
* A way to compare alternatives at each functional layer before committing

### Research strategy

For each Layer we should research and compare the available platforms/tools, and for each selected option, we need to add an entry of it's configuration to the centralized config file, which combines with a given script to be able to regenerate or rewrite the entire configuration if needed. In fact, the script should have an entry point that allows it to overwrite and update the configurations readily and as needed.

We also need a research strategy and outline for each of these available platforms in order to have a reasonably flushed out but high level view into all the available options. This will serve for pre-emptive decision making and also as a resource for future lookup.

---

### High level view of key features

**Installation strategy**

- Binary download
- Package manager

**Configuration strategy**

- Structured config file
- Loaded resource or binary (from code to fonts)
- Plugins
  - Load binary
  - Plugin manager
- Server pull
  - Local server
  - Remote server

**Configuration types**

- Visual
  - Theme
  - Fonts
- Details
  - Which details to show or hide
- Functional

---

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

---

## Application examples

### Terminal apps
+/- Ghostty (by Hashicorp)
+/- Wezterm

### Terminal multiplexer
+ Tmux

### Shells
+ Nushell (powerful for data structures)
+ ZSH

### Editors
+/- Vim/Neovim

### Prompter
+ P9k
+ P10k
+ Starship
+ Pure
+ Polyglot
+ Roundy

### Resources
+ [Nerd Fonts](nerdfonts.com)
