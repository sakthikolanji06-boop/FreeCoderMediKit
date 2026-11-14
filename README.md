<div align="center">

# Sakthi AI Kit

**A curated, reproducible bundle of the AI tooling I run locally for LLM apps, agents, routing, and automation.**

</div>

---

## What's inside

| Component | Purpose | Upstream | License |
|---|---|---|---|
| **AIClient2API** | OpenAI/Anthropic-compatible gateway that unifies multiple model providers behind one API | [justlovemaki/AIClient-2-API](https://github.com/justlovemaki/AIClient-2-API) | GPL-3.0 |
| **9Router** | Local AI router / token saver with a dashboard and provider pools | [decolua/9router](https://github.com/decolua/9router) | MIT |
| **scripts/** | Local launcher scripts (`start-claude-local`, `claude-launch`) | — | — |
| **docs/SETUP.md** | Step-by-step local stack setup (no secrets) | — | — |
| **docs/OPENCODE.md** | Install & configure the opencode coding agent | — | — |

## Quick start

```bash
# 1) API gateway
cd AIClient2API
npm install
cp configs/provider_pools.json.example configs/provider_pools.json   # add your own keys
./install-and-run.sh

# 2) Router
cd ../9router
npm install
cp .env.example .env                                                 # add your own keys
npm run dev

# 3) Point your client at the router
export ANTHROPIC_BASE_URL=http://127.0.0.1:20128/v1
```

## Documentation

- `docs/SETUP.md` — run the local AI stack
- `docs/OPENCODE.md` — install and configure opencode

See `docs/SETUP.md` for the full flow.

## Security

This kit contains **no API keys, tokens, databases, or logs**. All sensitive files
(`.env`, `configs/*.json`, `*.db`, `logs/`) are intentionally excluded — configure
your own credentials from the provided `*.example` templates.

## Attribution

Third-party components remain under their original licenses. See `ATTRIBUTION.md`
and the `LICENSE` file inside each component directory.
