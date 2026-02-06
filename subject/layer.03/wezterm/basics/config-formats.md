## 1️⃣ Configuration format(s)

---

### ✅ Structured config

WezTerm uses **Lua** exclusively.

* Main entry point:

```text
~/.wezterm.lua
```

* It is:

  * Declarative (`config.color_scheme = ...`)
  * Imperative (`wezterm.on("event", fn)`)

So it’s both:

* **Structured config**
* **Imperative scripting**

Example skeleton:

```lua
local wezterm = require 'wezterm'
local config = {}

config.font = wezterm.font("JetBrains Mono")
config.font_size = 13.0
config.color_scheme = "Catppuccin Mocha"

return config
```

---

### ✅ Imperative config

Because it’s Lua, you can:

* Define functions
* Handle events
* Compute values dynamically
* Load modules

Example:

```lua
wezterm.on("update-right-status", function(window, pane)
  window:set_right_status(os.date("%H:%M"))
end)
```

There is **no GUI config editor** for WezTerm. Everything is code.
