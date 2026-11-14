<div align="center">

<img src="https://raw.githubusercontent.com/sakthikolanji06-boop/FreeCoderMediKit/main/assets/banner.svg" alt="FreeCoder MediKit" width="100%" />

### Run a full LLM stack in minutes — no API juggling, no vendor lock-in.

[![Stars](https://img.shields.io/github/stars/sakthikolanji06-boop/FreeCoderMediKit?style=for-the-badge&color=22d3ee&label=stars)](https://github.com/sakthikolanji06-boop/FreeCoderMediKit/stargazers)
[![Release](https://img.shields.io/github/v/release/sakthikolanji06-boop/FreeCoderMediKit?style=for-the-badge&color=8b5cf6&label=release)](https://github.com/sakthikolanji06-boop/FreeCoderMediKit/releases)
[![Downloads](https://img.shields.io/github/downloads/sakthikolanji06-boop/FreeCoderMediKit/total?style=for-the-badge&color=f0abfc&label=downloads)](https://github.com/sakthikolanji06-boop/FreeCoderMediKit/releases)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-34d399?style=for-the-badge)](CONTRIBUTING.md)

**One bundle. Three layers. Any model.**
Gateway + router + coding agent — wired together, secret-free, reproducible.

</div>

---

## Why FreeCoder MediKit?

Most AI setups break the moment you change providers. Keys live in five places,
every tool speaks a different API, and nothing is reproducible.

**FreeCoder MediKit fixes that:**

- 🔌 **One API surface** — OpenAI *and* Anthropic compatible
- 🧭 **Provider-agnostic** — route to any model, swap without rewriting code
- 🧰 **Batteries included** — gateway, router, launcher scripts, and docs
- 🔒 **Secret-free by design** — no keys, DBs, or logs in the bundle
- ⚡ **Minutes, not weekends** — copy the `*.example` configs, add your key, run

## Features

<div align="center">
<img src="https://raw.githubusercontent.com/sakthikolanji06-boop/FreeCoderMediKit/main/assets/features.svg" alt="Features" width="100%" />
</div>

## One command to start

```bash
git clone https://github.com/sakthikolanji06-boop/FreeCoderMediKit.git
cd FreeCoderMediKit && ./scripts/start-claude-local services
```

Then point any client at `http://127.0.0.1:20128/v1`.

## Architecture

<div align="center">
<img src="https://raw.githubusercontent.com/sakthikolanji06-boop/FreeCoderMediKit/main/assets/architecture.svg" alt="Architecture" width="100%" />
</div>

## What's inside

| Component | Purpose | Upstream | License |
|---|---|---|---|
| **AIClient2API** | OpenAI/Anthropic-compatible gateway that unifies model providers behind one API | [justlovemaki/AIClient-2-API](https://github.com/justlovemaki/AIClient-2-API) | GPL-3.0 |
| **9Router** | Local AI router / token saver with dashboard and provider pools | [decolua/9router](https://github.com/decolua/9router) | MIT |
| **scripts/** | `start-claude-local`, `claude-launch` | — | — |
| **docs/SETUP.md** | Step-by-step local stack setup | — | — |
| **docs/OPENCODE.md** | Install & configure opencode | — | — |

## Quick start (manual)

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
export ANTHROPIC_MODEL=claude-sonnet-5
```

## Documentation

| Guide | Description |
|---|---|
| [docs/SETUP.md](docs/SETUP.md) | Run the local AI stack end to end |
| [docs/OPENCODE.md](docs/OPENCODE.md) | Install & configure the opencode coding agent |
| [ROADMAP.md](ROADMAP.md) | What's next |
| [CONTRIBUTING.md](CONTRIBUTING.md) | How to help |

## Security

This kit contains **no API keys, tokens, databases, or logs**. All sensitive files
(`.env`, `configs/*.json`, `*.db`, `logs/`) are intentionally excluded — configure
your own credentials from the provided `*.example` templates.

## Star history

<div align="center">
<a href="https://star-history.com/#sakthikolanji06-boop/FreeCoderMediKit&Date">
  <img src="https://api.star-history.com/svg?repos=sakthikolanji06-boop/FreeCoderMediKit&type=Date" alt="Star history" width="80%" />
</a>
</div>

---

<div align="center">

**If this saved you a weekend, drop a ⭐ — it helps others find it.**

<a href="https://github.com/sakthikolanji06-boop/FreeCoderMediKit/stargazers">
  <img src="https://img.shields.io/badge/⭐_Star_this_repo-22d3ee?style=for-the-badge" alt="Star this repo" />
</a>

</div>

## Attribution

Third-party components remain under their original licenses. See
[ATTRIBUTION.md](ATTRIBUTION.md) and the `LICENSE` file inside each component directory.
