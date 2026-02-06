## 4️⃣ Extensibility

### ✅ Plugins (WezTerm style)

WezTerm doesn’t have a classic plugin manager like Neovim, but it supports:

* GitHub module loading
* Lua modules
* Event hooks

Example:

```lua
local wezterm = require 'wezterm'
local bar = wezterm.plugin.require("https://github.com/username/wezterm-status")
```

Or local modules:

```lua
local tabs = require("tabs")
```

Plugin format = **Lua modules**.

No central plugin manager, but people use:

* Git submodules
* dotfile repos
* manual git clone

### ✅ External binaries

WezTerm integrates with:

* `ssh`
* `tmux`
* shell scripts
* OS commands via Lua

Example:

```lua
wezterm.run_child_process({"bash", "-lc", "hostname"})
```

So automation hooks can talk to your system easily.
