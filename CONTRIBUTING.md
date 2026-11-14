# Contributing to FreeCoder MediKit

Thanks for helping! This project packages a working local AI stack, so improvements
that keep it **reproducible** and **secret-free** are especially welcome.

## Ways to help

- 🐛 Report bugs with reproduction steps
- 📖 Improve docs (`docs/`)
- 🔌 Add provider examples to the `*.example` configs
- 🧪 Add smoke tests for the launcher scripts
- ⭐ Star the repo and share it

## Ground rules

- **Never commit secrets** — no keys, tokens, `.env`, databases, or logs.
- Keep changes focused; one concern per PR.
- Match existing formatting and naming.
- Update docs when behavior changes.

## Pull request flow

1. Fork and create a branch: `feat/<short-name>` or `fix/<short-name>`
2. Make the change and test the scripts you touched
3. Open a PR describing **what** and **why**
4. Link any related issue

## Development check

```bash
./scripts/start-claude-local check
```

By contributing you agree to follow the [Code of Conduct](CODE_OF_CONDUCT.md).
