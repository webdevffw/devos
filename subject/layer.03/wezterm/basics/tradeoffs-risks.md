# Tradeoffs & Risks

---

## 🔒 Lock-in

* You write Lua for WezTerm only.
* Not portable to Alacritty / Kitty.

Mitigation:

* Keep logic isolated (appearance.lua, keys.lua).

---

## 🧠 Complexity

* Lua gives power, but configs can become real programs.
* Debugging mistakes can break startup.

Mitigation:

* Modularize.
* Use `wezterm.log_info(...)`.

---

## ⚡ Performance

* Lua is fast.
* Status updates every frame can hurt performance if you run shell commands.

Mitigation:

* Cache expensive calls.
* Avoid spawning processes on every status tick.

Bad:

```lua
io.popen("git branch")
```

Good:

* Cache results
* Update on interval

---

## 🛠 Maintenance burden

* Plugins are unmanaged.
* GitHub modules can break.

Mitigation:

* Vendor critical modules.
* Pin versions in dotfiles.
