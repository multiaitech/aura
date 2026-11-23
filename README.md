# Aura

Aura is a local-first AI desktop application from Multi AI Tech. A Leader agent coordinates a roster of specialist agents, and every role can run on an API model, a local model, or an external coding harness. Settings, credentials and chat history stay on the machine inside `AuraData/`.

## Three differentiators

1. **Team coordination** - a Leader orchestrates specialist roles (Coder, Reviewer, Security, Tester, Documentation) with configurable models per role.
2. **API, Local or Harness** - you are never locked to one vendor. Use your own API key, a model running on your machine, or a coding agent you already installed.
3. **Assembled from bricks** - modes, roles, pipelines, MCP connections, skills, modules and schedules are attached and detached by you, not fixed by the vendor.

## Membership tiers and Delta Credit (MAIC)

| Tier | Price | Mandatory Lesson Learned | Delta Credit |
|------|-------|--------------------------|--------------|
| Free | Free forever | Yes | No |
| Pro | $5/month or $50/year | Yes | Yes |
| Advance | $10/month or $100/year | Optional | Only if contributing LL |

## Delta Credit accumulation and release

- **Accumulation:** Delta Credits are collected during the membership period.
- **Release trigger:** When 200 Pro/Advance annual members are reached, token release begins.
- **Dynamic daily rate:** accumulated_credits / accumulation_days, per member.
- **Example:** 10M credits over 20 days = 500k/day per user during distribution.

### Tier change behavior

- **Paid to Free:** the Delta Credit balance resets to 0 and the accumulation backlog is zeroed.
- **Free to Paid:** the balance stays 0; only new Lesson Learned records generate Delta Credit.
- **Re-upgrade:** only contributions made after returning earn Delta Credit.

## Platform builds

| Platform | Build | Size | Download |
|----------|-------|------|----------|
| Windows x64 | `windows-x64` | 137.7 MB | [Member area](https://multiaitech.com/member.html) |
| Windows ARM64 | `windows-arm64` | 136.3 MB | [Member area](https://multiaitech.com/member.html) |
| Linux DEB | `linux-deb` | 96.1 MB | [Member area](https://multiaitech.com/member.html) |
| Linux AppImage | `linux-appimage` | 173.6 MB | [Member area](https://multiaitech.com/member.html) |

Installers are hosted in the member area only. They are never published on GitHub.

### Installing on Windows (.exe)

1. Download the `.exe` file from the member area.
2. Run the installer and follow the wizard.

### Installing on Linux (.deb)

1. Download the `.deb` file.
2. Install it with: `sudo dpkg -i <file-name>.deb`
3. If dependencies are missing, run: `sudo apt install -f`

### Installing on Linux (.AppImage)

1. Download the `.AppImage` file.
2. Make it executable: `chmod +x <file-name>.AppImage`
3. Run it with: `./<file-name>.AppImage`

## SHA-256 verification

Every installer has a SHA-256 hash published on the Released builds page (https://multiaitech.com/) and in the member portal. Compare it with the output of `sha256sum <file>` in your terminal to confirm file integrity.

## Quick start

```
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

- [MAIC Token & Economics](https://multiaitech.com/ai-info.html)
- [Owner Checklist](https://multiaitech.com/Owner.txt)
- [Upload Procedure](https://multiaitech.com/upload-web.txt)

## Proprietary

Aura core, installer, and the permission gate are closed source. User packages run in a sandboxed extension container.
