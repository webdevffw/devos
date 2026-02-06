# 1️⃣ Automatic Layout Based on CWD (layout by project)

Goal:

> When WezTerm starts (or when you create a workspace), it chooses a layout based on the project path.

We do this by:

* Defining project rules
* Matching cwd
* Applying topology + commands

---

## ✅ Update `layout.lua`

```lua
local wezterm = require "wezterm"
local mux = wezterm.mux
local workspaces = require "workspaces"

local M = {}

local PROJECTS = {
  {
    name = "infra",
    match = "/projects/infra",
    cwd = "/Users/yourname/projects/infra",
  },
  {
    name = "api",
    match = "/projects/api",
    cwd = "/Users/yourname/projects/api",
  },
}

local function detect_project()
  local cwd = wezterm.home_dir
  for _, p in ipairs(PROJECTS) do
    if cwd:find(p.match) then
      return p
    end
  end
end

function M.setup()
  wezterm.on("gui-startup", function(cmd)
    local project = detect_project()

    if project then
      workspaces.launch_project(project.name, project.cwd)
    else
      local tab, pane, window = mux.spawn_window(cmd or {})
      pane:split { direction = "Right", size = 0.5 }
      pane:split { direction = "Bottom", size = 0.3 }
      mux.set_active_workspace "default"
    end
  end)
end

return M
```

Now your terminal **bootstraps itself based on project identity**, not just empty windows.

Later, you can auto-detect from `PWD`, git root, env vars, etc.

---

## ✅ Improve `workspaces.lua`

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

  mux.set_active_workspace(name)
end

return M
```

You now have **layout-as-code**.
