# 3️⃣ tmux-like Keys — `keys.lua`

Leader = `Ctrl+Space`.

```lua
local wezterm = require "wezterm"
local act = wezterm.action

local M = {}

function M.apply(config)
  config.leader = {
    key = "Space",
    mods = "CTRL",
    timeout_milliseconds = 1000,
  }

  config.keys = {
    -- splits
    { key = "v", mods = "LEADER", action = act.SplitHorizontal { domain = "CurrentPaneDomain" } },
    { key = "s", mods = "LEADER", action = act.SplitVertical { domain = "CurrentPaneDomain" } },

    -- navigation
    { key = "h", mods = "LEADER", action = act.ActivatePaneDirection "Left" },
    { key = "j", mods = "LEADER", action = act.ActivatePaneDirection "Down" },
    { key = "k", mods = "LEADER", action = act.ActivatePaneDirection "Up" },
    { key = "l", mods = "LEADER", action = act.ActivatePaneDirection "Right" },

    -- resize
    { key = "H", mods = "LEADER|SHIFT", action = act.AdjustPaneSize { "Left", 5 } },
    { key = "J", mods = "LEADER|SHIFT", action = act.AdjustPaneSize { "Down", 5 } },
    { key = "K", mods = "LEADER|SHIFT", action = act.AdjustPaneSize { "Up", 5 } },
    { key = "L", mods = "LEADER|SHIFT", action = act.AdjustPaneSize { "Right", 5 } },

    -- tabs
    { key = "c", mods = "LEADER", action = act.SpawnTab "CurrentPaneDomain" },
    { key = "x", mods = "LEADER", action = act.CloseCurrentPane { confirm = true } },

    -- zoom
    { key = "z", mods = "LEADER", action = act.TogglePaneZoomState },

    -- reload
    { key = "r", mods = "LEADER", action = act.ReloadConfiguration },
  }
end

return M
```

This mirrors tmux muscle memory.
