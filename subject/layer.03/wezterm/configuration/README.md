# README

---

## Concepts

1) [Directory Structure](./concepts/directory-layout.md)
2) [Behavior](./concepts/behavior.md)
3) [First Pass](./concepts/first-pass.md)
4) [Modular architecture](./concepts/modular-structure.md)
5) [Design Philosophy](./concepts/design-philosophy.md)

---

## Components

1) [Root loader](./components/root-loader.md)
2) [Appearance](./components/appearance.md)
3) [Tmux likeness](./components/tmux-likeness.md)
4) [Status bar](./components/status-bar)
5) [Tab Formatting](./components/tab-formatting.md)
6) [Startup layout](./components/startup-layout.md)
7) [Project workspaces](./components/project-wkspaces.md)
8) [CWD based layout](./components/cwd-layout.md)
9) [Workspace switcher](./components/wkspace-switcher.md)
6) [Git status bar](./components/git-status-bar.md)

---

## 🚀 Next-Level Additions (later)

* Git branch caching
* Battery / CPU display
* Dynamic per-repo layout
* SSH-aware status
* Workspace switcher keymaps
* tmux session importer
* per-repo commands (`package.json` aware)
* ssh workspace launcher
* project discovery via `git rev-parse --show-toplevel`
* Session persistence

---

## 🧠 Architectural Definitions

| Feature            | Architectural Meaning  |
| ------------------ | ---------------------- |
| cwd layouts        | topology orchestration |
| workspace launcher | navigation plane       |
| git status         | telemetry layer        |
| cache              | performance discipline |

---

## Brief Summary

WezTerm becomes:

* A control plane
* Not just a terminal

Your layout can map to:

* build
* logs
* deploy
* shell
* monitor

Automatically.
