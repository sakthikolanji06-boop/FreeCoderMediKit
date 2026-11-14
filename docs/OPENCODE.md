# opencode — Install & Configure

[opencode](https://opencode.ai) is an open-source, terminal-based AI coding agent.
This guide installs it and points it at the local router from this kit.

## Requirements

- Node.js 18+ (for the npm install path)
- A running local router (`http://127.0.0.1:20128/v1`) or any OpenAI-compatible endpoint

## 1. Install

**Option A — install script (recommended)**

```bash
curl -fsSL https://opencode.ai/install | bash
```

**Option B — npm**

```bash
npm install -g opencode-ai
```

**Option C — package managers**

```bash
brew install sst/tap/opencode     # macOS / Linuxbrew
```

## 2. Verify

```bash
opencode --version
```

## 3. Configure a provider

Config lives at `~/.config/opencode/opencode.jsonc`.

```jsonc
{
  "$schema": "https://opencode.ai/config.json",
  "provider": {
    "local-router": {
      "npm": "@ai-sdk/openai-compatible",
      "name": "Local Router",
      "options": {
        "baseURL": "http://127.0.0.1:20128/v1"
      },
      "models": {
        "claude-sonnet-5": { "name": "Claude Sonnet 5" },
        "claude-opus-5":   { "name": "Claude Opus 5" },
        "claude-haiku-4-5":{ "name": "Claude Haiku 4.5" }
      }
    }
  },
  "model": "local-router/claude-sonnet-5"
}
```

For hosted providers, authenticate once:

```bash
opencode auth login
```

## 4. Add an MCP server (optional)

MCP servers extend opencode with tools. Example — the REA analysis server:

```jsonc
{
  "mcp": {
    "rea": {
      "type": "local",
      "command": ["npx", "-y", "rea-agents@6.8.0", "mcp"],
      "enabled": true
    }
  }
}
```

## 5. Run

```bash
opencode                        # interactive TUI
opencode run "explain this repo" # one-shot
opencode --model local-router/claude-opus-5
```

## Troubleshooting

| Symptom | Fix |
|---|---|
| Config ignored | Confirm the file is `~/.config/opencode/opencode.jsonc` and valid JSONC |
| Model / connection error | Check the `baseURL` and that the router is healthy: `curl -s http://127.0.0.1:20128/api/health` |
| Auth errors | Run `opencode auth login` and re-select the provider |
| Inspect logs | See `~/.local/share/opencode/log/` |

## Reference

- Docs: https://opencode.ai/docs
- Config schema: https://opencode.ai/config.json
