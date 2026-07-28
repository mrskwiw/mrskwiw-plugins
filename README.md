# mrskwiw-plugins — a Claude Code plugin marketplace

A single marketplace listing the agent tooling built by **mrskwiw** / **knot0**.
Each plugin lives in its own repository and installs independently.

## Install

```bash
# 1. Add this marketplace (once it's pushed to GitHub)
/plugin marketplace add mrskwiw/mrskwiw-plugins

# 2. Install any plugin from it
/plugin install web-qa@mrskwiw-plugins
/plugin install web-replicate@mrskwiw-plugins
/plugin install claude-novel-writer@mrskwiw-plugins
/plugin install vibe-testing@mrskwiw-plugins
/plugin install repl-scratchpad@mrskwiw-plugins

# Manage
/plugin marketplace update
/plugin marketplace list
```

For **local testing** before pushing, add this directory directly:

```bash
/plugin marketplace add ./marketplace
```

## Plugins

| Plugin | What it does | Source | Status |
|---|---|---|---|
| `web-qa` | AI-assisted web QA — drives real user journeys in a headless browser and judges whether the goal was achieved | `github:mrskwiw/web-qa` | ⚠️ repo not created/pushed yet |
| `web-replicate` | Reconstruction-grade rebuild blueprints for web apps (sibling of web-qa) | `github:mrskwiw/web-replicate` | ⚠️ repo not created/pushed yet |
| `claude-novel-writer` | AI-assisted novel writing — structure, consistency, prose analysis | `git-subdir:mrskwiw/claude-novel-writer/project` | ✅ live |
| `vibe-testing` | Pressure-test specs with LLM reasoning before writing code | `github:knot0-com/vibe-testing` | ⚠️ needs a Claude Code `plugin.json` (see below) |
| `repl-scratchpad` | Persistent REPL for agents — vars survive turns, only `print()` enters context | `github:knot0-com/repl-scratchpad` | ⚠️ needs a Claude Code `plugin.json` (see below) |

## Before this marketplace is fully installable

Three follow-ups, none of which this repo can do on its own:

1. **Push `web-qa` and `web-replicate` to GitHub** as `mrskwiw/web-qa` and
   `mrskwiw/web-replicate` (each a self-contained plugin: `SKILL.md` + vendored
   `engine/` + `requirements.txt` + a `.claude-plugin/plugin.json`). Their marketplace
   entries already point at those repo names.
2. **Push this marketplace** to `github:mrskwiw/mrskwiw-plugins` so
   `/plugin marketplace add mrskwiw/mrskwiw-plugins` resolves.
3. **`vibe-testing` and `repl-scratchpad`** are currently published in a *cross-platform
   skills* format (a root `marketplace.json` with `skills[]` + `compatibility[]`, no
   `.claude-plugin/plugin.json`). To install them as **Claude Code** plugins they need a
   `.claude-plugin/plugin.json` added to their repos (a small PR to each). Until then their
   entries here are listed for discovery but may not `/plugin install` cleanly.

## Notes

- Plugin `name` fields are the stable install identifiers (`name@mrskwiw-plugins`); `displayName` is the UI label.
- `version` in each plugin's own `plugin.json` is authoritative and overrides the value listed here.
- Schema reference: <https://code.claude.com/docs/en/plugin-marketplaces.md>
