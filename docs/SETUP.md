# Local AI Stack — Setup

This guide recreates the local stack used for LLM app development and Claude-compatible tooling.
It contains no credentials.

## Requirements

- Node.js 18+ and npm
- Linux (tested on Ubuntu/Debian-based)
- Outbound HTTPS to your model providers

## 1. AIClient2API (gateway, port 3000)

```bash
cd AIClient2API
npm install
cp configs/provider_pools.json.example configs/provider_pools.json
# edit configs/provider_pools.json and add your provider keys
./install-and-run.sh
curl -s http://127.0.0.1:3000/health
```

## 2. 9Router (router, port 20128)

```bash
cd 9router
npm install
cp .env.example .env
# edit .env with your keys
npm run dev
curl -s http://127.0.0.1:20128/api/health
```

## 3. Point a client at the router

```bash
export ANTHROPIC_BASE_URL=http://127.0.0.1:20128/v1
export ANTHROPIC_MODEL=claude-sonnet-5
```

## 4. Launcher scripts

`scripts/start-claude-local` starts both services and can check health:

```bash
./scripts/start-claude-local services
./scripts/start-claude-local check
```

`scripts/claude-launch` opens a terminal with Claude Code against the local router.

## Troubleshooting

- Port already in use: `ss -ltnp | grep -E '3000|20128'`
- Service not healthy: check `AIClient2API/logs/` and the router console output
- Keys rejected: verify the provider entry in `provider_pools.json` / `.env`
