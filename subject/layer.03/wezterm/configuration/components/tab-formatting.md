# 5️⃣ Tab Formatting — `tabs.lua`

```lua
local wezterm = require "wezterm"

local M = {}

function M.apply(config)
  wezterm.on("format-tab-title", function(tab)
    local pane = tab.active_pane
    local cwd = pane:get_current_working_dir()
    local title = cwd and cwd.path or tab.active_pane.title

    title = title:gsub("file://", "")
    title = title:match("([^/]+)$") or title

    local zoom = pane:is_zoomed() and " Z" or ""

    return {
      { Text = string.format(" [%d] %s%s ", tab.tab_index + 1, title, zoom) },
    }
  end)
end

return M
```

Result:

```
[1] api-server Z
[2] logs
[3] shell
```

Dense but readable.
