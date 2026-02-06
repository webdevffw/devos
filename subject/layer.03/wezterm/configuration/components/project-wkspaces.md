# 7️⃣ Project Workspaces — `workspaces.lua`

Now the important part: **per-project launch setups**.

Example pattern:

```lua
local wezterm = require "wezterm"
local mux = wezterm.mux

local M = {}

function M.launch_project(name, cwd)
  local tab, pane, window = mux.spawn_window {
    workspace = name,
    cwd = cwd,
  }

  local right = pane:split { direction = "Right", cwd = cwd }
  local bottom = pane:split { direction = "Bottom", cwd = cwd }

  pane:send_text("nvim .\n")
  right:send_text("npm run dev\n")
  bottom:send_text("git status\n")
end

return M
```

You can call this from layout later.

Example usage:

```lua
local ws = require("workspaces")
ws.launch_project("api", "/Users/you/projects/api")
```

This turns WezTerm into a **project launcher**, not just a terminal.
