# 1️⃣ What does “tmux-like behavior” mean in WezTerm?

> Do you want WezTerm to act like a programmable workspace manager, not just a terminal emulator?

`tmux` is a terminal multiplexer. People use it for:

* Splitting panes
* Managing tabs/windows
* Navigating without the mouse
* Persistent sessions
* Leader key workflows

When someone says “tmux-like behavior” in WezTerm, they usually mean:

> Using WezTerm’s native features to replace most of what tmux does.

Not literally running tmux — but copying the **interaction model**.

---

## ✅ Core tmux concepts

| tmux concept       | WezTerm equivalent                 |
| ------------------ | ---------------------------------- |
| Leader key         | `config.leader`                    |
| Split panes        | `SplitHorizontal`, `SplitVertical` |
| Move between panes | `ActivatePaneDirection`            |
| Resize panes       | `AdjustPaneSize`                   |
| Tabs / windows     | `SpawnTab`, `SpawnWindow`          |
| Status bar         | `update-status` hook               |
| Workspaces         | `wezterm.mux` workspaces           |
| Zoom pane          | `TogglePaneZoomState`              |

---

## ✅ What tmux-like feels like

Instead of:

```text
Cmd+T
Cmd+W
Mouse to resize
```

You do:

```text
Ctrl+A, v   -> vertical split
Ctrl+A, s   -> horizontal split
Ctrl+A, h   -> move left
Ctrl+A, l   -> move right
Ctrl+A, z   -> zoom pane
Ctrl+A, c   -> new tab
```

So your terminal becomes **modal and keyboard-driven**.

---

## ✅ Benefits

* Faster navigation
* Less mouse usage
* Predictable layout control
* Same workflow over SSH
* No need for tmux itself

---

## ⚠️ Drawbacks

* More cognitive load
* Conflicts with shell shortcuts
* Takes time to memorize
