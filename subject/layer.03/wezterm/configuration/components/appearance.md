# 2️⃣ Appearance (macOS tuned) — `appearance.lua`

```lua
local wezterm = require "wezterm"

local M = {}

function M.apply(config)
  config.font = wezterm.font_with_fallback {
    "JetBrains Mono",
    "SF Mono",
  }

  config.font_size = 13.5
  config.line_height = 1.1

  config.color_scheme = "Catppuccin Mocha"

  config.window_decorations = "RESIZE"
  config.native_macos_fullscreen_mode = true

  config.enable_tab_bar = true
  config.use_fancy_tab_bar = false
  config.tab_bar_at_bottom = false

  config.window_padding = {
    left = 6,
    right = 6,
    top = 6,
    bottom = 4,
  }
end

return M
```

macOS-specific bits:

* Retina sizing
* native fullscreen
* CMD friendliness
* tighter padding for density

---
