# Aura

Aura is a local-first AI desktop application from Multi AI Tech. A Leader agent coordinates a roster of specialist agents, and every role can run on an API model, a local model, or an external coding harness. Settings, credentials and chat history stay on the machine inside `AuraData/`.

## Three differentiators

1. **Team coordination** - a Leader orchestrates specialist roles (Coder, Reviewer, Security, Tester, Documentation) with configurable models per role.
2. **API, Local or Harness** - you are never locked to one vendor. Use your own API key, a model running on your machine, or a coding agent you already installed.
3. **Assembled from bricks** - modes, roles, pipelines, MCP connections, skills, modules and schedules are attached and detached by you, not fixed by the vendor.

## Membership Tiers & Delta Credit (MAIC)

| Tier | Price | Mandatory Lesson Learned | Delta Credit |
|------|-------|--------------------------|--------------|
| Free | Free forever | ✅ Yes | ❌ No |
| Pro | $5/month or $50/year | ✅ Yes | ✅ Yes |
| Advance | $10/month or $100/year | ❌ Optional | ✅ Only if contributing LL |

### Delta Credit Accumulation & Release

**Accumulation:** Delta Credits are collected during membership period.

**Release trigger:** When 200 Pro/Advance annual members are reached, token release begins.

**Dynamic daily rate:** `accumulated_credits ÷ accumulation_days` per member.

**Example:** 10M credits over 20 days = 500k/day per user during distribution.

### Tier change behavior

- **Paid → Free:** Delta Credit balance resets to 0, accumulation backlog zeroed.
- **Free → Paid:** Balance stays 0, only new Lesson Learned generates Delta Credit.
- **Re-upgrade:** Only post-return contributions earn Delta Credit.

## Quick start

```bash
git clone https://github.com/multiaitech/aura
cd aura
npm install
npm start
```

## Models

Aura ships with sensible defaults for every role. Bring your own keys or run local models via Ollama, llama.cpp, or your preferred harness.

## Features

- Multi-agent orchestration with configurable pipelines
- In-app browser for interactive workflows
- Credential vault and checkpoint/rollback
- Module system for recurring tasks
- Telegram remote control built-in

## Reference

- [MAIC Token & Economics](https://github.com/multiaitech/maic/blob/main/MAIC.md)
- [Owner Checklist](https://github.com/multiaitech/maic/blob/main/Owner.txt)
- [Upload Procedure](https://github.com/multiaitech/maic/blob/main/upload-web.txt)

## Proprietary

Aura core, installer, and the permission gate are closed source. User packages run in a sandboxed extension container.
