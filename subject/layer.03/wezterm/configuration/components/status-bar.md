# 4️⃣ Dense Status Bar — `status.lua`

We show:

* workspace
* host
* cwd
* git branch
* zoom
* time

```lua
local wezterm = require "wezterm"

local M = {}

function M.setup()
  wezterm.on("update-right-status", function(window, pane)
    local cwd = pane:get_current_working_dir()
    cwd = cwd and cwd.path or ""

    local hostname = wezterm.hostname()
    local workspace = window:active_workspace()

    local zoom = pane:is_zoomed() and " Z " or ""

    local time = wezterm.strftime "%H:%M"

    window:set_right_status(string.format(
      " WS:%s | %s | %s%s | %s ",
      workspace,
      hostname,
      cwd:gsub("file://", ""),
      zoom,
      time
    ))
  end)
end

return M
```

Later you can inject git via caching (not spawning every tick).
