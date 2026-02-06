# 3️⃣ Git Branch in Status Bar (Cached)

Important rule:

> Never spawn `git` every frame.

We cache results and update occasionally.

---

## ✅ Upgrade `status.lua`

```lua
local wezterm = require "wezterm"

local M = {}

local git_cache = {}
local last_update = 0

local function get_git_branch(cwd)
  local now = os.time()
  if git_cache[cwd] and (now - last_update) < 5 then
    return git_cache[cwd]
  end

  local success, stdout = wezterm.run_child_process {
    "bash",
    "-lc",
    "cd " .. cwd .. " 2>/dev/null && git rev-parse --abbrev-ref HEAD 2>/dev/null"
  }

  if success and stdout then
    stdout = stdout:gsub("\n", "")
    git_cache[cwd] = stdout ~= "" and stdout or nil
    last_update = now
  end

  return git_cache[cwd]
end

function M.setup()
  wezterm.on("update-right-status", function(window, pane)
    local cwd_uri = pane:get_current_working_dir()
    local cwd = cwd_uri and cwd_uri.path or ""

    local hostname = wezterm.hostname()
    local workspace = window:active_workspace()
    local zoom = pane:is_zoomed() and " Z " or ""
    local time = wezterm.strftime "%H:%M"

    local branch = get_git_branch(cwd)
    local git = branch and ("  " .. branch) or ""

    window:set_right_status(string.format(
      " WS:%s | %s | %s%s%s | %s ",
      workspace,
      hostname,
      cwd:gsub("file://", ""),
      git,
      zoom,
      time
    ))
  end)
end

return M
```

Now you get:

```
WS:api | macbook | ~/projects/api  main Z | 23:41
```

Dense, fast, and safe.
