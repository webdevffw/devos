# Individual Tool Research Template

```md
## Purpose
- What problem does this tool solve?
- Which layer does it belong to?
- What pain does it eliminate or reduce?

## Core Responsibilities
- Primary function(s)
- Secondary / emergent capabilities
- What it explicitly does *not* handle

## Key Features
- Differentiating features
- Automation friendliness
- Extensibility
- Performance characteristics

## Installation Strategy
- Supported platforms (macOS, Linux, Windows)
- Installation methods
  - Package manager (brew, apt, nix, pacman, etc.)
  - Binary download
  - Source build
- CI / headless install friendliness
  - Paths & persmissions (sudo?)

## Configuration Strategy
- Configuration format(s)
  - Structured config (TOML, YAML, JSON, Lua, etc.)
  - Imperative config (scripts)
- Reload behavior
  - Hot reload
  - Restart required
- State location
  - Single file
  - Directory-based
- Extensibility
  - Plugins
    - Plugin format
    - Plugin manager
  - External binaries
- Remote or centralized config
  - Git pull
  - Server-based config
  - Dotfile sync compatibility

## Configuration Types
- Visual
  - Themes
  - Fonts
  - Colors
- Informational
  - What metadata is shown
  - Density / verbosity
- Functional
  - Keybindings
  - Behavior flags
  - Automation hooks

## Ecosystem & Maturity
- Community size
- Maintenance activity
- Documentation quality
- Backward compatibility

## Tradeoffs & Risks
- Lock-in
- Complexity
- Performance
- Maintenance burden

## Ideal Use Cases
- Solo developer
- Team-wide standardization
- Remote / ephemeral environments

## Known Resources
- Official docs
- Community configs
- Related tooling
```
