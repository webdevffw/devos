## 3️⃣ State location

### ✅ Single file by default

```text
~/.wezterm.lua
```

### ✅ Directory-based (recommended)

You can split your config:

```text
~/.config/wezterm/
  ├── wezterm.lua
  ├── appearance.lua
  ├── keys.lua
  ├── status.lua
  ├── tabs.lua
  └── utils.lua
```

And in `wezterm.lua`:

```lua
local wezterm = require 'wezterm'
local config = {}

require("appearance").apply(config)
require("keys").apply(config)
require("status").setup()

return config
```

This scales well once you start doing real customization.

👉 This matches how you already structure tooling projects.
