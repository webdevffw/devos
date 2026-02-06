# 6️⃣ Project Startup Layout — `layout.lua`

This is your **first-pass layout config**.

```lua
local wezterm = require "wezterm"
local mux = wezterm.mux

local M = {}

function M.setup()
  wezterm.on("gui-startup", function(cmd)
    local tab, pane, window = mux.spawn_window(cmd or {})

    pane:split { direction = "Right", size = 0.5 }
    pane:split { direction = "Bottom", size = 0.3 }

    mux.set_active_workspace "default"
  end)
end

return M
```

This creates a useful base topology every time.
