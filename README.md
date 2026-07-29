# mrskwiw-plugins — a Claude Code plugin marketplace

A single marketplace listing the agent tooling built by **mrskwiw** / **knot0**.
Each plugin lives in its own repository and installs independently.

## Install

```bash
# 1. Add this marketplace
/plugin marketplace add mrskwiw/mrskwiw-plugins

# 2. Install any plugin from it
/plugin install web-qa@mrskwiw-plugins
/plugin install web-replicate@mrskwiw-plugins
/plugin install claude-novel-writer@mrskwiw-plugins

# Manage
/plugin marketplace update
/plugin marketplace list
```

For **local testing**, add a checkout of this repo directly:

```bash
/plugin marketplace add ./mrskwiw-plugins
```

## Plugins

| Plugin | What it does | Source |
|---|---|---|
| `web-qa` | AI-assisted web QA — drives real user journeys in a headless browser and judges whether the goal was achieved | `github:mrskwiw/web-qa` |
| `web-replicate` | Reconstruction-grade rebuild blueprints for web apps (sibling of web-qa) | `github:mrskwiw/web-replicate` |
| `claude-novel-writer` | AI-assisted novel writing — structure, consistency, prose analysis | `git-subdir:mrskwiw/claude-novel-writer/project` |

All three are live and install cleanly.

## Related projects (not Claude Code plugins)

These are published as **cross-platform agent skills** (root `SKILL.md`, no
`.claude-plugin/plugin.json`), so they aren't listed as installable plugins here —
install them via their own repos:

- [`knot0-com/vibe-testing`](https://github.com/knot0-com/vibe-testing) — pressure-test specs with LLM reasoning before writing code.
- [`knot0-com/repl-scratchpad`](https://github.com/knot0-com/repl-scratchpad) — persistent REPL for agents; variables survive turns, only `print()` enters context.

## Notes

- Plugin `name` fields are the stable install identifiers (`name@mrskwiw-plugins`); `displayName` is the UI label.
- `version` in each plugin's own `plugin.json` is authoritative and overrides the value listed here.
- Schema reference: <https://code.claude.com/docs/en/plugin-marketplaces.md>
