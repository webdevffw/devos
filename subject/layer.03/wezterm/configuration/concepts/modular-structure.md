# 3️⃣ Modular macOS-Focused Architecture

Now let’s tie it to a modular macOS config.

---

## ✅ Target structure

On macOS:

```text
~/.config/wezterm/
  ├── wezterm.lua
  ├── appearance.lua
  ├── keys.lua
  ├── status.lua
  ├── tabs.lua
  ├── workspaces.lua
  ├── layout.lua
  └── utils.lua
```

Each file owns a concern:

| File           | Responsibility                  |
| -------------- | ------------------------------- |
| appearance.lua | fonts, colors, spacing          |
| keys.lua       | leader, keymaps, modal behavior |
| status.lua     | info bar: cwd, git, host, time  |
| tabs.lua       | tab titles, formatting          |
| workspaces.lua | named workspaces                |
| layout.lua     | startup topology                |
| utils.lua      | helpers, caching, shell calls   |

This prevents the “1,200-line wezterm.lua” problem.

---

## ✅ macOS-specific concerns

On macOS you care about:

* `CMD` key usage
* Retina font sizing
* window decorations
* fullscreen behavior
* native tab bar integration

Examples:

```lua
config.window_decorations = "RESIZE"
config.native_macos_fullscreen_mode = true
config.send_composed_key_when_left_alt_is_pressed = true
```

You also often mix:

* `CMD` for OS-native things
* `leader` for workspace actions
