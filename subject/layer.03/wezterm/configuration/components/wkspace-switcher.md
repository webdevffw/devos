# 2️⃣ Fuzzy Workspace Switcher

WezTerm has a built-in fuzzy launcher, so we wire a key to it.

---

## ✅ Add to `keys.lua`

Inside `config.keys`:

```lua
{ 
  key = "w",
  mods = "LEADER",
  action = wezterm.action.ShowLauncherArgs { flags = "FUZZY|WORKSPACES" }
},
```

Now:

```text
Ctrl+Space w
```

opens a fuzzy workspace picker.

This gives you:

* fast switching
* no manual cycling
* scalable when you have many projects

You can later add:

* tabs
* commands
* ssh hosts

with the same launcher.
