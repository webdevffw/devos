## 5️⃣ Remote / centralized config

This fits very well with your engineering workflow.

### ✅ Git-based config

Common approach:

```bash
~/.config/wezterm -> dotfiles repo
```

Then:

* GitHub
* Bare repo
* Stow / chezmoi / yadm

WezTerm works perfectly with dotfile syncing.

### ✅ Server-based config

You *can* fetch remote config dynamically:

```lua
local f = io.popen("curl -s https://example.com/wezterm.lua")
```

But this is usually overkill and risky.

### ✅ Dotfile sync compatibility

WezTerm config is portable and OS-agnostic, so it’s excellent for:

* Mac
* Linux
* WSL
