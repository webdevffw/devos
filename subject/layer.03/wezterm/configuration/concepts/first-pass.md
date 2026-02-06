# 2️⃣ What is a “first-pass layout config”?

When you configure WezTerm, there are two layers:

### Layer A — Appearance & behavior

Fonts, colors, keybinds, status bar, tabs, spacing.

### Layer B — Workspace & layout

What happens when WezTerm launches:

* How many windows?
* How many tabs?
* How many panes?
* What commands run?
* Which workspace is active?

A **first-pass layout config** is:

> Your *default workspace topology* at startup.

Instead of opening an empty terminal, you get a structured environment.

---

## ✅ Example idea of a layout

When you start WezTerm:

```
┌──────────────┬──────────────┐
│  editor      │   server     │
│              │              │
├──────────────┴──────────────┤
│            logs             │
└─────────────────────────────┘
```

Or:

* Tab 1 → project shell
* Tab 2 → git / tooling
* Tab 3 → monitoring

Automatically.

---

## ✅ WezTerm supports this via `mux`

Example concept:

```lua
wezterm.on("gui-startup", function(cmd)
  local tab, pane, window = wezterm.mux.spawn_window({})
  pane:split{ direction="Right" }
  pane:split{ direction="Bottom" }
end)
```

So a first-pass layout means:

* You design your default working shape.
* WezTerm becomes a workspace launcher.

---

## ✅ Why it matters for information density

Information density is not only text on screen, but:

* Multiple live processes
* Visible status
* Context per pane
* Predictable layout

If you don’t define layout, every session starts blank.
