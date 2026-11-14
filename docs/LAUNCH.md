# Launch Playbook

**One-liner:** *Run a full LLM stack — gateway, router, coding agent — in minutes. Free, self-hosted, provider-agnostic.*

**Who it's for:** developers who juggle OpenAI/Anthropic/local models, self-hosters, AI-agent builders, opencode users, and anyone tired of re-wiring API keys per tool.

> Stars can't be bought — they're earned by being genuinely useful to a specific person.
> This playbook maximizes the chance the right person sees it and converts.

---

## Before launch (do all of these first)

- [ ] Social preview set (Settings → Social preview → upload `assets/social-preview.png`)
- [ ] Description + 16 topics set
- [ ] Discussions enabled
- [ ] README opens with the outcome, not the feature list
- [ ] Release `v1.0.0` asset downloads and unzips cleanly
- [ ] `.example` configs exist for every secret
- [ ] Repo pinned on your profile
- [ ] A 30–60s screen recording of `git clone` → working request

## Launch day

Post in this order, 60–90 min apart, and reply to every comment for the first 4 hours.

1. X/Twitter thread
2. LinkedIn
3. Reddit (one subreddit, not three at once)
4. Hacker News (Show HN)
5. Dev.to cross-post

---

## X / Twitter thread

**1/**
Most AI setups break the moment you switch providers.

Keys in five places. Five different APIs. Nothing reproducible.

I packaged the whole stack into one repo — free, self-hosted, secret-free.

FreeCoder MediKit 🧵

**2/**
The problem:

→ OpenAI-compatible here, Anthropic-compatible there
→ Every tool wants its own key
→ Your "local setup" is 12 undocumented steps

**3/**
The fix — one bundle, three layers:

🔌 AIClient2API — one API for any provider
🧭 9Router — routing + token savings
⌨️ opencode — coding agent wired to it

All behind `http://127.0.0.1:20128/v1`.

**4/**
```bash
git clone https://github.com/sakthikolanji06-boop/FreeCoderMediKit
cd FreeCoderMediKit && ./scripts/start-claude-local services
```

Copy the example configs → add your key → run.

**5/**
Security was non-negotiable:

❌ no keys
❌ no databases
❌ no logs

Everything sensitive is excluded by default and documented in `SECURITY.md`.

**6/**
It's free and MIT-friendly to build on (third-party components keep their licenses).

If this saves you a weekend, a ⭐ helps other developers find it:

https://github.com/sakthikolanji06-boop/FreeCoderMediKit

---

## LinkedIn

> **I got tired of re-wiring my AI stack every time I changed a model provider. So I packaged it.**
>
> FreeCoder MediKit is a free, self-hosted, reproducible bundle of the tooling I use for LLM apps and agents:
> • a gateway that speaks OpenAI *and* Anthropic
> • a local router for provider routing and token savings
> • a coding agent wired to both
>
> It ships with **no keys, no databases, no logs** — you add your own credentials from `.example` templates.
>
> Clone it, add a key, and you have a working stack in minutes:
> https://github.com/sakthikolanji06-boop/FreeCoderMediKit
>
> Feedback and PRs welcome. What would you add next?

---

## Reddit

### r/LocalLLaMA
**Title:** I packaged my local LLM stack (gateway + router + coding agent) into one reproducible, secret-free repo

Body: short version of the README, emphasize self-hosted + provider-agnostic + no secrets. Ask what provider they want supported next. Reply with real details, no marketing tone.

### r/selfhosted
**Title:** FreeCoder MediKit – self-hosted LLM gateway + router + agent, secret-free by default

### r/SideProject
**Title:** I built a toolkit to stop re-wiring my AI stack for every provider

---

## Hacker News (Show HN)

**Title:** Show HN: FreeCoder MediKit – a reproducible, secret-free LLM stack

**First comment:**
> Author here. I kept rebuilding the same stack: a gateway that normalizes OpenAI and Anthropic APIs, a router for provider choice and token savings, and a coding agent on top.
>
> The bundle is deliberately boring and reproducible: pinned components, `.example` configs, no secrets, no state. Clone, add a key, run.
>
> I'd love feedback on the launcher scripts and on which providers to add first. Happy to answer anything about the architecture.

---

## Product Hunt

**Tagline:** Run a full LLM stack in minutes — free and self-hosted
**Description:** A curated bundle of a provider-agnostic AI gateway, a local router, and a coding agent — wired together, secret-free, and reproducible.

---

## Dev.to

**Title:** Stop re-wiring your AI stack: one reproducible bundle for any model
Use the README's Why + Quick start sections, add a screenshot of the architecture SVG.

---

## Hashtags

`#AI #LLM #OpenSource #SelfHosted #DevTools #LLMOps #opencode #Agents`

---

## After launch

- Reply to every issue/comment within 24h
- Ship one visible improvement per week (roadmap items)
- Add "Used by" / testimonials only when real
- Re-post on relevant subreddits only with a real update, not the same link
