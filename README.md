# Aura

Aura is a local-first AI desktop application from Multi AI Tech. A Leader agent coordinates a roster of specialist agents, and every role can run on an API model, a local model, or an external coding harness. Settings, credentials and chat history stay on the machine inside `AuraData/`.

## Three differentiators

1. **Team coordination** - a Leader orchestrates specialist roles (Coder, Reviewer, Security, Tester, Documentation) with configurable models per role.
2. **API, Local or Harness** - you are never locked to one vendor. Use your own API key, a model running on your machine, or a coding agent you already installed.
3. **Assembled from bricks** - modes, roles, pipelines, MCP connections, skills, modules and schedules are attached and detached by you, not fixed by the vendor.

## Tier Structure & Delta Credit Release

### Membership Tiers

| Tier | Harga | Wajib LL | Dapat Delta Credit |
|------|-------|----------|-------------------|
| **Free** | Gratis selamanya | ✅ Ya | ❌ Tidak |
| **Pro** | $5/bln / $50/tahun | ✅ Ya | ✅ Ya |
| **Advance** | $10/bln / $100/tahun | ❌ Opsional | ✅ Hanya jika kontribusi LL |

### Delta Credit Accumulation

- **Kumpul selama membership**: Delta credit dikumpulkan per member selama berlangganan
- **Rilis saat token launch**: Saat kuota rilis token (200 member Pro/Advance tahunan), credit dirilis bertahap
- **Rate dinamis**: `daily_rate = accumulated_credits ÷ accumulation_days`
- Contoh: 20k credit 10 hari → **2k/hari**; 10M credit 20 hari → **500k/hari**
- Per-member, bukan fixed quota global

### Free Tier Zeroing

- Di `deltaAssessment.js`: `finalizeAssessment` → `reward_eligible_delta_credits = 0` untuk tier FREE
- LL tetap diterima & dipublish — hanya tidak dapat Delta Credit
- Invariant `verified = eligible + excluded` tetap terjaga

### Turun ke Free Tier

- LL **masa depan** tidak menghasilkan Delta Credit (di-asses berdasarkan tier saat ini)
- Delta Credit **sudah terkumpul** tidak di-clawback — tetap dirilis sesuai rumus

### Trigger Rilis Token

- Ketika 200 member Pro/Advance tahunan terpenuhi
- Credit terkumpul dibagi lama akumulasi → daily rate
- Setiap member dapat 500k/hari (contoh 10M/20 hari)

## Quick start

1. **Install** - download the Windows installer from [multiaitech.com](https://multiaitech.com/download) and run it.
Use Control + Shift + m to toggle the tab key moving focus. Alternatively, use esc then tab to move to the next interactive element on the page.
Attach files by dragging & dropping, selecting or pasting them.

## Three differentiators

1. **Team coordination** - a Leader orchestrates specialist roles (Coder, Reviewer, Security, Tester, Documentation) with configurable models per role.
2. **API, Local or Harness** - you are never locked to one vendor. Use your own API key, a model running on your machine, or a coding agent you already installed.
3. **Assembled from bricks** - modes, roles, pipelines, MCP connections, skills, modules and schedules are attached and detached by you, not fixed by the vendor.

## Models

the three executor paths in detail

## Features

modes, roles, modules, MCP, skills, browser, checkpoints

## Reference

sidebar labels, status lights, AuraData contents, troubleshooting

## Proprietary

Proprietary software from Multi AI Tech. All rights reserved. See LICENSE.

multiaitech.com
Download
