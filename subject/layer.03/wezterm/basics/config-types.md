# WezTerm Configuration Types

---

## 🎨 Visual

### Themes

```lua
config.color_scheme = "Catppuccin Mocha"
```

List schemes:

```bash
wezterm ls-colors
```

### Fonts

```lua
config.font = wezterm.font_with_fallback {
  "JetBrains Mono",
  "Fira Code",
}

config.font_size = 13.0
```

### Colors

Override:

```lua
config.colors = {
  tab_bar = {
    background = "#1e1e2e",
  },
}
```

---

## ℹ️ Informational

WezTerm supports a **status bar API**.

Example:

```lua
wezterm.on("update-right-status", function(window, pane)
  local cwd = pane:get_current_working_dir()
  window:set_right_status(" " .. cwd.path .. " ")
end)
```

You can show:

* cwd
* hostname
* time
* git branch
* battery
* workspace
* zoom state

Density is controlled by what you render.

---

## ⚙️ Functional

### Keybindings

```lua
config.keys = {
  { key = "t", mods = "CMD", action = wezterm.action.SpawnTab("CurrentPaneDomain") },
  { key = "w", mods = "CMD", action = wezterm.action.CloseCurrentTab { confirm = true } },
}
```

You can also do modal behavior, leader keys, tmux-like configs.

Example:

```lua
config.leader = { key = "a", mods = "CTRL", timeout_milliseconds = 1000 }
```

### Behavior flags

Examples:

```lua
config.scrollback_lines = 5000
config.enable_tab_bar = true
config.use_fancy_tab_bar = false
config.window_decorations = "RESIZE"
```

### Automation hooks

Events:

```lua
wezterm.on("gui-startup", function(cmd)
  wezterm.mux.spawn_window(cmd or {})
end)
```

Hooks include:

* startup
* tab-title-format
* update-status
* format-tab-title

This is where WezTerm becomes a programmable workspace.
