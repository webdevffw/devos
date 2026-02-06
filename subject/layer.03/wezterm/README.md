# WezTerm Configuration Strategy

Set up a **production-grade first-pass WezTerm architecture** with extensibility.

> 🧠 Not just a shell window, but a programmable 
> **workspace manager/orchestrator**
> **runtime system**
> **full control plane**

WezTerm is *very* configurable, but it’s also different from most terminals because the configuration is actually a **Lua program**, not just a static file. That gives you power, but it also means you want a clean strategy instead of dumping everything into one file.

Allows for the following options and much more:

✅ Modular skeleton
✅ tmux-like leader UX
✅ Information-dense status bar
✅ Smart tab titles
✅ Startup topology
✅ Project-aware workspaces
✅ macOS-optimized
✅ JetBrains Mono
✅ automatic layout by CWD
✅ fuzzy workspace switcher
✅ git branch in status bar

---

## Basics

Learn the basics of the WezTerm configuration strategy:

1) [Config formats](./basics/config-formats.md)
2) [Reload behavior](./basics/reload-behavior.md)
3) [State location](./basics/state-location.md)
4) [Extensibility](./basics/extensibility.md)
5) [Remote config](./basics/remote-config.md)
6) [Config types](./basics/config-types.md)
7) [Tradeoffs](./basics/tradeoffs-risks.md)

For the direct implementation strategy, check out the [configuration README](./configuration/README.md)
