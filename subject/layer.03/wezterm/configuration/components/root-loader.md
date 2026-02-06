# 1️⃣ Root Loader — `wezterm.lua`

```lua
local wezterm = require "wezterm"
local config = wezterm.config_builder()

require("appearance").apply(config)
require("keys").apply(config)
require("tabs").apply(config)
require("layout").setup()
require("status").setup()

return config
```

This file stays small and clean.
